```python
from aide_design.play import*
```
# Laboratory 1 PreLab Questions
## Sung Min Kim

1. Why are contact lenses hazardous in the laboratory?
Wearing contact lenses is considered hazardous in the lab because contact lenses can hold foreign materials against the cornea and they can be difficult to remove in case of a splash. Specifically, soft contact lenses are particularly hazardous because they can absorb and retain chemical vapors.

2. What is the minimum information needed on the label for each chemical? When are Right-To-Know labels required?
The minimum is the full chemical name (and chemical formula), concentration and date prepared. The Right-To-Know labels are needed if the chemical is designated as a hazardous material and if it is made into a solution or repackaged as a solid or liquid in a concentration greater than 1%.

3. Why is it important to label a bottle even if it only contains distilled water?
It is important to label a bottle even if it is only distilled water because it is a potential safety hazard for disposal. Many chemical and liquids are clear so without a label, there would be no way to distinguish multiple bottle through just color.

4. Find an SDS for sodium nitrate.
    1. Who created the SDS?
Occupational Safety and Health Administration (OSHA)
    2. What is the solubility of sodium nitrate in water?
92.1g/100 mL of water at 25 degrees Celsius
180g/100 mL of water at 100 degrees Celsius
    3. Is sodium nitrate carcinogenic?
Yes
    4. What is the LD50 oral rat?
1,267 mg/kg
    5. How much sodium nitrate would you have to ingest to give a 50% chance of death (estimate from available LD50 data).
```python
LD50rat= 1267*u.mg/u.kg
weight= 70*u.kg
death= LD50rat*weight
print(death)
```
    6. How much of a 1 M solution would you have to ingest to give a 50% chance of death?
  ```python
  MW= 84.99*u.g/u.mol
  solution= 1*u.mol/u.L
  amount= death/(MW*solution)
  print(amount.to(u.L))
  ```
    7. Are there any chronic effects of exposure to sodium nitrate?
Yes. Mutagenic for bacteria and/or yeast. Substance may be toxic to blood and can produce target organ damage.

5. You are in the laboratory preparing chemical solutions for an experiment and it is lunchtime. You decide to go to CTB to eat. What must you do before leaving the laboratory?
You first make sure that there are no reactions and equipment left to run unattended. You then put a note plainly posted with a phone number so that you and the instructor can be reached in case of an emergency.
