```python
from aide_design.play import *
import math as math
```
# Laboratory PreLab 5 Questions
## Sung Min Kim

1. Calculate the volume of a 40g/L red dye stock that would need to be added to 1L of water to produce 0, 5, 10, 15, 20, 25, and 30 mg/L calibration points.

```Python
dye_conc = 40000*u.mg/u.L
water_volume = 1000*u.mL
calib_5 = 5*u.mg/u.L
calib_10 = 10*u.mg/u.L
calib_15 = 15*u.mg/u.L
calib_20 = 20*u.mg/u.L
calib_25 = 25*u.mg/u.L
calib_30 = 30*u.mg/u.L

vol_5 = dye_conc*water_volume/calib_5
vol_10 = dye_conc*water_volume/calib_10
vol_15 = dye_conc*water_volume/calib_15
vol_20 = dye_conc*water_volume/calib_20
vol_25 = dye_conc*water_volume/calib_25
vol_30 = dye_conc*water_volume/calib_30
print(vol_5)
print(vol_10)
print(vol_15)
print(vol_20)
print(vol_25)
print(vol_30)
```

2. Calculate the change in hydraulic grade line between baffled sections of a reactor with a flow rate of 300 mL/min. The reactor baffles are perforated with 24 holes 1mm in diameter.

```Python
n = 24
d = 1*u.mm
A = (math.pi*d**2)/4
g = 9.81*u.m/u.s**2
Q = 300*u.mL/u.min
K= 0.6

HGL = ((Q/(K*A*n))**2)/(2*g)
print(HGL.to(u.mm))
```

3. On a single graph from Excel, plot the exit age distribution (E (t*) ) for a reactor with a
volume of 1L and a flow rate of 150 mL/min that operates as a 1-dimensional
advection-dispersion reactor with Peclet numbers of 1, 10, and 100 (there will be
three lines on the graph). The x-axis should be t* from 0.0 to 3.0. Comment on the
shapes of the curves as a function of Pe.

```Python
volume = 1000
Q = 150
residence_time = volume/Q#minutes
tstar = np.arange(0.01,3,100)

pe_1 = 1
pe_10 = 10
pe_100 = 100

Et_1 = math.sqrt(pe_1/(4*math.pi*tstar))
#*math.exp(-1*(1-tstar)**2*pe_1/(4*tstar))

plt.plot(Et_1, tstar)
plt.xlabel('Graph 1: Hydraulic Residence Time', fontsize=15)
plt.ylabel('pH', fontsize=15)
plt.show()
```
The higher the pellet number, the more advection whereas a low pellet number has more mixing. 
