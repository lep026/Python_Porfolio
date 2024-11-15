# Python_Porfolio
This repository showcases all the work and code that I completed in Dr. Josh Vandenbrink's  Inro Python class. 
## Jupyter_Notebooks_Parts_1_and_2 
Im Sorry Dr. Josh :( I had some difficulty with the 2nd part and so there are lots of errors :/ 

Also since you like dad jokes... How do functions break up? They stop calling each other :) 


```python
%matplotlib inline 
import pandas as pd 
import matplotlib.pyplot as plt 
import seaborn as sns 
sns.set(style = "darkgrid")
```


```python
df = pd.read_csv('/home/student/Desktop/classroom/myfiles/notebooks/fortune500.csv')
```


```python
df.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Year</th>
      <th>Rank</th>
      <th>Company</th>
      <th>Revenue (in millions)</th>
      <th>Profit (in millions)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>1955</td>
      <td>1</td>
      <td>General Motors</td>
      <td>9823.5</td>
      <td>806</td>
    </tr>
    <tr>
      <td>1</td>
      <td>1955</td>
      <td>2</td>
      <td>Exxon Mobil</td>
      <td>5661.4</td>
      <td>584.8</td>
    </tr>
    <tr>
      <td>2</td>
      <td>1955</td>
      <td>3</td>
      <td>U.S. Steel</td>
      <td>3250.4</td>
      <td>195.4</td>
    </tr>
    <tr>
      <td>3</td>
      <td>1955</td>
      <td>4</td>
      <td>General Electric</td>
      <td>2959.1</td>
      <td>212.6</td>
    </tr>
    <tr>
      <td>4</td>
      <td>1955</td>
      <td>5</td>
      <td>Esmark</td>
      <td>2510.8</td>
      <td>19.1</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.tail()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Year</th>
      <th>Rank</th>
      <th>Company</th>
      <th>Revenue (in millions)</th>
      <th>Profit (in millions)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>25495</td>
      <td>2005</td>
      <td>496</td>
      <td>Wm. Wrigley Jr.</td>
      <td>3648.6</td>
      <td>493</td>
    </tr>
    <tr>
      <td>25496</td>
      <td>2005</td>
      <td>497</td>
      <td>Peabody Energy</td>
      <td>3631.6</td>
      <td>175.4</td>
    </tr>
    <tr>
      <td>25497</td>
      <td>2005</td>
      <td>498</td>
      <td>Wendy's International</td>
      <td>3630.4</td>
      <td>57.8</td>
    </tr>
    <tr>
      <td>25498</td>
      <td>2005</td>
      <td>499</td>
      <td>Kindred Healthcare</td>
      <td>3616.6</td>
      <td>70.6</td>
    </tr>
    <tr>
      <td>25499</td>
      <td>2005</td>
      <td>500</td>
      <td>Cincinnati Financial</td>
      <td>3614.0</td>
      <td>584</td>
    </tr>
  </tbody>
</table>
</div>




```python
df.columns = ['year', 'rank', 'company', 'revenue', 'profit']
```


```python
df.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>year</th>
      <th>rank</th>
      <th>company</th>
      <th>revenue</th>
      <th>profit</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>1955</td>
      <td>1</td>
      <td>General Motors</td>
      <td>9823.5</td>
      <td>806</td>
    </tr>
    <tr>
      <td>1</td>
      <td>1955</td>
      <td>2</td>
      <td>Exxon Mobil</td>
      <td>5661.4</td>
      <td>584.8</td>
    </tr>
    <tr>
      <td>2</td>
      <td>1955</td>
      <td>3</td>
      <td>U.S. Steel</td>
      <td>3250.4</td>
      <td>195.4</td>
    </tr>
    <tr>
      <td>3</td>
      <td>1955</td>
      <td>4</td>
      <td>General Electric</td>
      <td>2959.1</td>
      <td>212.6</td>
    </tr>
    <tr>
      <td>4</td>
      <td>1955</td>
      <td>5</td>
      <td>Esmark</td>
      <td>2510.8</td>
      <td>19.1</td>
    </tr>
  </tbody>
</table>
</div>




```python
len(df)
```




    25500




```python
df.dtypes
```




    year         int64
    rank         int64
    company     object
    revenue    float64
    profit      object
    dtype: object




```python
non_numeric_profits = df.profit.str.contains('[^0-9.-]') 
df.loc[non_numeric_profits].head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>year</th>
      <th>rank</th>
      <th>company</th>
      <th>revenue</th>
      <th>profit</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>228</td>
      <td>1955</td>
      <td>229</td>
      <td>Norton</td>
      <td>135.0</td>
      <td>N.A.</td>
    </tr>
    <tr>
      <td>290</td>
      <td>1955</td>
      <td>291</td>
      <td>Schlitz Brewing</td>
      <td>100.0</td>
      <td>N.A.</td>
    </tr>
    <tr>
      <td>294</td>
      <td>1955</td>
      <td>295</td>
      <td>Pacific Vegetable Oil</td>
      <td>97.9</td>
      <td>N.A.</td>
    </tr>
    <tr>
      <td>296</td>
      <td>1955</td>
      <td>297</td>
      <td>Liebmann Breweries</td>
      <td>96.0</td>
      <td>N.A.</td>
    </tr>
    <tr>
      <td>352</td>
      <td>1955</td>
      <td>353</td>
      <td>Minneapolis-Moline</td>
      <td>77.4</td>
      <td>N.A.</td>
    </tr>
  </tbody>
</table>
</div>




```python
set(df.profit[non_numeric_profits])
```




    {'N.A.'}




```python
len(df.profit[non_numeric_profits])
```




    0




```python
bin_sizes, _, _ = plt.hist(df.year[non_numeric_profits], bins = range(1955, 2006 ))
```


![png](output_11_0.png)



```python
df = df.loc[~non_numeric_profits]
df.profit = df.profit.apply(pd.to_numeric)
```


```python
len(df)
```




    25131




```python
df.dtypes
```




    year         int64
    rank         int64
    company     object
    revenue    float64
    profit     float64
    dtype: object




```python
group_by_year df.loc['year', 'revenue', 'profit'].groupby('year')
                     
avgs = group_by_year.mean()  
x = avgs.index 
y1 = avgs.profit 
def plot(x, y, ax,title, y_label): 
                     
as.set_title(title) 
as.set_ylabel(y_label) 
ax.plot(x,y) 
ax.margrin(x = 0, y = 0)
```


      File "<ipython-input-32-e1a7621b36ac>", line 1
        group_by_year df.loc['year', 'revenue', 'profit'].groupby('year')
                       ^
    SyntaxError: invalid syntax




```python
fig, ax = plt.subplots()
```


![png](output_16_0.png)



```python
fig, ax = plt.subplots() 
plot(x, y1, ax, 'Increase in mean Fortune 500 company profits from 1950 to 2005')
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    <ipython-input-34-7153cfc5713a> in <module>
          1 fig, ax = plt.subplots()
    ----> 2 plot(x, y1, ax, 'Increase in mean Fortune 500 company profits from 1950 to 2005')
    

    NameError: name 'plot' is not defined



![png](output_17_1.png)



```python
y2 = avgs.revenue 
fig, ax = plt.subplot() 
plot(x, y2, ax, 'Increase in mean Fortune 500 company profits from 1950 to 2005', 'Revenue(millions')')
```


      File "<ipython-input-1-515651fcc3c9>", line 3
        plot(x, y2, ax, 'Increase in mean Fortune 500 company profits from 1950 to 2005', 'Revenue(millions')')
                                                                                                               ^
    SyntaxError: EOL while scanning string literal




```python
def plot_with_std(x, y, stds, ax, title, y_label): 
    ax.fill_between(x, y - stds, y + stds, alpha = 0.2) 
    plot(a, y, ax, title, y_label) 
    fig, (ax1, ax2) = plt.subplots(ncols = 2) 
    title = 'Increase in main and std fortune 500 company %s from 1995 to 2005' 
    stds1 = group_by_year.std().profit.values 
    stds2 = group_by_year.std().revenue.values 
    plot_with_std(x, y1.values, stds1, ax1, title % 'profits', 'Profit (millions)') 
    plot_with_std(x, y1.values, stds2, ax2, title % 'profits', 'Revenue (millions)') 
    fig.set_size_inches(14,4) 
    fig.tight_layout()
```


```python

```





## Python_Fundamentals 
This shows all the work i did in python fundamentals 

```python
# Any python interpreter can be used as a calculator:  
3 + 4 * 5

```




    23




```python
# Lets save a value to a a variable 
weight_kg = 60
```


```python
print(weight_kg)
```

    60



```python
# Weight0 = valud 
# 0weight = invalid 
# weight and Weight are different
```


```python
# Types of data 
# There are three common types of data 
# Integer numbers 
# floating point numbers 
# Strings
```


```python
weight_kg=60.3 
# floating point
```


```python
patient_name = "John Smith" 
# String comprised of letters
```


```python
patient_id = "001"  
# String comprised of numbers

```


```python
# Use variables in python 

weight_lb = 2.2 * weight_kg 

print(weight_lb)

```

    132.66



```python
# lets add a prefix to our patient id 

patient_id = 'inflam_' + patient_id 

print(patient_id)

```

    inflam_001



```python
# Lets combine print statements 

print(patient_id, 'weight in kilograms:', weight_kg)
```

    inflam_001 weight in kilograms: 60.3



```python
# we can call a function inside another function 

print(type(60.3)) 

print(type(patient_id))
```

    <class 'float'>
    <class 'str'>



```python
# We can also do calculations inside the print function 

print('weight in lbs', 2.2 * weight_kg)
```

    weight in lbs 132.66



```python
print(weight_kg)
```

    60.3



weight_kg = 65.0 

print('weight in kilograms is now', weight_kg)
```

    weight in kilograms is now 65.0




```

## Analyzing_Patient_Data 
This showcases all the work i did for analyzing inflammation data 

```python
import numpy
```


```python
numpy.loadtxt(fname = 'inflammation-01.csv', delimiter = ',')
```




    array([[0., 0., 1., ..., 3., 0., 0.],
           [0., 1., 2., ..., 1., 0., 1.],
           [0., 1., 1., ..., 2., 1., 1.],
           ...,
           [0., 1., 1., ..., 1., 1., 1.],
           [0., 0., 0., ..., 0., 2., 0.],
           [0., 0., 1., ..., 1., 1., 0.]])




```python
data = numpy.loadtxt(fname = 'inflammation-01.csv', delimiter = ',')
```


```python
print(data)
```

    [[0. 0. 1. ... 3. 0. 0.]
     [0. 1. 2. ... 1. 0. 1.]
     [0. 1. 1. ... 2. 1. 1.]
     ...
     [0. 1. 1. ... 1. 1. 1.]
     [0. 0. 0. ... 0. 2. 0.]
     [0. 0. 1. ... 1. 1. 0.]]



```python
print(type(data))
```

    <class 'numpy.ndarray'>



```python
print(data.shape)
```

    (60, 40)



```python
print('first value in data:', data[0,0])
```

    first value in data: 0.0



```python
print('middle value in data', data[29,19])
```

    middle value in data 16.0



```python
print(data[0:4, 0:10])
```

    [[0. 0. 1. 3. 1. 2. 4. 7. 8. 3.]
     [0. 1. 2. 1. 2. 1. 3. 2. 2. 6.]
     [0. 1. 1. 3. 3. 2. 6. 2. 5. 9.]
     [0. 0. 2. 0. 4. 2. 2. 1. 6. 7.]]



```python
print(data[5:10, 0:10])
```

    [[0. 0. 1. 2. 2. 4. 2. 1. 6. 4.]
     [0. 0. 2. 2. 4. 2. 2. 5. 5. 8.]
     [0. 0. 1. 2. 3. 1. 2. 3. 5. 3.]
     [0. 0. 0. 3. 1. 5. 6. 5. 5. 8.]
     [0. 1. 1. 2. 1. 3. 5. 3. 5. 8.]]



```python
small = data[:3, 36:]
```


```python
print('small is:')
```

    small is:



```python
print(small)
```

    [[2. 3. 0. 0.]
     [1. 1. 0. 1.]
     [2. 2. 1. 1.]]



```python
#lets us a numpy function 

print(numpy.mean(data))
```

    6.14875



```python
maxval, minval, stdval = numpy.amax(data), numpy.amin(data), numpy.std(data)
```


```python
print(maxval) 
print(minval) 
print(stdval)
```

    20.0
    0.0
    4.613833197118566



```python
print('maximum inflammation:', maxval) 
print('minimum inflammation:', minval) 
print('standard deviation:', stdval) 
```

    maximum inflammation: 20.0
    minimum inflammation: 0.0
    standard deviation: 4.613833197118566



```python
#sometimes we want to look at variation in statistical values, such as maximum inflammation per patient or average from day one. 

pateint_0 = data[0, :] # 0 on the first axis (rows), everythingon the second (columns) 

print('maximum inflammation for patient 0:', numpy.amax(patient_0)) 


```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    <ipython-input-28-94e5c3206992> in <module>
          3 pateint_0 = data[0, :] # 0 on the first axis (rows), everythingon the second (columns)
          4 
    ----> 5 print('maximum inflammation for patient 0', numpy.amax(patient_0))
          6 


    NameError: name 'patient_0' is not defined



```python
print('maximum inflammation for patient 2:', numpy.amax(data[2, :]))
```

    maximum inflammation for patient 2: 19.0



```python
print(numpy.mean(data, axis = 0))
```

    [ 0.          0.45        1.11666667  1.75        2.43333333  3.15
      3.8         3.88333333  5.23333333  5.51666667  5.95        5.9
      8.35        7.73333333  8.36666667  9.5         9.58333333 10.63333333
     11.56666667 12.35       13.25       11.96666667 11.03333333 10.16666667
     10.          8.66666667  9.15        7.25        7.33333333  6.58333333
      6.06666667  5.95        5.11666667  3.6         3.3         3.56666667
      2.48333333  1.5         1.13333333  0.56666667]



```python
print(numpy.mean(data, axis = 0).shape)
```

    (40,)



```python
print(numpy.mean(data, axis = 1))
```

    [5.45  5.425 6.1   5.9   5.55  6.225 5.975 6.65  6.625 6.525 6.775 5.8
     6.225 5.75  5.225 6.3   6.55  5.7   5.85  6.55  5.775 5.825 6.175 6.1
     5.8   6.425 6.05  6.025 6.175 6.55  6.175 6.35  6.725 6.125 7.075 5.725
     5.925 6.15  6.075 5.75  5.975 5.725 6.3   5.9   6.75  5.925 7.225 6.15
     5.95  6.275 5.7   6.1   6.825 5.975 6.725 5.7   6.25  6.4   7.05  5.9  ]



```python

```

## Analyzing_Data_2_Data_Visualization 
This section includes the work i did for sections 2 and 3 of the Analyzing Data section. 

```python
import numpy 
data = numpy.loadtxt(fname= 'inflammation-01.csv', delimiter = ',')
```


```python
import matplotlib.pyplot 
image = matplotlib.pyplot.imshow(data) 
matplotlib.pyplot.show()
```


![png](output_1_0.png)



```python
# average inflammation over time 

ave_inflammation = numpy.mean(data, axis = 0) 
ave_plot = matplotlib.pyplot.plot(ave_inflammation) 
matplotlib.pyplot.show()
```


![png](output_2_0.png)



```python
max_plot = matplotlib.pyplot(numpy.amax(data, axis = 0)) 
matplotlib.pyplot.show()
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    <ipython-input-10-9b3aa0a24171> in <module>
    ----> 1 max_plot = matplotlib.pyplot(numpy.amax(data, axis = 0))
          2 matplotlib.pyplot.show()


    TypeError: 'module' object is not callable



```python
min_plot = matplotlib.pyplot.plot(numpy.amin(data, axis = 0)) 
mtplotlib.pyplot.show()
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    <ipython-input-11-269fe4855bc2> in <module>
          1 min_plot = matplotlib.pyplot.plot(numpy.amin(data, axis = 0))
    ----> 2 mtplotlib.pyplot.show()
    

    NameError: name 'mtplotlib' is not defined



![png](output_4_1.png)



```python
import numpy 
import matplotlib.pyplot 

```


```python
fig = matplotlib.pyplot.figure(figsize = (10.0, 3.0)) 

axes1 = fig.add_subplot(1, 3, 1) 
axes2 = fig.add_subplot(1, 3, 2) 
axes3 = fig.add_subplot(1, 3, 3) 

axes1.set_ylabel('average') 
axes1.plot(numpy.mean(data, axis = 0)) 

axes2.set_ylabel('max') 
axes2.plot(numpy.amax(data, axis = 0)) 

axes3.set_ylabel('min') 
axes3.plot(numpy.amin(data, axis =0)) 

fig.tight_layout() 
matplotlib.pyplot.savefig('inflammation.png')  
matplotlib.pyplot.show()

```


![png](output_6_0.png)



```python

```
## Analyzing Data 3 

I need to go in and see what name i gave this file in jupyter  

## Storing Values in Lists 

```python
odds = [1, 3, 5, 7] 
print('odds are:', odds)
```

    odds are: [1, 3, 5, 7]



```python
print('first element:', odds[0]) 
print('last element:', odds[3]) 
print('"-1" element:', odds[-1])
```

    first element: 1
    last element: 7
    "-1" element: 7



```python
names = ['Curie', 'Darwing', 'Turing'] # typo in Darwins name 

print('names is originally:', names)  

names[1] = 'Darwin' # Correct the name  

print('final value of names:', names)
```

    names is originally: ['Curie', 'Darwing', 'Turing']
    final value of names: ['Curie', 'Darwin', 'Turing']



```python
#name = 'Darwin' 
#name[0] = 'd'
```


```python
odds.append(11) 
print('odds after adding a value:', odds)
```

    odds after adding a value: [1, 3, 5, 7, 11, 11]



```python
removed_element = odds.pop(0) 
print('odds after removing first element:', odds) 
print('removed_element:', removed_element)
```

    odds after removing first element: [3, 5, 7, 11, 11]
    removed_element: 1



```python
odds.reverse() 
print('odds after reversing:', odds)
```

    odds after reversing: [11, 11, 7, 5, 3]



```python
odds = [3,5,7] 
primes = odds 
primes.append(2) 
print('primes:', primes) 
print('odds:', odds)
```

    primes: [3, 5, 7, 2]
    odds: [3, 5, 7, 2]



```python
odds = [3,5,7] 
primes = list(odds) 
primes.append(2) 
print('primes:', primes)
print('odds:', odds)
```

    primes: [3, 5, 7, 2]
    odds: [3, 5, 7]



```python
binomial_name = "Drosophila melanogaster" 
group = binomial_name[0:10] 
print('group:', group) 

species = binomial_name[11:23] 
print('species', species) 
chromosomes = ['X', 'Y', '2', '3', '4'] 
autosomes = chromosomes[2:5] 
print('autosomes:', autosomes) 
last = chromosomes[-1] 
print('last:', last)
```

    group: Drosophila
    species melanogaster
    autosomes: ['2', '3', '4']
    last: 4



```python
date = 'Monday 4 January 2023'
day = date[0:6]
print('Using 0 to begin range:', day)
day = date[:6]
print('omitting beginning index:', day)
```

    Using 0 to begin range: Monday
    omitting beginning index: Monday



```python
months = ['jan,' 'feb', 'mar', 'apr', 'may', 'jun', 'jul', 'aug', 'sep', 'oct', 'nov', 'dec'] 
          
sond = months[8:12] 

print('With known last position:', sond) 
sond = months[8:len(months)]  
print('Using len() to get last entry:', sond) 
sand = months[8:] 
print('Omitting ending index:', sond)
```

    With known last position: ['oct', 'nov', 'dec']
    Using len() to get last entry: ['oct', 'nov', 'dec']
    Omitting ending index: ['oct', 'nov', 'dec']



```python

```

## Using Loops 

```python
odds = [1,3,5,7] 
```


```python
print(odds[0])
print(odds[1]) 
print(odds[2]) 
print(odds[3])
```

    1
    3
    5
    7



```python
odds = [1,3,5] 
print(odds[0]) 
print(odds[1]) 
print(odds[2]) 
print(odds[3])
```

    1
    3
    5



    ---------------------------------------------------------------------------

    IndexError                                Traceback (most recent call last)

    <ipython-input-3-70c007a0821f> in <module>
          3 print(odds[1])
          4 print(odds[2])
    ----> 5 print(odds[3])
    

    IndexError: list index out of range



```python

```


```python
odds = [1, 3, 5, 7, 9, 11, 13, 15, 17, 19] 

for num in odds: 
    print(num)
```

    1
    3
    5
    7
    9
    11
    13
    15
    17
    19



```python
length = 0 
names = ['Curie', 'Darwin', 'Turting'] 
for value in names: 
    length = length + 1 
print('There are', length, 'names in the list')
```

    There are 3 names in the list



```python
name = "Rosalind" 
for name in ['Curie', 'Darwin', 'Turing']: 
    print(name) 
print('after the loop, name is', name)
```

    Curie
    Darwin
    Turing
    after the loop, name is Turing



```python
print(len([0,1,2,3]))
```

    4



```python
name = ['Curie', 'Darwin','Turing'] 

print(len(name))
```

    3



```python

```

## Using Multiple Files 

```python
import glob
```


```python
print(glob.glob('inflammation*.csv'))
```

    ['inflammation-10.csv', 'inflammation-09.csv', 'inflammation-11.csv', 'inflammation-06.csv', 'inflammation-05.csv', 'inflammation-08.csv', 'inflammation-01.csv', 'inflammation-07.csv', 'inflammation-04.csv', 'inflammation-03.csv', 'inflammation-02.csv', 'inflammation-12.csv']



```python
import glob 
import numpy 
import matplolib.pyplot 

filenames = sorted(glob.glob('inflammation*.csv')) 
filenames = filenames[0:3] 

for filename in filenames: 
    print(filename) 
    
    data = numpy.load.txt(fname=filename, delimiter = ',') 
    
    fig = matplotlib.pyplot.figure(figsize = (10.0, 3.0) 
    
    axes1 = fig.add_subplot(1,3,1) 
    axes2 = fig.add_subplot(1,3,2) 
    axes3 = fig.add_subplot(1,3,3) 
    
    axes1.set_ylabel('average') 
    axes1.plot(numpy.mean(data, axis = 0)) 
    
    axes2.set_ylabel('max') 
    axes2.plot(numpy.amax(data, axis = 0))  
    
    axes3.set_ylabel('min') 
    axes3.plot(numpy.amin(data, axis = 0)) 
    
    fig.tight_layout() 
    matplotlib.pyplot.show()
```


      File "<ipython-input-8-3d286e472047>", line 15
        axes1 = fig.add_subplot(1,3,1)
            ^
    SyntaxError: invalid syntax




```python
#ask dr josh why this is not running
```


```python

```

## Making Choices 

### Making_choices_2  

```python
import numpy
```


```python
data = numpy.loadtxt(fname='inflammation-01.csv', delimiter = ',')

```


```python
max_inflammation_0 = numpy.amax(data, axis = 0) 

```


```python
max_inflammation_20 = numpy.amax(data, axis = 0)[20] 

if max_inflammation_0 == 0 and max_inflammation_20 == 20: 
    print('Saspictious looking maxima!')
```


    ---------------------------------------------------------------------------

    ValueError                                Traceback (most recent call last)

    <ipython-input-7-2aaa6d4d284d> in <module>
          1 max_inflammation_20 = numpy.amax(data, axis = 0)[20]
          2 
    ----> 3 if max_inflammation_0 == 0 and max_inflammation_20 == 20:
          4     print('Saspictious looking maxima!')


    ValueError: The truth value of an array with more than one element is ambiguous. Use a.any() or a.all()



```python
elif numpy.sum(numpy.amin(data, axis = 0)) == 0: 
    print('Minima add up to zero!')
```


      File "<ipython-input-8-94b57988b22c>", line 1
        elif numpy.sum(numpy.amin(data, axis = 0)) == 0:
           ^
    SyntaxError: invalid syntax




```python
else: 
    print('seems ok')
```


      File "<ipython-input-9-a219a9d5551e>", line 1
        else:
           ^
    SyntaxError: invalid syntax




```python
data = numpy.load.txt(fname = 'inflammation-03.csv' , delimiter= ',') 

max_inflammation_0 = numpy.amax(data, axis = 0)[0] 

max_inflammation_20 = numpy.amax(data, axis = 0)[20] 

if max_inflammation_0 == and max_inflammation_20 == 20: 
    print('suspicious looking maxima') 
elif numpy.sum(numpy.amin(data, axis=0)) == 0: 
    print('minima add up to zero -> healthy person alaert') 
else: 
    print('seems ok')
```


      File "<ipython-input-11-2cbefcdf0e96>", line 7
        if max_inflammation_0 == and max_inflammation_20 == 20:
                                   ^
    SyntaxError: invalid syntax




```python

```

### Making_Choices 

```python
num = 37 
if num > 100: 
    print('greater') 
else: 
    print('not greater') 
print('done')
    

    
```

    not greater
    done



```python
num = 53 
print('before conditional...') 
if num > 100: 
    print(num, 'is greater than 100') 
print('...after conditional')
```

    before conditional...
    ...after conditional



```python
num = -3 

if num > 0: 
    print(num, 'is positive')
elif num == 0:
    print(num, 'is zero')
else: 
    print(num, 'is negative')
```

    -3 is negative



```python
if (1 > 0) and (-1 >= 0): 
    print('both parts are true')
else: 
    print('at least one part if false')
```

    at least one part if false



```python
if (-1 > 0) or (-1 >= 0): 

    print('at least one part is false') 
else: 
    print('both of these are false')
```

    both of these are false



```python
import numpy 
```


```python

```

## Functions (1,2,3,and 4) 

### Functions_Part_1 

```python
fahrenheit_val = 99 
celcius_val = ((fahrenheit_val - 32) *(5/9)) 

print(celcius_val)
```

    37.22222222222222



```python
fahrenheit_val2 = 43 
celcius_val2 = ((fahrenheit_val2 - 32) *(5/9)) 

print(celcius_val2)
```

    6.111111111111112



```python
def explicit_fahr_to_celsius(temp): 
    # Assign the converted value to variable 
    converted = ((temp - 32) * (5/9)) 
    # return the values of the new variable 
    return converted
```


```python
def fahr_to_celsius(temp): 
    # return converted values more efficiently using the return function without creating 
    # a new variable. this code does the same thing as the previous function but it is more 
    # explicit in explaining how the return commnd works. 
    return ((temp - 32) * (5/9))
```


```python
fahr_to_celsius(32) 
```




    0.0




```python
explicit_fahr_to_celsius(32)
```




    0.0




```python
print('freezing point of water:', fahr_to_celsius(32), 'C') 
print('boiling point of water:', fahr_to_celsius(221), 'C')
```

    freezing point of water: 0.0 C
    boiling point of water: 105.0 C



```python
def celsius_to_kevin(temp_c): 
    return temp_c + 273.15 

print('freezing point of water in Kelvin:' , celsius_to_kelvin(0.))
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    <ipython-input-20-f807a024d3c1> in <module>
          2     return temp_c + 273.15
          3 
    ----> 4 print('freezing point of water in Kelvin:' , celsius_to_kelvin(0.))
    

    NameError: name 'celsius_to_kelvin' is not defined



```python
def fahr_to_kelvin(temp_f): 
    temp_c = fahr_to_celsius(temp_f) 
    temp_k = celsius_to_kelvin(temp_c) 
    return temp_k 

print('boiling point of water in kelvin:', fahr_to_kelvin(212.0))
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    <ipython-input-18-65409be2dd2e> in <module>
          4     return temp_k
          5 
    ----> 6 print('freezing point of water in kelvin:', fahr_to_kelvin(212.0))
    

    <ipython-input-18-65409be2dd2e> in fahr_to_kelvin(temp_f)
          1 def fahr_to_kelvin(temp_f):
          2     temp_c = fahr_to_celsius(temp_f)
    ----> 3     temp_k = celsius_to_kelvin(temp_c)
          4     return temp_k
          5 


    NameError: name 'celsius_to_kelvin' is not defined



```python
print('Again, temperature in Kelvin was:', temp_k)
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    <ipython-input-21-eed2471d229b> in <module>
    ----> 1 print('Again, temperature in Kelvin was:', temp_k)
    

    NameError: name 'temp_k' is not defined



```python
temp_kelvin = fahr_to_kelvin(212.0)
print('Temperature in Kelvin was:', temp_kelvin)
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    <ipython-input-25-aae613bdf395> in <module>
    ----> 1 temp_kelvin = fahr_to_kelvin(212.0)
          2 print('Temperature in Kelvin was:', temp_kelvin)


    <ipython-input-18-65409be2dd2e> in fahr_to_kelvin(temp_f)
          1 def fahr_to_kelvin(temp_f):
          2     temp_c = fahr_to_celsius(temp_f)
    ----> 3     temp_k = celsius_to_kelvin(temp_c)
          4     return temp_k
          5 


    NameError: name 'celsius_to_kelvin' is not defined



```python
def print_temperature(): 
    print('Temperature in Fahrenheit was:', temp_fahr)
    print('Temperature in Kelvin was:', temp_kelvin)
    
temp_fahr = 212.0 
temp_kelvin = fahr_to_kelvin(temp_fahr) 

print_temperaturres()
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    <ipython-input-28-9371da9cb6aa> in <module>
          4 
          5 temp_fahr = 212.0
    ----> 6 temp_kelvin = fahr_to_kelvin(temp_fahr)
          7 
          8 print_temperaturres()


    <ipython-input-18-65409be2dd2e> in fahr_to_kelvin(temp_f)
          1 def fahr_to_kelvin(temp_f):
          2     temp_c = fahr_to_celsius(temp_f)
    ----> 3     temp_k = celsius_to_kelvin(temp_c)
          4     return temp_k
          5 


    NameError: name 'celsius_to_kelvin' is not defined



```python

```
### creating-functions-part-2 

```python
import numpy  
import glob 
import matplotlib 
import matplotlib.pyplot 

```


```python
def visualize(filename): 
    
    data = numpy.loadtxt(fname = filename, delimiter = ',') 
    
    fig = matplotlib.pyplot.figure(figsize=(10.0, 3.0)) 
    
    axes1 = fig.add_subplot(1, 3, 1) 
    axes2 = fig.add_subplot(1, 3, 2) 
    axes3 = fig.add_subplot(1, 3, 3) 
    
    axes1.set_ylabel('average')  
    axes1.plot(numpy.mean(data, axis = 0)) 
    
    axes2.set_ylabel('max') 
    axes2.plot(numpy.amax(data, axis = 0)) 
    
    axes3.set_ylabel('min') 
    axes3.plot(numpy.amin(data, axis = 0)) 
    
    fig.tight_layout() 
    matplotlib.pyplot.show()
```


```python
def detect_problems(filename): 
    
    data = numpy.loadtxt(fname = filename, delimiter = ',') 
    
    if numpy.amax(data, axis = 0)[0] == 0 and numpy.amax(data, axis=0)[20] == 20: 
        print("Suspicious looking maxima") 
    elif numpy.sum(numpy.amin(data, axis = 0)) == 0: 
        print('Minimum add up to zero') 
    else: 
        print('Seems ok') 
filenames = sorted(glob.glob('inflammation*.csv'))
```


```python
filenames = sorted(glob.glob('inflammation*.csv')) 

for filename in filenames:
    print(filename) 
    visualize(filename)
    detect_problems(filename)
```

    inflammation-01.csv



![png](output_3_1.png)


    Suspicious looking maxima
    inflammation-02.csv



![png](output_3_3.png)


    Suspicious looking maxima
    inflammation-03.csv



![png](output_3_5.png)


    Minimum add up to zero
    inflammation-04.csv



![png](output_3_7.png)


    Suspicious looking maxima
    inflammation-05.csv



![png](output_3_9.png)


    Suspicious looking maxima
    inflammation-06.csv



![png](output_3_11.png)


    Suspicious looking maxima
    inflammation-07.csv



![png](output_3_13.png)


    Suspicious looking maxima
    inflammation-08.csv



![png](output_3_15.png)


    Minimum add up to zero
    inflammation-09.csv



![png](output_3_17.png)


    Suspicious looking maxima
    inflammation-10.csv



![png](output_3_19.png)


    Suspicious looking maxima
    inflammation-11.csv



![png](output_3_21.png)


    Minimum add up to zero
    inflammation-12.csv



![png](output_3_23.png)


    Suspicious looking maxima



```python
def offset_mean(data, target_mean_value): 
    return (data - numpy.mean(data)) + target_mean_value
```


```python
z = numpy.zeros((2,2)) 
print(offset_mean(z, 3)) 

```

    [[3. 3.]
     [3. 3.]]



```python
data = numpy.loadtxt(fname = 'inflammation-01.csv', delimiter = ',') 

print(offset_mean(data, 0))
```

    [[-6.14875 -6.14875 -5.14875 ... -3.14875 -6.14875 -6.14875]
     [-6.14875 -5.14875 -4.14875 ... -5.14875 -6.14875 -5.14875]
     [-6.14875 -5.14875 -5.14875 ... -4.14875 -5.14875 -5.14875]
     ...
     [-6.14875 -5.14875 -5.14875 ... -5.14875 -5.14875 -5.14875]
     [-6.14875 -6.14875 -6.14875 ... -6.14875 -4.14875 -6.14875]
     [-6.14875 -6.14875 -5.14875 ... -5.14875 -5.14875 -6.14875]]



```python
print('original min, mean and max are:', numpy.amin(data), numpy.mean(data), numpy.amax(data)) 
offset_data = offset_mean(data, 0) 
print('min, mean, and max of offset data are:', 
    numpy.amin(offset_data), 
    numpy.mean(offset_data), 
    numpy.amax(offset_data))
```

    original min, mean and max are: 0.0 6.14875 20.0
    min, mean, and max of offset data are: -6.14875 2.842170943040401e-16 13.85125



```python
print('std dev before and after:', numpy.std(data), numpy.std(offset_data))
```

    std dev before and after: 4.613833197118566 4.613833197118566



```python
print('difference in standard deviation before and after:', 
      numpy.std(data) - numpy.std(offset_data))
```

    difference in standard deviation before and after: 0.0



```python
# offset_mean(data, target_mean_value): 
# return a new array containing the original data with its mean offset to match the desired value. 
# This data should be imputed as a measurement in columns and samples in rows

def offset_mean(data, target_mean_value): 
    return (data - numpy.mean(data)) + target_mean_value
```


```python
def offset_mean(data, target_mean_value): 
    """Return a new array containing the original datra with its mean offset to match the desired value""" 
    return(data - numpy.mean(data)) + target_mean_value
```


```python
help(offset_mean)
```

    Help on function offset_mean in module __main__:
    
    offset_mean(data, target_mean_value)
        Return a new array containing the original datra with its mean offset to match the desired value
    



```python
def offset_mean(data, target_mean_value): 
    """Return a new array containing the original data with its mean offset to match the desired value. 
    
    Examples 
    ---------- 
    
    >>> Offset_mean([1,2,3], 0) 
    array([-1., 0., 1.]) 
    """ 
    return (data - numpy.mean(data)) + target_mean_value
```


```python
help(offset_mean)
```

    Help on function offset_mean in module __main__:
    
    offset_mean(data, target_mean_value)
        Return a new array containing the original data with its mean offset to match the desired value. 
        
        Examples 
        ---------- 
        
        >>> Offset_mean([1,2,3], 0) 
        array([-1., 0., 1.])
    



```python
numpy.loadtxt('inflammation-01.csv', delimiter = ',')
```




    array([[0., 0., 1., ..., 3., 0., 0.],
           [0., 1., 2., ..., 1., 0., 1.],
           [0., 1., 1., ..., 2., 1., 1.],
           ...,
           [0., 1., 1., ..., 1., 1., 1.],
           [0., 0., 0., ..., 0., 2., 0.],
           [0., 0., 1., ..., 1., 1., 0.]])




```python
def offset_mean(data, target_mean_value = 0.0): 
    """Return a new array containing the original data with its mean offset to match the desired value, (0 by default). 
    
    Examples 
    ---------- 
    
    >>> offset_mean([1,2,3]) 
    array([-1., 0., 1.]) 
    """ 
    return (data - numpy.mean(data)) + target_mean_value
```


```python
test_data = numpy.zeros((2,2)) 
print(offset_mean(test_data, 3))
```

    [[3. 3.]
     [3. 3.]]



```python
print(offset_mean(test_data))
```

    [[0. 0.]
     [0. 0.]]



```python
def display(a=1, b=2, c=3): 
    print('a:', a, 'b:', b, 'c:', c) 
    
    print('no parameters:') 
    display() 
    print('one parameter:') 
    display(55) 
    print('two parameters:') 
    display(55,66)
```


```python
print('only setting the value of c') 
display(c = 77)
```

    only setting the value of c
    a: 1 b: 2 c: 77
    no parameters:
   
    
   
   


    ---------------------------------------------------------------------------

    RecursionError                            Traceback (most recent call last)

    <ipython-input-28-8580baa3a697> in <module>
          1 print('only setting the value of c')
    ----> 2 display(c = 77)
    

    <ipython-input-27-3c91cc97c252> in display(a, b, c)
          3 
          4     print('no parameters:')
    ----> 5     display()
          6     print('one parameter:')
          7     display(55)


    ... last 1 frames repeated, from the frame below ...


    <ipython-input-27-3c91cc97c252> in display(a, b, c)
          3 
          4     print('no parameters:')
    ----> 5     display()
          6     print('one parameter:')
          7     display(55)


    RecursionError: maximum recursion depth exceeded while calling a Python object



```python
help(numpy.loadtxt)
```

    Help on function loadtxt in module numpy:
    
    loadtxt(fname, dtype=<class 'float'>, comments='#', delimiter=None, converters=None, skiprows=0, usecols=None, unpack=False, ndmin=0, encoding='bytes', max_rows=None)
        Load data from a text file.
        
        Each row in the text file must have the same number of values.
        
        Parameters
        ----------
        fname : file, str, or pathlib.Path
            File, filename, or generator to read.  If the filename extension is
            ``.gz`` or ``.bz2``, the file is first decompressed. Note that
            generators should return byte strings for Python 3k.
        dtype : data-type, optional
            Data-type of the resulting array; default: float.  If this is a
            structured data-type, the resulting array will be 1-dimensional, and
            each row will be interpreted as an element of the array.  In this
            case, the number of columns used must match the number of fields in
            the data-type.
        comments : str or sequence of str, optional
            The characters or list of characters used to indicate the start of a
            comment. None implies no comments. For backwards compatibility, byte
            strings will be decoded as 'latin1'. The default is '#'.
        delimiter : str, optional
            The string used to separate values. For backwards compatibility, byte
            strings will be decoded as 'latin1'. The default is whitespace.
        converters : dict, optional
            A dictionary mapping column number to a function that will parse the
            column string into the desired value.  E.g., if column 0 is a date
            string: ``converters = {0: datestr2num}``.  Converters can also be
            used to provide a default value for missing data (but see also
            `genfromtxt`): ``converters = {3: lambda s: float(s.strip() or 0)}``.
            Default: None.
        skiprows : int, optional
            Skip the first `skiprows` lines, including comments; default: 0.
        usecols : int or sequence, optional
            Which columns to read, with 0 being the first. For example,
            ``usecols = (1,4,5)`` will extract the 2nd, 5th and 6th columns.
            The default, None, results in all columns being read.
        
            .. versionchanged:: 1.11.0
                When a single column has to be read it is possible to use
                an integer instead of a tuple. E.g ``usecols = 3`` reads the
                fourth column the same way as ``usecols = (3,)`` would.
        unpack : bool, optional
            If True, the returned array is transposed, so that arguments may be
            unpacked using ``x, y, z = loadtxt(...)``.  When used with a structured
            data-type, arrays are returned for each field.  Default is False.
        ndmin : int, optional
            The returned array will have at least `ndmin` dimensions.
            Otherwise mono-dimensional axes will be squeezed.
            Legal values: 0 (default), 1 or 2.
        
            .. versionadded:: 1.6.0
        encoding : str, optional
            Encoding used to decode the inputfile. Does not apply to input streams.
            The special value 'bytes' enables backward compatibility workarounds
            that ensures you receive byte arrays as results if possible and passes
            'latin1' encoded strings to converters. Override this value to receive
            unicode arrays and pass strings as input to converters.  If set to None
            the system default is used. The default value is 'bytes'.
        
            .. versionadded:: 1.14.0
        max_rows : int, optional
            Read `max_rows` lines of content after `skiprows` lines. The default
            is to read all the lines.
        
            .. versionadded:: 1.16.0
        
        Returns
        -------
        out : ndarray
            Data read from the text file.
        
        See Also
        --------
        load, fromstring, fromregex
        genfromtxt : Load data with missing values handled as specified.
        scipy.io.loadmat : reads MATLAB data files
        
        Notes
        -----
        This function aims to be a fast reader for simply formatted files.  The
        `genfromtxt` function provides more sophisticated handling of, e.g.,
        lines with missing values.
        
        .. versionadded:: 1.10.0
        
        The strings produced by the Python float.hex method can be used as
        input for floats.
        
        Examples
        --------
        >>> from io import StringIO   # StringIO behaves like a file object
        >>> c = StringIO(u"0 1\n2 3")
        >>> np.loadtxt(c)
        array([[0., 1.],
               [2., 3.]])
        
        >>> d = StringIO(u"M 21 72\nF 35 58")
        >>> np.loadtxt(d, dtype={'names': ('gender', 'age', 'weight'),
        ...                      'formats': ('S1', 'i4', 'f4')})
        array([(b'M', 21, 72.), (b'F', 35, 58.)],
              dtype=[('gender', 'S1'), ('age', '<i4'), ('weight', '<f4')])
        
        >>> c = StringIO(u"1,0,2\n3,0,4")
        >>> x, y = np.loadtxt(c, delimiter=',', usecols=(0, 2), unpack=True)
        >>> x
        array([1., 3.])
        >>> y
        array([2., 4.])
    



```python
numpy.loadtxt('inflammation-01.csv', delimiter = ',')
```




    array([[0., 0., 1., ..., 3., 0., 0.],
           [0., 1., 2., ..., 1., 0., 1.],
           [0., 1., 1., ..., 2., 1., 1.],
           ...,
           [0., 1., 1., ..., 1., 1., 1.],
           [0., 0., 0., ..., 0., 2., 0.],
           [0., 0., 1., ..., 1., 1., 0.]])




```python

```

what videos and see what other 2 files need to be added

## Defensive Programming 

```python
numbers = [1.5, 2.3, 0.001, 4.4] 
total = 0.0 
for num in numbers: 
    assert num > 0.0, 'Data should only contain positive values'
    total += num 
print('total is:', total)
```

    total is: 8.201



```python
numbers = [1.5, 2.3, -0.001, 4.4] 
total = 0.0 
for num in numbers: 
    assert num > 0.0, 'Data should only contain positive values'
    total += num 
print('total is:', total)
```


    ---------------------------------------------------------------------------

    AssertionError                            Traceback (most recent call last)

    <ipython-input-3-c2f302079723> in <module>
          2 total = 0.0
          3 for num in numbers:
    ----> 4     assert num > 0.0, 'Data should only contain positive values'
          5     total += num
          6 print('total is:', total)


    AssertionError: Data should only contain positive values



```python
def normalize_rectangle(rect):
    """Normalizes a rectangle so that it is at the origin and 1.0 units long on its longesr axis. insputshould be of the format (x0,, y0, x1, y1). 
    (x0, y0) and (x1, y1) define the lower left and upper right corners of the rectangle respectively""" 
    assert len(rect) == 4, 'Rectangles must contin 4 coordinates' 
    x0, y0, x1, y1 = rect 
    assert x0 < x1, 'Invalid X coordinates' 
    assert y0 < y1, 'Invalid Y coordiates' 
    
    dx = x1 - x0 
    dy = y1 - y0 
    if dx > dy:  
        scaled = dy / dx 
        upper_x, upper_y = 1.0, scaled 
    else: 
        scaled = dx / dy 
        upper_x, upper_y = scaled, 1.0 
        
    assert 0 < upper_x <= 1.0, 'Calculated upper X coordinate invalid'  
    assert 0 < upper_y <= 1.0, 'Calculated upper Y coordinate invalid' 
    
    return (0, 0, upper_x, upper_y)
```


```python
print(normalize_rectangle( 0.0, 1.0, 2.0))
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    <ipython-input-8-e34c2165d31c> in <module>
    ----> 1 print(normalize_rectangle( 0.0, 1.0, 2.0))
    

    TypeError: normalize_rectangle() takes 1 positional argument but 3 were given



```python
print(normalize_rectangle((4.0, 2.0, 1.0, 5.0)))
```


    ---------------------------------------------------------------------------

    AssertionError                            Traceback (most recent call last)

    <ipython-input-11-5e28a32bada1> in <module>
    ----> 1 print(normalize_rectangle((4.0, 2.0, 1.0, 5.0)))
    

    <ipython-input-6-0a21467636bc> in normalize_rectangle(rect)
          4     assert len(rect) == 4, 'Rectangles must contin 4 coordinates'
          5     x0, y0, x1, y1 = rect
    ----> 6     assert x0 < x1, 'Invalid X coordinates'
          7     assert y0 < y1, 'Invalid Y coordiates'
          8 


    AssertionError: Invalid X coordinates



```python
print(normalize_rectangle((0.0, 0.0, 1.0, 5.0)))
```

    (0, 0, 0.2, 1.0)



```python
print(normalize_rectangle((0.0, 0.0, 5.0, 1.0)))
```


    ---------------------------------------------------------------------------

    AssertionError                            Traceback (most recent call last)

    <ipython-input-13-1337bef8f4bf> in <module>
    ----> 1 print(normalize_rectangle((0.0, 0.0, 5.0, 1.0)))
    

    <ipython-input-6-0a21467636bc> in normalize_rectangle(rect)
         17 
         18     assert 0 < upper_x <= 1.0, 'Calculated upper X coordinate invalid'
    ---> 19     assert 0 < upper_y <= 1.0, 'Calculated upper Y coordinate invalid'
         20 
         21     return (0, 0, upper_x, upper_y)


    AssertionError: Calculated upper Y coordinate invalid



```python

```

## Transcribing DNA to RNA 

```python
# prompt user to enter the fasta file name 

input_file_name = input("Enter the name of the input fasta file: ") 
```

    Enter the name of the input fasta file:  RARa_sequence.txt



```python
# Open the input fasta file and read the dna sequence 

with open(input_file_name, "r") as input_file: 
    dna_sequence = "" 
    for line in input_file: 
        if line.startswith(">"): 
            continue 
            
        dna_sequence += line.strip() 
        
```


```python
# transcribe the dna to rna 
rna_sequence = "" 
for nucleotide in dna_sequence: 
    if nucleotide == "T": 
        rna_sequence += "U" 
        
    else: 
        rna_sequence += nucleotide
```


```python
# Prompt the user to enter the output file name 

output_file_name = input("Enter the name of the output file:")
```

    Enter the name of the output file: RaRA_sequence2.txt



```python
# Save the RNA sequence to a text file 

with open(output_file_name, "w") as output_file: 
    output_file.write(rna_sequence) 
    print( "The RNA sequence have been saved to {output_file_name} ")
```

    The RNA sequence have been saved to {output_file_name} 



```python
print(rna_sequence)
```

    AUGGCCAGCAACAGCAGCUCCUGCCCGACACCUGGGGGCGGGCACCUCAAUGGGUACCCGGUGCCUCCCUACGCCUUCUUCUUCCCCCCUAUGCUGGGUGGACUCUCCCCGCCAGGCGCUCUGACCACUCUCCAGCACCAGCUUCCAGUUAGUGGAUAUAGCACACCAUCCCCAGCCACCAUUGAGACCCAGAGCAGCAGUUCUGAAGAGAUAGUGCCCAGCCCUCCCUCGCCACCCCCUCUACCCCGCAUCUACAAGCCUUGCUUUGUCUGUCAGGACAAGUCCUCAGGCUACCACUAUGGGGUCAGCGCCUGUGAGGGCUGCAAGGGCUUCUUCCGCCGCAGCAUCCAGAAGAACAUGGUGUACACGUGUCACCGGGACAAGAACUGCAUCAUCAACAAGGUGACCCGGAACCGCUGCCAGUACUGCCGACUGCAGAAGUGCUUUGAAGUGGGCAUGUCCAAGGAGUCUGUGAGAAACGACCGAAACAAGAAGAAGAAGGAGGUGCCCAAGCCCGAGUGCUCUGAGAGCUACACGCUGACGCCGGAGGUGGGGGAGCUCAUUGAGAAGGUGCGCAAAGCGCACCAGGAAACCUUCCCUGCCCUCUGCCAGCUGGGCAAAUACACUACGAACAACAGCUCAGAACAACGUGUCUCUCUGGACAUUGACCUCUGGGACAAGUUCAGUGAACUCUCCACCAAGUGCAUCAUUAAGACUGUGGAGUUCGCCAAGCAGCUGCCCGGCUUCACCACCCUCACCAUCGCCGACCAGAUCACCCUCCUCAAGGCUGCCUGCCUGGACAUCCUGAUCCUGCGGAUCUGCACGCGGUACACGCCCGAGCAGGACACCAUGACCUUCUCGGACGGGCUGACCCUGAACCGGACCCAGAUGCACAACGCUGGCUUCGGCCCCCUCACCGACCUGGUCUUUGCCUUCGCCAACCAGCUGCUGCCCCUGGAGAUGGAUGAUGCGGAGACGGGGCUGCUCAGCGCCAUCUGCCUCAUCUGCGGAGACCGCCAGGACCUGGAGCAGCCGGACCGGGUGGACAUGCUGCAGGAGCCGCUGCUGGAGGCGCUAAAGGUCUACGUGCGGAAGCGGAGGCCCAGCCGCCCCCACAUGUUCCCCAAGAUGCUAAUGAAGAUUACUGACCUGCGAAGCAUCAGCGCCAAGGGGGCUGAGCGGGUGAUCACGCUGAAGAUGGAGAUCCCGGGCUCCAUGCCGCCUCUCAUCCAGGAAAUGUUGGAGAACUCAGAGGGCCUGGACACUCUGAGCGGACAGCCGGGGGGUGGGGGGCGGGACGGGGGUGGCCUGGCCCCCCCGCCAGGCAGCUGUAGCCCCAGCCUCAGCCCCAGCUCCAACAGAAGCAGCCCGGCCACCCACUCCCCGUGA



```python

```


```python

```

## Translating RNA into Protein  

```python
# Promt the user to enter the input RNA file 

input_file_name = input("Enter the name of the input RNA file:")
```

    Enter the name of the input RNA file: RaRA_sequence2.txt



```python
# Open the RNA file and read the RNA sequence 

with open(input_file_name, "r") as input_file: 
    rna_sequence = input_file.read().strip()
```


```python
# Define the codon table 

codon_table = { 
    "UUU": "F", "UUC": "F", "UUA": "L", "UUG": "L",  
    "CUU": "L", "CUC": "L", "CUA": "L", "CUG": "L",
    "AUU": "I", "AUC": "I", "AUA": "I", "AUG": "M", 
    "GUU": "V", "GUC": "V", "GUA": "V", "GUG": "V",
    "UCU": "S", "UCC": "S", "UCA": "S", "UCG": "S",
    "CCU": "P", "CCC": "P", "CCA": "P", "CCG": "P",
    "ACU": "T", "ACC": "T", "ACA": "T", "ACG": "T",
    "GCU": "A", "GCC": "A", "GCA": "A", "GCG": "A", 
    "UAU": "Y", "UAC": "Y", "UAA": "*", "UAG": "*", 
    "CAU": "H", "CAC": "H", "CAA": "Q", "CAG": "Q",
    "AAU": "N", "AAC": "N", "AAA": "K", "AAG": "K",
    "GAU": "D", "GAC": "D", "GAA": "E", "GAG": "E", 
    "UGU": "C", "UGC": "C", "UGA": "*", "UGG": "W", 
    "CGU": "R", "CGC": "R", "CGA": "R", "CGG": "R", 
    "AGU": "S", "AGC": "S", "AGA": "R", "AGG": "R", 
    "GGU": "G", "GGC": "G", "GGA": "G", "GGG": "G", 
}
```


```python
# Translate RNA to protein 

protein_sequence = " " 
for i in range(0, len(rna_sequence), 3): 
    codon = rna_sequence[i:i+3] 
    if len(codon) == 3: 
        amino_acid = codon_table[codon] 
        if amino_acid == "*": 
            break  
        protein_sequence += amino_acid
        
        
```


```python
# Prompt the user to enter the output file name 

output_file_name = input("Enter the name of the output file: ")
```

    Enter the name of the output file:  RARa_Protein_Sequence.txt



```python
# Save the protein sequence to that text file 

with open(output_file_name, "w") as output_file: 
    output_file.write(protein_sequence) 
    print("The protein sequence has been saved to {output_file_name}")
```

    The protein sequence has been saved to {output_file_name}



```python
print(protein_sequence)
```

     MASNSSSCPTPGGGHLNGYPVPPYAFFFPPMLGGLSPPGALTTLQHQLPVSGYSTPSPATIETQSSSSEEIVPSPPSPPPLPRIYKPCFVCQDKSSGYHYGVSACEGCKGFFRRSIQKNMVYTCHRDKNCIINKVTRNRCQYCRLQKCFEVGMSKESVRNDRNKKKKEVPKPECSESYTLTPEVGELIEKVRKAHQETFPALCQLGKYTTNNSSEQRVSLDIDLWDKFSELSTKCIIKTVEFAKQLPGFTTLTIADQITLLKAACLDILILRICTRYTPEQDTMTFSDGLTLNRTQMHNAGFGPLTDLVFAFANQLLPLEMDDAETGLLSAICLICGDRQDLEQPDRVDMLQEPLLEALKVYVRKRRPSRPHMFPKMLMKITDLRSISAKGAERVITLKMEIPGSMPPLIQEMLENSEGLDTLSGQPGGGGRDGGGLAPPPGSCSPSLSPSSNRSSPATHSP



```python

```











