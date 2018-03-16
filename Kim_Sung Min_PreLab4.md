#PreLab 4
##Sung Min Kim, sk2795

1) Compare the ability of Cayuga lake and Wolf pond (an Adirondack lake) to withstand an acid rain runoff event (from snow melt) that results in 20% of the original lake water being replaced by acid rain. The acid rain has a pH of 3.5 and is in equilibrium with the atmosphere. The ANC of Cayuga lake is 1.6 meq/L and the ANC of Wolf Pond is 70 µeq/L. Assume that carbonate species are the primary component of ANC in both lakes, and that they are in equilibrium with the atmosphere. What is the pH of both bodies of water after the acid rain input? Remember that ANC is the conservative parameter (not pH!).


```python
from aide_design.play import *
import math as math
Kw = 10**(-14)
K1_carbonate = 10**(-6.37)
K2_carbonate = 10**(-10.25)
K_Henry_CO2 = 10**(-1.5)
P_CO2 = 10**(-3.5)

#inputs from 1
pHrain= 3.5
ANCrain= 10**(-pHrain)*u.mol/u.L
ANCcayuga= 1.6*10**(-3)*u.mol/u.L
ANCwolf= 70*10**(-6)*u.mol/u.L

ANCcayugaout= ANCrain*(1-math.exp(-0.2))+ANCcayuga*(math.exp(-0.2))
ANCwolfout= ANCrain*(1-math.exp(-0.2))+ANCwolf*(math.exp(-0.2))

def invpH(pH):
  return 10**(-pH)

def alpha0_carbonate(pH):
   alpha0_carbonate = 1/(1+(K1_carbonate/invpH(pH))*(1+(K2_carbonate/invpH(pH))))
   return alpha0_carbonate

def alpha1_carbonate(pH):
  alpha1_carbonate = 1/((invpH(pH)/K1_carbonate) + 1 + (K2_carbonate/invpH(pH)))
  return alpha1_carbonate

def alpha2_carbonate(pH):
  alpha2_carbonate = 1/(1+(invpH(pH)/K2_carbonate)*(1+(invpH(pH)/K1_carbonate)))
  return alpha2_carbonate
def ANC_closed(pH,Total_Carbonates):
  return Total_Carbonates*(alpha1_carbonate(pH)+2*alpha2_carbonate(pH)) + Kw/invpH(pH) - invpH(pH)

def ANC_open(pH):
  return ANC_closed(pH,P_CO2*K_Henry_CO2/alpha0_carbonate(pH))


import scipy
from scipy import optimize

# Strip the units off of the ANC function so that scipy can calculate the root.
def ANC_open_cayugaunitless(pH):
  return (ANC_open(pH)-ANCcayugaout.magnitude)

def ANC_open_wolfunitless(pH):
  return (ANC_open(pH)-ANCwolfout.magnitude)

def pH_opencayuga():
  return optimize.brentq(ANC_open_cayugaunitless, 1, 12)

def pH_openwolf():
  return optimize.brentq(ANC_open_wolfunitless, 1, 12)

pH_opencayuga()
pH_openwolf()
```

2) What is the ANC of a water sample containing only carbonates and a strong acid that is at pH 3.2? This requires that you inspect all of the species in the ANC equation and determine which species are important.

The ANC of solutions that have a pH less than 4 are equal to -[H+]. This is because when pH is this low, the concentration of protons are significantly larger than those of carbonate, bicarbonate and hydroxide.
```python
pH= 3.2
ANC= 10**(-1*pH)
print(ANC)
```

3) Why is [H+] not a conserved species?
[H+] is not a conserved species because when ANC is not 0, there are reactions that consume protons.
