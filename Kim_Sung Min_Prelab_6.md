```python
from aide_design.play import*
import math as math
```

#Prelab 6 Gas transfer
##Sung Min Kim, sk2795

1)	Calculate the mass of sodium sulfite needed to reduce all the dissolved oxygen in 4 L of pure water in equilibrium with the atmosphere and at 30°C.

```Python
###oxygen equilibrium concentration in water= 10 mg/L
###ratio of sodium sulfite: oxygen= 7.875 mg/ mg
volume= 4*u.L
oxygen_conc= 7.5*u.mg/u.L #at 30 degrees
ratio= 7.875*u.mg/u.mg
sodium_sulfite= oxygen_conc*volume*ratio
print(sodium_sulfite)

volume_2= .600*u.L
sodium_sulfite_2= oxygen_conc*volume_2*ratio
print(sodium_sulfite_2)
```

2)	Describe your expectations for dissolved oxygen concentration as a function of time during a reaeration experiment. Assume you have added enough sodium sulfite to consume all of the oxygen at the start of the experiment. What would the shape of the curve look like?

During the reaeration experiment, the shape of the curve is initially linear because there is constant reaeration until the concentration reaches the saturation concentration. Once it reaches saturation, the curve looks like a logarithmic curve.

3)	Why is $\hat{k}_{v,l}$ not zero when the gas flow rate is zero? How can oxygen transfer into the reactor even when no air is pumped into the diffuser?

Referring to equation 1.6, it would seem that $\hat{k}_{v,l}$ would be 0 when the gas flow rate is zero. However, it is not because our system is an open, not closed system. Even though there is no air being pumped in, there is still oxygen transfer with the atmosphere.

4)	Describe your expectations for $\hat{k}_{v,l}$ as a function of gas flow rate. Do you expect a straight line? Why?

The gas air flow affects bubble size and laminar boundary layer. The  $\hat{k}_{v,l}$ increases linearly with the gas flow rate. When there is a higher gas flow rate, the bubbles become bigger and thus, the interface area increases. Referring to Equation 1.3, with a larger interface area, there is an increase in the gas transfer coefficient. It increases linearly until it reaches saturation and then is constant.

5)	A dissolved oxygen probe was placed in a small vial in such a way that the vial was sealed. The water in the vial was sterile. Over a period of several hours the dissolved oxygen concentration gradually decreased to zero. Why? (You need to know how dissolved oxygen probes work to answer this!)

Over time, the dissolved oxygen concentration gradually decreases to zero because there is an applied voltage that reduces oxygen to water. The dissolved oxygen probe continues to reduce the oxygen to water and thus, decreases the dissolved oxygen concentration to zero.
