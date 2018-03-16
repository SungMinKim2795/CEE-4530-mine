```python
from aide_design.play import*
```
# Laboratory 2 PreLab Questions
## Sung Min Kim

1. You need 100 mL of a 1 µM solution of zinc that you will use as a standard to calibrate an atomic adsorption spectrophotometer. Find a source of zinc ions combined either with chloride or nitrate (you can use the internet or any other source of information). What is the molecular formula of the compound that you found?

Zn(NO<sub>3)<sub>2

a) Zinc disposal down the sanitary sewer is restricted at Cornell and the solutions you prepare may need to be disposed of as hazardous waste. As an environmental engineering student you strive to minimize waste production. How would you prepare this standard using techniques readily available in the environmental laboratory so that you minimize the production of solutions that you don’t need? Note that we have pipettes that can dispense volumes between 10 µL and 1 mL and that we have 100 mL and 1 L volumetric flasks. Include enough information so that you could prepare the standard without doing any additional calculations. Consider your ability to accurately weigh small masses. Explain your procedure for any dilutions. Note that the stock solution concentration should be an easy multiple of your desired solution concentration.

We would prepare the low concentration standard by diluting a higher concentration stock solution. Because we are not able to accurately weigh small masses, we will prepare 18.9 mg of Zinc Nitrate to put into 1 L. The solution concentration will be 0.1 mM. Then we will take 1 mL of the 0.1mM stock solution and dilute it to 100 mL to obtain 100 mL of 1 µM.


2. The density of sodium chloride solutions as a function of concentration is approximately 0.6985C + 998.29 (kg/m3) (C is kg of salt/m3). What is the density of a 1 M solution of sodium chloride?
```python
MW= 58.4*u.g/u.mol
solution= 1*u.mol/u.L
concentration= (MW*solution).to(u.kg/u.m**3)
density= 0.6985*concentration + 998.29*u.kg/u.m**3
print(density)
```
