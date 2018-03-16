```python
from aide_design.play import*
import math as math
```
# Laboratory 3 PreLab Questions
## Sung Min Kim

1)	How many grams of NaHCO3 would be required to keep the ANC levels in a lake above 50 µeq/L for 3 hydraulic residence times given an influent pH of 3.0 and a lake volume of 4 L, if the current lake ANC is 0 µeq/L?

#due to problems with using the units equivalents, I substituted the units with moles

```python
ANCo= 0*u.umol/u.L #initial ANC in the lake
ANCout= 50*u.umol/u.L #ANC in lake at time t
ANCin= -0.001* u.mol/u.L
theta= 15*u.min #residence time
V= 4*u.L #volume of the lake
MW= 84*u.mg/u.mmol
t= 45*u.min #because we are running through 3 residence times

ANC= (ANCout-ANCin*(1-math.exp(-t/theta)))*math.exp(t/theta)
amount= (ANC.to(u.mmol/u.L))*MW*V
print (amount)

```
