# Población Mundial

#### Primero se cargan las librerias necesarias para realizar el analisis de los datos de la poblacion mundial. 
#### La libreria Numpy se usa para tratar con matrices y operar con ellas.
#### La libreria Pandas, que se construye sobre numpy y nos permite tratar y transformar datos de una forma increible.


```python
import numpy as np
import pandas as pd
import matplotlib.pyplot as  plt
import seaborn as sns
```


```python
df = pd.read_csv('PoblacionMundial.csv', sep = ';', index_col = 'Country Name')
```


```python
df
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
      <th>Country Code</th>
      <th>1960</th>
      <th>1961</th>
      <th>1962</th>
      <th>1963</th>
      <th>1964</th>
      <th>1965</th>
      <th>1966</th>
      <th>1967</th>
      <th>1968</th>
      <th>...</th>
      <th>2013</th>
      <th>2014</th>
      <th>2015</th>
      <th>2016</th>
      <th>2017</th>
      <th>2018</th>
      <th>2019</th>
      <th>2020</th>
      <th>2021</th>
      <th>2022</th>
    </tr>
    <tr>
      <th>Country Name</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Aruba</th>
      <td>ABW</td>
      <td>54608.0</td>
      <td>55811.0</td>
      <td>56682.0</td>
      <td>57475.0</td>
      <td>58178.0</td>
      <td>58782.0</td>
      <td>59291.0</td>
      <td>59522.0</td>
      <td>59471.0</td>
      <td>...</td>
      <td>102880</td>
      <td>103594</td>
      <td>104257</td>
      <td>104874</td>
      <td>105439</td>
      <td>105962</td>
      <td>106442</td>
      <td>106585</td>
      <td>106537</td>
      <td>106445</td>
    </tr>
    <tr>
      <th>Afganistán</th>
      <td>AFG</td>
      <td>8622466.0</td>
      <td>8790140.0</td>
      <td>8969047.0</td>
      <td>9157465.0</td>
      <td>9355514.0</td>
      <td>9565147.0</td>
      <td>9783147.0</td>
      <td>10010030.0</td>
      <td>10247780.0</td>
      <td>...</td>
      <td>31541209</td>
      <td>32716210</td>
      <td>33753499</td>
      <td>34636207</td>
      <td>35643418</td>
      <td>36686784</td>
      <td>37769499</td>
      <td>38972230</td>
      <td>40099462</td>
      <td>41128771</td>
    </tr>
    <tr>
      <th>Angola</th>
      <td>AGO</td>
      <td>5357195.0</td>
      <td>5441333.0</td>
      <td>5521400.0</td>
      <td>5599827.0</td>
      <td>5673199.0</td>
      <td>5736582.0</td>
      <td>5787044.0</td>
      <td>5827503.0</td>
      <td>5868203.0</td>
      <td>...</td>
      <td>26147002</td>
      <td>27128337</td>
      <td>28127721</td>
      <td>29154746</td>
      <td>30208628</td>
      <td>31273533</td>
      <td>32353588</td>
      <td>33428486</td>
      <td>34503774</td>
      <td>35588987</td>
    </tr>
    <tr>
      <th>Albania</th>
      <td>ALB</td>
      <td>1608800.0</td>
      <td>1659800.0</td>
      <td>1711319.0</td>
      <td>1762621.0</td>
      <td>1814135.0</td>
      <td>1864791.0</td>
      <td>1914573.0</td>
      <td>1965598.0</td>
      <td>2022272.0</td>
      <td>...</td>
      <td>2895092</td>
      <td>2889104</td>
      <td>2880703</td>
      <td>2876101</td>
      <td>2873457</td>
      <td>2866376</td>
      <td>2854191</td>
      <td>2837849</td>
      <td>2811666</td>
      <td>2777689</td>
    </tr>
    <tr>
      <th>Andorra</th>
      <td>AND</td>
      <td>9443.0</td>
      <td>10216.0</td>
      <td>11014.0</td>
      <td>11839.0</td>
      <td>12690.0</td>
      <td>13563.0</td>
      <td>14546.0</td>
      <td>15745.0</td>
      <td>17079.0</td>
      <td>...</td>
      <td>71367</td>
      <td>71621</td>
      <td>71746</td>
      <td>72540</td>
      <td>73837</td>
      <td>75013</td>
      <td>76343</td>
      <td>77700</td>
      <td>79034</td>
      <td>79824</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>Kosovo</th>
      <td>XKX</td>
      <td>947000.0</td>
      <td>966000.0</td>
      <td>994000.0</td>
      <td>1022000.0</td>
      <td>1050000.0</td>
      <td>1078000.0</td>
      <td>1106000.0</td>
      <td>1135000.0</td>
      <td>1163000.0</td>
      <td>...</td>
      <td>1818117</td>
      <td>1812771</td>
      <td>1788196</td>
      <td>1777557</td>
      <td>1791003</td>
      <td>1797085</td>
      <td>1788878</td>
      <td>1790133</td>
      <td>1786038</td>
      <td>1761985</td>
    </tr>
    <tr>
      <th>Yemen</th>
      <td>YEM</td>
      <td>5542459.0</td>
      <td>5646668.0</td>
      <td>5753386.0</td>
      <td>5860197.0</td>
      <td>5973803.0</td>
      <td>6097298.0</td>
      <td>6228430.0</td>
      <td>6368014.0</td>
      <td>6515904.0</td>
      <td>...</td>
      <td>26984002</td>
      <td>27753304</td>
      <td>28516545</td>
      <td>29274002</td>
      <td>30034389</td>
      <td>30790513</td>
      <td>31546691</td>
      <td>32284046</td>
      <td>32981641</td>
      <td>33696614</td>
    </tr>
    <tr>
      <th>Sudáfrica</th>
      <td>ZAF</td>
      <td>16520441.0</td>
      <td>16989464.0</td>
      <td>17503133.0</td>
      <td>18042215.0</td>
      <td>18603097.0</td>
      <td>19187194.0</td>
      <td>19789771.0</td>
      <td>20410677.0</td>
      <td>21050540.0</td>
      <td>...</td>
      <td>53873616</td>
      <td>54729551</td>
      <td>55876504</td>
      <td>56422274</td>
      <td>56641209</td>
      <td>57339635</td>
      <td>58087055</td>
      <td>58801927</td>
      <td>59392255</td>
      <td>59893885</td>
    </tr>
    <tr>
      <th>Zambia</th>
      <td>ZMB</td>
      <td>3119430.0</td>
      <td>3219451.0</td>
      <td>3323427.0</td>
      <td>3431381.0</td>
      <td>3542764.0</td>
      <td>3658024.0</td>
      <td>3777680.0</td>
      <td>3901288.0</td>
      <td>4029173.0</td>
      <td>...</td>
      <td>15234976</td>
      <td>15737793</td>
      <td>16248230</td>
      <td>16767761</td>
      <td>17298054</td>
      <td>17835893</td>
      <td>18380477</td>
      <td>18927715</td>
      <td>19473125</td>
      <td>20017675</td>
    </tr>
    <tr>
      <th>Zimbabwe</th>
      <td>ZWE</td>
      <td>3806310.0</td>
      <td>3925952.0</td>
      <td>4049778.0</td>
      <td>4177931.0</td>
      <td>4310332.0</td>
      <td>4447149.0</td>
      <td>4588529.0</td>
      <td>4734694.0</td>
      <td>4886347.0</td>
      <td>...</td>
      <td>13555422</td>
      <td>13855753</td>
      <td>14154937</td>
      <td>14452704</td>
      <td>14751101</td>
      <td>15052184</td>
      <td>15354608</td>
      <td>15669666</td>
      <td>15993524</td>
      <td>16320537</td>
    </tr>
  </tbody>
</table>
<p>263 rows × 64 columns</p>
</div>



Con esta funcion podemos vizualizar la suma total, el promedio entre otra informacion, en resumen algunos datos estadisticos.


```python
df.describe()
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
      <th>1960</th>
      <th>1961</th>
      <th>1962</th>
      <th>1963</th>
      <th>1964</th>
      <th>1965</th>
      <th>1966</th>
      <th>1967</th>
      <th>1968</th>
      <th>1969</th>
      <th>...</th>
      <th>2013</th>
      <th>2014</th>
      <th>2015</th>
      <th>2016</th>
      <th>2017</th>
      <th>2018</th>
      <th>2019</th>
      <th>2020</th>
      <th>2021</th>
      <th>2022</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>2.620000e+02</td>
      <td>2.620000e+02</td>
      <td>2.620000e+02</td>
      <td>2.620000e+02</td>
      <td>2.620000e+02</td>
      <td>2.620000e+02</td>
      <td>2.620000e+02</td>
      <td>2.620000e+02</td>
      <td>2.620000e+02</td>
      <td>2.620000e+02</td>
      <td>...</td>
      <td>2.630000e+02</td>
      <td>2.630000e+02</td>
      <td>2.630000e+02</td>
      <td>2.630000e+02</td>
      <td>2.630000e+02</td>
      <td>2.630000e+02</td>
      <td>2.630000e+02</td>
      <td>2.630000e+02</td>
      <td>2.630000e+02</td>
      <td>2.630000e+02</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>1.172963e+08</td>
      <td>1.188971e+08</td>
      <td>1.210619e+08</td>
      <td>1.237416e+08</td>
      <td>1.264428e+08</td>
      <td>1.291824e+08</td>
      <td>1.320379e+08</td>
      <td>1.348910e+08</td>
      <td>1.378239e+08</td>
      <td>1.408619e+08</td>
      <td>...</td>
      <td>2.913540e+08</td>
      <td>2.951591e+08</td>
      <td>2.989312e+08</td>
      <td>3.027008e+08</td>
      <td>3.064753e+08</td>
      <td>3.101828e+08</td>
      <td>3.138062e+08</td>
      <td>3.173097e+08</td>
      <td>3.204836e+08</td>
      <td>3.233431e+08</td>
    </tr>
    <tr>
      <th>std</th>
      <td>3.709541e+08</td>
      <td>3.755171e+08</td>
      <td>3.822590e+08</td>
      <td>3.909899e+08</td>
      <td>3.997631e+08</td>
      <td>4.086681e+08</td>
      <td>4.180387e+08</td>
      <td>4.273659e+08</td>
      <td>4.369816e+08</td>
      <td>4.469904e+08</td>
      <td>...</td>
      <td>9.219470e+08</td>
      <td>9.333642e+08</td>
      <td>9.446318e+08</td>
      <td>9.558297e+08</td>
      <td>9.670358e+08</td>
      <td>9.779431e+08</td>
      <td>9.885156e+08</td>
      <td>9.986146e+08</td>
      <td>1.007729e+09</td>
      <td>1.015672e+09</td>
    </tr>
    <tr>
      <th>min</th>
      <td>2.646000e+03</td>
      <td>2.888000e+03</td>
      <td>3.171000e+03</td>
      <td>3.481000e+03</td>
      <td>3.811000e+03</td>
      <td>4.161000e+03</td>
      <td>4.531000e+03</td>
      <td>4.930000e+03</td>
      <td>5.354000e+03</td>
      <td>5.646000e+03</td>
      <td>...</td>
      <td>1.069400e+04</td>
      <td>1.089900e+04</td>
      <td>1.087700e+04</td>
      <td>1.085200e+04</td>
      <td>1.082800e+04</td>
      <td>1.086500e+04</td>
      <td>1.095600e+04</td>
      <td>1.106900e+04</td>
      <td>1.120400e+04</td>
      <td>1.131200e+04</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>5.129838e+05</td>
      <td>5.205975e+05</td>
      <td>5.284225e+05</td>
      <td>5.367042e+05</td>
      <td>5.454410e+05</td>
      <td>5.533950e+05</td>
      <td>5.666910e+05</td>
      <td>5.747158e+05</td>
      <td>5.828600e+05</td>
      <td>5.870228e+05</td>
      <td>...</td>
      <td>1.569241e+06</td>
      <td>1.596985e+06</td>
      <td>1.624186e+06</td>
      <td>1.623444e+06</td>
      <td>1.634805e+06</td>
      <td>1.650897e+06</td>
      <td>1.670954e+06</td>
      <td>1.693091e+06</td>
      <td>1.710252e+06</td>
      <td>1.718446e+06</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>3.708088e+06</td>
      <td>3.816540e+06</td>
      <td>3.931214e+06</td>
      <td>4.033994e+06</td>
      <td>4.112910e+06</td>
      <td>4.194930e+06</td>
      <td>4.257383e+06</td>
      <td>4.317222e+06</td>
      <td>4.410692e+06</td>
      <td>4.515734e+06</td>
      <td>...</td>
      <td>9.893082e+06</td>
      <td>9.866468e+06</td>
      <td>9.843028e+06</td>
      <td>9.964656e+06</td>
      <td>1.021538e+07</td>
      <td>1.028382e+07</td>
      <td>1.028626e+07</td>
      <td>1.035344e+07</td>
      <td>1.041581e+07</td>
      <td>1.043286e+07</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>2.419421e+07</td>
      <td>2.489467e+07</td>
      <td>2.559781e+07</td>
      <td>2.630856e+07</td>
      <td>2.700654e+07</td>
      <td>2.771038e+07</td>
      <td>2.842635e+07</td>
      <td>2.913157e+07</td>
      <td>2.984755e+07</td>
      <td>3.056912e+07</td>
      <td>...</td>
      <td>5.226098e+07</td>
      <td>5.290099e+07</td>
      <td>5.420966e+07</td>
      <td>5.541204e+07</td>
      <td>5.645412e+07</td>
      <td>5.771504e+07</td>
      <td>5.890807e+07</td>
      <td>5.912039e+07</td>
      <td>5.926271e+07</td>
      <td>5.941716e+07</td>
    </tr>
    <tr>
      <th>max</th>
      <td>3.031474e+09</td>
      <td>3.072422e+09</td>
      <td>3.126850e+09</td>
      <td>3.193429e+09</td>
      <td>3.260442e+09</td>
      <td>3.328209e+09</td>
      <td>3.398480e+09</td>
      <td>3.468371e+09</td>
      <td>3.540164e+09</td>
      <td>3.614573e+09</td>
      <td>...</td>
      <td>7.229303e+09</td>
      <td>7.317040e+09</td>
      <td>7.403850e+09</td>
      <td>7.490415e+09</td>
      <td>7.576442e+09</td>
      <td>7.660371e+09</td>
      <td>7.741775e+09</td>
      <td>7.820206e+09</td>
      <td>7.888306e+09</td>
      <td>7.950947e+09</td>
    </tr>
  </tbody>
</table>
<p>8 rows × 63 columns</p>
</div>



Con esta funcion se puede visualizar los 5 primeros datos de la matriz u observar la cantidad que sea necesaria.


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
      <th>Country Code</th>
      <th>1960</th>
      <th>1961</th>
      <th>1962</th>
      <th>1963</th>
      <th>1964</th>
      <th>1965</th>
      <th>1966</th>
      <th>1967</th>
      <th>1968</th>
      <th>...</th>
      <th>2013</th>
      <th>2014</th>
      <th>2015</th>
      <th>2016</th>
      <th>2017</th>
      <th>2018</th>
      <th>2019</th>
      <th>2020</th>
      <th>2021</th>
      <th>2022</th>
    </tr>
    <tr>
      <th>Country Name</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Aruba</th>
      <td>ABW</td>
      <td>54608.0</td>
      <td>55811.0</td>
      <td>56682.0</td>
      <td>57475.0</td>
      <td>58178.0</td>
      <td>58782.0</td>
      <td>59291.0</td>
      <td>59522.0</td>
      <td>59471.0</td>
      <td>...</td>
      <td>102880</td>
      <td>103594</td>
      <td>104257</td>
      <td>104874</td>
      <td>105439</td>
      <td>105962</td>
      <td>106442</td>
      <td>106585</td>
      <td>106537</td>
      <td>106445</td>
    </tr>
    <tr>
      <th>Afganistán</th>
      <td>AFG</td>
      <td>8622466.0</td>
      <td>8790140.0</td>
      <td>8969047.0</td>
      <td>9157465.0</td>
      <td>9355514.0</td>
      <td>9565147.0</td>
      <td>9783147.0</td>
      <td>10010030.0</td>
      <td>10247780.0</td>
      <td>...</td>
      <td>31541209</td>
      <td>32716210</td>
      <td>33753499</td>
      <td>34636207</td>
      <td>35643418</td>
      <td>36686784</td>
      <td>37769499</td>
      <td>38972230</td>
      <td>40099462</td>
      <td>41128771</td>
    </tr>
    <tr>
      <th>Angola</th>
      <td>AGO</td>
      <td>5357195.0</td>
      <td>5441333.0</td>
      <td>5521400.0</td>
      <td>5599827.0</td>
      <td>5673199.0</td>
      <td>5736582.0</td>
      <td>5787044.0</td>
      <td>5827503.0</td>
      <td>5868203.0</td>
      <td>...</td>
      <td>26147002</td>
      <td>27128337</td>
      <td>28127721</td>
      <td>29154746</td>
      <td>30208628</td>
      <td>31273533</td>
      <td>32353588</td>
      <td>33428486</td>
      <td>34503774</td>
      <td>35588987</td>
    </tr>
    <tr>
      <th>Albania</th>
      <td>ALB</td>
      <td>1608800.0</td>
      <td>1659800.0</td>
      <td>1711319.0</td>
      <td>1762621.0</td>
      <td>1814135.0</td>
      <td>1864791.0</td>
      <td>1914573.0</td>
      <td>1965598.0</td>
      <td>2022272.0</td>
      <td>...</td>
      <td>2895092</td>
      <td>2889104</td>
      <td>2880703</td>
      <td>2876101</td>
      <td>2873457</td>
      <td>2866376</td>
      <td>2854191</td>
      <td>2837849</td>
      <td>2811666</td>
      <td>2777689</td>
    </tr>
    <tr>
      <th>Andorra</th>
      <td>AND</td>
      <td>9443.0</td>
      <td>10216.0</td>
      <td>11014.0</td>
      <td>11839.0</td>
      <td>12690.0</td>
      <td>13563.0</td>
      <td>14546.0</td>
      <td>15745.0</td>
      <td>17079.0</td>
      <td>...</td>
      <td>71367</td>
      <td>71621</td>
      <td>71746</td>
      <td>72540</td>
      <td>73837</td>
      <td>75013</td>
      <td>76343</td>
      <td>77700</td>
      <td>79034</td>
      <td>79824</td>
    </tr>
  </tbody>
</table>
<p>5 rows × 64 columns</p>
</div>




```python
df.head(7)
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
      <th>Country Code</th>
      <th>1960</th>
      <th>1961</th>
      <th>1962</th>
      <th>1963</th>
      <th>1964</th>
      <th>1965</th>
      <th>1966</th>
      <th>1967</th>
      <th>1968</th>
      <th>...</th>
      <th>2013</th>
      <th>2014</th>
      <th>2015</th>
      <th>2016</th>
      <th>2017</th>
      <th>2018</th>
      <th>2019</th>
      <th>2020</th>
      <th>2021</th>
      <th>2022</th>
    </tr>
    <tr>
      <th>Country Name</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Aruba</th>
      <td>ABW</td>
      <td>54608.0</td>
      <td>55811.0</td>
      <td>56682.0</td>
      <td>57475.0</td>
      <td>58178.0</td>
      <td>58782.0</td>
      <td>59291.0</td>
      <td>59522.0</td>
      <td>59471.0</td>
      <td>...</td>
      <td>102880</td>
      <td>103594</td>
      <td>104257</td>
      <td>104874</td>
      <td>105439</td>
      <td>105962</td>
      <td>106442</td>
      <td>106585</td>
      <td>106537</td>
      <td>106445</td>
    </tr>
    <tr>
      <th>Afganistán</th>
      <td>AFG</td>
      <td>8622466.0</td>
      <td>8790140.0</td>
      <td>8969047.0</td>
      <td>9157465.0</td>
      <td>9355514.0</td>
      <td>9565147.0</td>
      <td>9783147.0</td>
      <td>10010030.0</td>
      <td>10247780.0</td>
      <td>...</td>
      <td>31541209</td>
      <td>32716210</td>
      <td>33753499</td>
      <td>34636207</td>
      <td>35643418</td>
      <td>36686784</td>
      <td>37769499</td>
      <td>38972230</td>
      <td>40099462</td>
      <td>41128771</td>
    </tr>
    <tr>
      <th>Angola</th>
      <td>AGO</td>
      <td>5357195.0</td>
      <td>5441333.0</td>
      <td>5521400.0</td>
      <td>5599827.0</td>
      <td>5673199.0</td>
      <td>5736582.0</td>
      <td>5787044.0</td>
      <td>5827503.0</td>
      <td>5868203.0</td>
      <td>...</td>
      <td>26147002</td>
      <td>27128337</td>
      <td>28127721</td>
      <td>29154746</td>
      <td>30208628</td>
      <td>31273533</td>
      <td>32353588</td>
      <td>33428486</td>
      <td>34503774</td>
      <td>35588987</td>
    </tr>
    <tr>
      <th>Albania</th>
      <td>ALB</td>
      <td>1608800.0</td>
      <td>1659800.0</td>
      <td>1711319.0</td>
      <td>1762621.0</td>
      <td>1814135.0</td>
      <td>1864791.0</td>
      <td>1914573.0</td>
      <td>1965598.0</td>
      <td>2022272.0</td>
      <td>...</td>
      <td>2895092</td>
      <td>2889104</td>
      <td>2880703</td>
      <td>2876101</td>
      <td>2873457</td>
      <td>2866376</td>
      <td>2854191</td>
      <td>2837849</td>
      <td>2811666</td>
      <td>2777689</td>
    </tr>
    <tr>
      <th>Andorra</th>
      <td>AND</td>
      <td>9443.0</td>
      <td>10216.0</td>
      <td>11014.0</td>
      <td>11839.0</td>
      <td>12690.0</td>
      <td>13563.0</td>
      <td>14546.0</td>
      <td>15745.0</td>
      <td>17079.0</td>
      <td>...</td>
      <td>71367</td>
      <td>71621</td>
      <td>71746</td>
      <td>72540</td>
      <td>73837</td>
      <td>75013</td>
      <td>76343</td>
      <td>77700</td>
      <td>79034</td>
      <td>79824</td>
    </tr>
    <tr>
      <th>El mundo árabe</th>
      <td>ARB</td>
      <td>93359407.0</td>
      <td>95760348.0</td>
      <td>98268683.0</td>
      <td>100892507.0</td>
      <td>103618568.0</td>
      <td>106444103.0</td>
      <td>109394536.0</td>
      <td>112499764.0</td>
      <td>115729597.0</td>
      <td>...</td>
      <td>389131555</td>
      <td>397922915</td>
      <td>406501999</td>
      <td>415077960</td>
      <td>423664839</td>
      <td>432545676</td>
      <td>441467739</td>
      <td>449228296</td>
      <td>456520777</td>
      <td>464684914</td>
    </tr>
    <tr>
      <th>Emiratos Árabes Unidos</th>
      <td>ARE</td>
      <td>133426.0</td>
      <td>140984.0</td>
      <td>148877.0</td>
      <td>157006.0</td>
      <td>165305.0</td>
      <td>173797.0</td>
      <td>182509.0</td>
      <td>191404.0</td>
      <td>213582.0</td>
      <td>...</td>
      <td>8751847</td>
      <td>8835951</td>
      <td>8916899</td>
      <td>8994263</td>
      <td>9068296</td>
      <td>9140169</td>
      <td>9211657</td>
      <td>9287289</td>
      <td>9365145</td>
      <td>9441129</td>
    </tr>
  </tbody>
</table>
<p>7 rows × 64 columns</p>
</div>



En pandas los dataframes estan formados por Series. Las Series no son mas que arrays de un mismo tipo. Los dataframes pueden estar formados de Series de distintos tipos y podemos ver estos tipos con .dtypes


```python
df.dtypes
```




    Country Code     object
    1960            float64
    1961            float64
    1962            float64
    1963            float64
                     ...   
    2018              int64
    2019              int64
    2020              int64
    2021              int64
    2022              int64
    Length: 64, dtype: object



 Con esta funcion se puede visualiza los datos por columna, pero los primeros datos.


```python
df['Country Code'].head()
```




    Country Name
    Aruba         ABW
    Afganistán    AFG
    Angola        AGO
    Albania       ALB
    Andorra       AND
    Name: Country Code, dtype: object




```python
sns.distplot(df('PoblacionMundial'))
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    Cell In[105], line 1
    ----> 1 sns.distplot(df('PoblacionMundial'))
    

    TypeError: 'DataFrame' object is not callable



```python
# De esta manera se puede vizualizar las columnas.
df.columns
```




    Index(['Country Code', '1960', '1961', '1962', '1963', '1964', '1965', '1966',
           '1967', '1968', '1969', '1970', '1971', '1972', '1973', '1974', '1975',
           '1976', '1977', '1978', '1979', '1980', '1981', '1982', '1983', '1984',
           '1985', '1986', '1987', '1988', '1989', '1990', '1991', '1992', '1993',
           '1994', '1995', '1996', '1997', '1998', '1999', '2000', '2001', '2002',
           '2003', '2004', '2005', '2006', '2007', '2008', '2009', '2010', '2011',
           '2012', '2013', '2014', '2015', '2016', '2017', '2018', '2019', '2020',
           '2021', '2022'],
          dtype='object')




```python
df['1960'].describe()
```




    count    2.620000e+02
    mean     1.172963e+08
    std      3.709541e+08
    min      2.646000e+03
    25%      5.129838e+05
    50%      3.708088e+06
    75%      2.419421e+07
    max      3.031474e+09
    Name: 1960, dtype: float64




```python
# Eliminamos la segunda columna el cual menciona las abreviaturas de los paises.

df1 = df.drop('Country Code', axis = 1)
```


```python
df1
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
      <th>1960</th>
      <th>1961</th>
      <th>1962</th>
      <th>1963</th>
      <th>1964</th>
      <th>1965</th>
      <th>1966</th>
      <th>1967</th>
      <th>1968</th>
      <th>1969</th>
      <th>...</th>
      <th>2013</th>
      <th>2014</th>
      <th>2015</th>
      <th>2016</th>
      <th>2017</th>
      <th>2018</th>
      <th>2019</th>
      <th>2020</th>
      <th>2021</th>
      <th>2022</th>
    </tr>
    <tr>
      <th>Country Name</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Aruba</th>
      <td>54608.0</td>
      <td>55811.0</td>
      <td>56682.0</td>
      <td>57475.0</td>
      <td>58178.0</td>
      <td>58782.0</td>
      <td>59291.0</td>
      <td>59522.0</td>
      <td>59471.0</td>
      <td>59330.0</td>
      <td>...</td>
      <td>102880</td>
      <td>103594</td>
      <td>104257</td>
      <td>104874</td>
      <td>105439</td>
      <td>105962</td>
      <td>106442</td>
      <td>106585</td>
      <td>106537</td>
      <td>106445</td>
    </tr>
    <tr>
      <th>Afganistán</th>
      <td>8622466.0</td>
      <td>8790140.0</td>
      <td>8969047.0</td>
      <td>9157465.0</td>
      <td>9355514.0</td>
      <td>9565147.0</td>
      <td>9783147.0</td>
      <td>10010030.0</td>
      <td>10247780.0</td>
      <td>10494489.0</td>
      <td>...</td>
      <td>31541209</td>
      <td>32716210</td>
      <td>33753499</td>
      <td>34636207</td>
      <td>35643418</td>
      <td>36686784</td>
      <td>37769499</td>
      <td>38972230</td>
      <td>40099462</td>
      <td>41128771</td>
    </tr>
    <tr>
      <th>Angola</th>
      <td>5357195.0</td>
      <td>5441333.0</td>
      <td>5521400.0</td>
      <td>5599827.0</td>
      <td>5673199.0</td>
      <td>5736582.0</td>
      <td>5787044.0</td>
      <td>5827503.0</td>
      <td>5868203.0</td>
      <td>5928386.0</td>
      <td>...</td>
      <td>26147002</td>
      <td>27128337</td>
      <td>28127721</td>
      <td>29154746</td>
      <td>30208628</td>
      <td>31273533</td>
      <td>32353588</td>
      <td>33428486</td>
      <td>34503774</td>
      <td>35588987</td>
    </tr>
    <tr>
      <th>Albania</th>
      <td>1608800.0</td>
      <td>1659800.0</td>
      <td>1711319.0</td>
      <td>1762621.0</td>
      <td>1814135.0</td>
      <td>1864791.0</td>
      <td>1914573.0</td>
      <td>1965598.0</td>
      <td>2022272.0</td>
      <td>2081695.0</td>
      <td>...</td>
      <td>2895092</td>
      <td>2889104</td>
      <td>2880703</td>
      <td>2876101</td>
      <td>2873457</td>
      <td>2866376</td>
      <td>2854191</td>
      <td>2837849</td>
      <td>2811666</td>
      <td>2777689</td>
    </tr>
    <tr>
      <th>Andorra</th>
      <td>9443.0</td>
      <td>10216.0</td>
      <td>11014.0</td>
      <td>11839.0</td>
      <td>12690.0</td>
      <td>13563.0</td>
      <td>14546.0</td>
      <td>15745.0</td>
      <td>17079.0</td>
      <td>18449.0</td>
      <td>...</td>
      <td>71367</td>
      <td>71621</td>
      <td>71746</td>
      <td>72540</td>
      <td>73837</td>
      <td>75013</td>
      <td>76343</td>
      <td>77700</td>
      <td>79034</td>
      <td>79824</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>Kosovo</th>
      <td>947000.0</td>
      <td>966000.0</td>
      <td>994000.0</td>
      <td>1022000.0</td>
      <td>1050000.0</td>
      <td>1078000.0</td>
      <td>1106000.0</td>
      <td>1135000.0</td>
      <td>1163000.0</td>
      <td>1191000.0</td>
      <td>...</td>
      <td>1818117</td>
      <td>1812771</td>
      <td>1788196</td>
      <td>1777557</td>
      <td>1791003</td>
      <td>1797085</td>
      <td>1788878</td>
      <td>1790133</td>
      <td>1786038</td>
      <td>1761985</td>
    </tr>
    <tr>
      <th>Yemen</th>
      <td>5542459.0</td>
      <td>5646668.0</td>
      <td>5753386.0</td>
      <td>5860197.0</td>
      <td>5973803.0</td>
      <td>6097298.0</td>
      <td>6228430.0</td>
      <td>6368014.0</td>
      <td>6515904.0</td>
      <td>6673981.0</td>
      <td>...</td>
      <td>26984002</td>
      <td>27753304</td>
      <td>28516545</td>
      <td>29274002</td>
      <td>30034389</td>
      <td>30790513</td>
      <td>31546691</td>
      <td>32284046</td>
      <td>32981641</td>
      <td>33696614</td>
    </tr>
    <tr>
      <th>Sudáfrica</th>
      <td>16520441.0</td>
      <td>16989464.0</td>
      <td>17503133.0</td>
      <td>18042215.0</td>
      <td>18603097.0</td>
      <td>19187194.0</td>
      <td>19789771.0</td>
      <td>20410677.0</td>
      <td>21050540.0</td>
      <td>21704214.0</td>
      <td>...</td>
      <td>53873616</td>
      <td>54729551</td>
      <td>55876504</td>
      <td>56422274</td>
      <td>56641209</td>
      <td>57339635</td>
      <td>58087055</td>
      <td>58801927</td>
      <td>59392255</td>
      <td>59893885</td>
    </tr>
    <tr>
      <th>Zambia</th>
      <td>3119430.0</td>
      <td>3219451.0</td>
      <td>3323427.0</td>
      <td>3431381.0</td>
      <td>3542764.0</td>
      <td>3658024.0</td>
      <td>3777680.0</td>
      <td>3901288.0</td>
      <td>4029173.0</td>
      <td>4159007.0</td>
      <td>...</td>
      <td>15234976</td>
      <td>15737793</td>
      <td>16248230</td>
      <td>16767761</td>
      <td>17298054</td>
      <td>17835893</td>
      <td>18380477</td>
      <td>18927715</td>
      <td>19473125</td>
      <td>20017675</td>
    </tr>
    <tr>
      <th>Zimbabwe</th>
      <td>3806310.0</td>
      <td>3925952.0</td>
      <td>4049778.0</td>
      <td>4177931.0</td>
      <td>4310332.0</td>
      <td>4447149.0</td>
      <td>4588529.0</td>
      <td>4734694.0</td>
      <td>4886347.0</td>
      <td>5044163.0</td>
      <td>...</td>
      <td>13555422</td>
      <td>13855753</td>
      <td>14154937</td>
      <td>14452704</td>
      <td>14751101</td>
      <td>15052184</td>
      <td>15354608</td>
      <td>15669666</td>
      <td>15993524</td>
      <td>16320537</td>
    </tr>
  </tbody>
</table>
<p>263 rows × 63 columns</p>
</div>




```python
Aruba = df1[0:1]
Aruba
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
      <th>1960</th>
      <th>1961</th>
      <th>1962</th>
      <th>1963</th>
      <th>1964</th>
      <th>1965</th>
      <th>1966</th>
      <th>1967</th>
      <th>1968</th>
      <th>1969</th>
      <th>...</th>
      <th>2013</th>
      <th>2014</th>
      <th>2015</th>
      <th>2016</th>
      <th>2017</th>
      <th>2018</th>
      <th>2019</th>
      <th>2020</th>
      <th>2021</th>
      <th>2022</th>
    </tr>
    <tr>
      <th>Country Name</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Aruba</th>
      <td>54608.0</td>
      <td>55811.0</td>
      <td>56682.0</td>
      <td>57475.0</td>
      <td>58178.0</td>
      <td>58782.0</td>
      <td>59291.0</td>
      <td>59522.0</td>
      <td>59471.0</td>
      <td>59330.0</td>
      <td>...</td>
      <td>102880</td>
      <td>103594</td>
      <td>104257</td>
      <td>104874</td>
      <td>105439</td>
      <td>105962</td>
      <td>106442</td>
      <td>106585</td>
      <td>106537</td>
      <td>106445</td>
    </tr>
  </tbody>
</table>
<p>1 rows × 63 columns</p>
</div>




```python

```


```python

```


```python

```


```python

```


```python

```


```python

```


```python

```
