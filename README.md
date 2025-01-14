# data_science_worksheets
This is a collection of worksheets that were sent to me by a student. I have provided my own solutions. 
These worksheets and their solutions can be found else-where online. 

To avoid confusion for beginners, the main difference is my avoidance of loops where possible. 
There are certain optimisations I could still do (pointed out in my comments when possible), but I think this is a marked improvement on the previous solution versions. 

Proper vectorisation will make your code much more efficient and readable. 
"Vectorized Operations" involve applying operations simultaneously to entire arrays without the need for explicit Python loops.

For instance: 
Many students will try to fill a new column populated by the division of a current column by another current column as follows:
```python
new_list = []

for i in range(len(data)):
    calculation_result = data["column1"][i]/data["column2][i]
    new_list.append(calculation_result)

data["new_column"] = new_list
```
Thankfully pandas supports vectorized operations so the best solution would be to simply do:

`data["new_column"] = data["column1"]/data["column2"]`

Vectorized operations leverage underlying libraries (like numpy) which are heavily optimise, making them significantly faster than equivalent Python for loops.
