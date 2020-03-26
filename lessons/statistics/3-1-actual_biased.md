[Think Stats Chapter 3 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2004.html#toc31) (actual vs. biased)

Something like the class size paradox appears if you survey children and ask how many children are in their family. Families with many children are more likely to appear in your sample, and families with no children have no chance to be in the sample.

Use the NSFG respondent variable `numkdhh` to construct the actual distribution for the number of children under 18 in the respondents' households.

Now compute the biased distribution we would see if we surveyed the children and asked them how many children under 18 (including themselves) are in their household.

Plot the actual and biased distributions, and compute their means.
```python
numkdhh_pmf = thinkstats2.Pmf(resp.numkdhh, label='numkdhh')
```
```python
numkdhh_biased_pmf = thinkstats2.Pmf(resp.numkdhh, label='numkdhh')
for x in numkdhh_biased_pmf:  
    numkdhh_biased_pmf[x] *= x  
numkdhh_biased_pmf.Normalize()
```
>>1.024205155043831
```python
thinkplot.Pmfs([numkdhh_pmf,numkdhh_biased_pmf])
```

```python
numkdhh_pmf.Mean()
```
>>1.024205155043831

```python
numkdhh_biased_pmf.Mean()
```
>>2.403679100664282

