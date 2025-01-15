# data_science_worksheets
This is a collection of worksheets that were sent to me by a student. I have provided my own solutions. 
These worksheets and their solutions can be found else-where online. 

To avoid confusion for beginners, the main difference is my avoidance of loops where possible (except for when asked by the student for demonstration purposes). 
There are certain optimisations I could still do (pointed out in my comments when possible), but I think this is a marked improvement on the previous solution versions. 

Proper vectorisation will make your code much more efficient and readable. 
"Vectorized Operations" involve applying operations simultaneously to entire arrays without the need for explicit Python loops.

For instance: 
Many students will try to fill a new column populated by the division of a current column by another current column as follows:
```python
new_list = []

for i in range(len(data)):
    calculation_result = data["column1"][i]/data["column2"][i]
    new_list.append(calculation_result)

data["new_column"] = new_list
```
Thankfully pandas supports vectorized operations so the best solution would be to simply do:

`data["new_column"] = data["column1"]/data["column2"]`

Vectorized operations leverage underlying libraries (like numpy) which are heavily optimise, making them significantly faster than equivalent Python for loops.

### A couple of other notes about these worksheets to keep in mind:
- when reporting data on salary, housing prices, or other distributions that may be skewed by large outliers, the *median* is often a better measure of the center.
    - When data is skewed, the median is typically considered a better measure of central tendency than the mean.
    - The mean is sensitive to outliers, which can distort its representation of the "typical" value in skewed distributions.
    - The median, by contrast, is more robust against the influence of extreme values.     
- is your data really normally distributed? That's an important question to ask and there are tests for normality.
    - The assumption of normality is often critical for many statistical analyses, especially parametric tests like t-tests and ANOVAs.
    - Tests for normality include the Shapiro-Wilk test, Kolmogorov-Smirnov test, and visual assessments such as Q-Q plots or histograms.
    - However, it's also worth noting that many statistical methods are robust to deviations from normality, particularly with large sample sizes (central limit theorem). 
- it's important to consider what data is collected, how, and when.
    - For example, if we're comparing the preformance of two advertisements, you may arrive at different conclusions if you compare their succcess off of daily clicks versus weekly clicks.
    - How you aggregate your data can highlight or obscure different trends and it's important to coax this out of your data when interpreting it. 
