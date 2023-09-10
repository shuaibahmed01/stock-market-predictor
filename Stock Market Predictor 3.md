```python
import yfinance as yf
```


```python
sp500 = yf.Ticker("^GSPC")
```


```python
sp500 = sp500.history(period="max")
```


```python
sp500
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
      <th>Open</th>
      <th>High</th>
      <th>Low</th>
      <th>Close</th>
      <th>Volume</th>
      <th>Dividends</th>
      <th>Stock Splits</th>
    </tr>
    <tr>
      <th>Date</th>
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
      <th>1927-12-30 00:00:00-05:00</th>
      <td>17.660000</td>
      <td>17.660000</td>
      <td>17.660000</td>
      <td>17.660000</td>
      <td>0</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>1928-01-03 00:00:00-05:00</th>
      <td>17.760000</td>
      <td>17.760000</td>
      <td>17.760000</td>
      <td>17.760000</td>
      <td>0</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>1928-01-04 00:00:00-05:00</th>
      <td>17.719999</td>
      <td>17.719999</td>
      <td>17.719999</td>
      <td>17.719999</td>
      <td>0</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>1928-01-05 00:00:00-05:00</th>
      <td>17.549999</td>
      <td>17.549999</td>
      <td>17.549999</td>
      <td>17.549999</td>
      <td>0</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>1928-01-06 00:00:00-05:00</th>
      <td>17.660000</td>
      <td>17.660000</td>
      <td>17.660000</td>
      <td>17.660000</td>
      <td>0</td>
      <td>0.0</td>
      <td>0.0</td>
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
    </tr>
    <tr>
      <th>2023-09-01 00:00:00-04:00</th>
      <td>4530.600098</td>
      <td>4541.250000</td>
      <td>4501.350098</td>
      <td>4515.770020</td>
      <td>3246260000</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>2023-09-05 00:00:00-04:00</th>
      <td>4510.060059</td>
      <td>4514.290039</td>
      <td>4496.009766</td>
      <td>4496.830078</td>
      <td>3526250000</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>2023-09-06 00:00:00-04:00</th>
      <td>4490.350098</td>
      <td>4490.350098</td>
      <td>4442.379883</td>
      <td>4465.479980</td>
      <td>3418850000</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>2023-09-07 00:00:00-04:00</th>
      <td>4434.549805</td>
      <td>4457.810059</td>
      <td>4430.459961</td>
      <td>4451.140137</td>
      <td>3763760000</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>2023-09-08 00:00:00-04:00</th>
      <td>4451.299805</td>
      <td>4473.529785</td>
      <td>4448.379883</td>
      <td>4457.490234</td>
      <td>3259290000</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
  </tbody>
</table>
<p>24037 rows × 7 columns</p>
</div>




```python
sp500.index
```




    DatetimeIndex(['1927-12-30 00:00:00-05:00', '1928-01-03 00:00:00-05:00',
                   '1928-01-04 00:00:00-05:00', '1928-01-05 00:00:00-05:00',
                   '1928-01-06 00:00:00-05:00', '1928-01-09 00:00:00-05:00',
                   '1928-01-10 00:00:00-05:00', '1928-01-11 00:00:00-05:00',
                   '1928-01-12 00:00:00-05:00', '1928-01-13 00:00:00-05:00',
                   ...
                   '2023-08-25 00:00:00-04:00', '2023-08-28 00:00:00-04:00',
                   '2023-08-29 00:00:00-04:00', '2023-08-30 00:00:00-04:00',
                   '2023-08-31 00:00:00-04:00', '2023-09-01 00:00:00-04:00',
                   '2023-09-05 00:00:00-04:00', '2023-09-06 00:00:00-04:00',
                   '2023-09-07 00:00:00-04:00', '2023-09-08 00:00:00-04:00'],
                  dtype='datetime64[ns, America/New_York]', name='Date', length=24037, freq=None)




```python
sp500.plot.line(y="Close", use_index=True)
```




    <Axes: xlabel='Date'>




    
![png](output_5_1.png)
    



```python
del sp500["Dividends"]
del sp500["Stock Splits"]
```


```python
sp500
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
      <th>Open</th>
      <th>High</th>
      <th>Low</th>
      <th>Close</th>
      <th>Volume</th>
    </tr>
    <tr>
      <th>Date</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1927-12-30 00:00:00-05:00</th>
      <td>17.660000</td>
      <td>17.660000</td>
      <td>17.660000</td>
      <td>17.660000</td>
      <td>0</td>
    </tr>
    <tr>
      <th>1928-01-03 00:00:00-05:00</th>
      <td>17.760000</td>
      <td>17.760000</td>
      <td>17.760000</td>
      <td>17.760000</td>
      <td>0</td>
    </tr>
    <tr>
      <th>1928-01-04 00:00:00-05:00</th>
      <td>17.719999</td>
      <td>17.719999</td>
      <td>17.719999</td>
      <td>17.719999</td>
      <td>0</td>
    </tr>
    <tr>
      <th>1928-01-05 00:00:00-05:00</th>
      <td>17.549999</td>
      <td>17.549999</td>
      <td>17.549999</td>
      <td>17.549999</td>
      <td>0</td>
    </tr>
    <tr>
      <th>1928-01-06 00:00:00-05:00</th>
      <td>17.660000</td>
      <td>17.660000</td>
      <td>17.660000</td>
      <td>17.660000</td>
      <td>0</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>2023-09-01 00:00:00-04:00</th>
      <td>4530.600098</td>
      <td>4541.250000</td>
      <td>4501.350098</td>
      <td>4515.770020</td>
      <td>3246260000</td>
    </tr>
    <tr>
      <th>2023-09-05 00:00:00-04:00</th>
      <td>4510.060059</td>
      <td>4514.290039</td>
      <td>4496.009766</td>
      <td>4496.830078</td>
      <td>3526250000</td>
    </tr>
    <tr>
      <th>2023-09-06 00:00:00-04:00</th>
      <td>4490.350098</td>
      <td>4490.350098</td>
      <td>4442.379883</td>
      <td>4465.479980</td>
      <td>3418850000</td>
    </tr>
    <tr>
      <th>2023-09-07 00:00:00-04:00</th>
      <td>4434.549805</td>
      <td>4457.810059</td>
      <td>4430.459961</td>
      <td>4451.140137</td>
      <td>3763760000</td>
    </tr>
    <tr>
      <th>2023-09-08 00:00:00-04:00</th>
      <td>4451.299805</td>
      <td>4473.529785</td>
      <td>4448.379883</td>
      <td>4457.490234</td>
      <td>3259290000</td>
    </tr>
  </tbody>
</table>
<p>24037 rows × 5 columns</p>
</div>




```python
sp500["Tomorrow"] = sp500["Close"].shift(-1)
```


```python
sp500
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
      <th>Open</th>
      <th>High</th>
      <th>Low</th>
      <th>Close</th>
      <th>Volume</th>
      <th>Tomorrow</th>
    </tr>
    <tr>
      <th>Date</th>
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
      <th>1927-12-30 00:00:00-05:00</th>
      <td>17.660000</td>
      <td>17.660000</td>
      <td>17.660000</td>
      <td>17.660000</td>
      <td>0</td>
      <td>17.760000</td>
    </tr>
    <tr>
      <th>1928-01-03 00:00:00-05:00</th>
      <td>17.760000</td>
      <td>17.760000</td>
      <td>17.760000</td>
      <td>17.760000</td>
      <td>0</td>
      <td>17.719999</td>
    </tr>
    <tr>
      <th>1928-01-04 00:00:00-05:00</th>
      <td>17.719999</td>
      <td>17.719999</td>
      <td>17.719999</td>
      <td>17.719999</td>
      <td>0</td>
      <td>17.549999</td>
    </tr>
    <tr>
      <th>1928-01-05 00:00:00-05:00</th>
      <td>17.549999</td>
      <td>17.549999</td>
      <td>17.549999</td>
      <td>17.549999</td>
      <td>0</td>
      <td>17.660000</td>
    </tr>
    <tr>
      <th>1928-01-06 00:00:00-05:00</th>
      <td>17.660000</td>
      <td>17.660000</td>
      <td>17.660000</td>
      <td>17.660000</td>
      <td>0</td>
      <td>17.500000</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>2023-09-01 00:00:00-04:00</th>
      <td>4530.600098</td>
      <td>4541.250000</td>
      <td>4501.350098</td>
      <td>4515.770020</td>
      <td>3246260000</td>
      <td>4496.830078</td>
    </tr>
    <tr>
      <th>2023-09-05 00:00:00-04:00</th>
      <td>4510.060059</td>
      <td>4514.290039</td>
      <td>4496.009766</td>
      <td>4496.830078</td>
      <td>3526250000</td>
      <td>4465.479980</td>
    </tr>
    <tr>
      <th>2023-09-06 00:00:00-04:00</th>
      <td>4490.350098</td>
      <td>4490.350098</td>
      <td>4442.379883</td>
      <td>4465.479980</td>
      <td>3418850000</td>
      <td>4451.140137</td>
    </tr>
    <tr>
      <th>2023-09-07 00:00:00-04:00</th>
      <td>4434.549805</td>
      <td>4457.810059</td>
      <td>4430.459961</td>
      <td>4451.140137</td>
      <td>3763760000</td>
      <td>4457.490234</td>
    </tr>
    <tr>
      <th>2023-09-08 00:00:00-04:00</th>
      <td>4451.299805</td>
      <td>4473.529785</td>
      <td>4448.379883</td>
      <td>4457.490234</td>
      <td>3259290000</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
<p>24037 rows × 6 columns</p>
</div>




```python
sp500["Target"] = (sp500["Tomorrow"] > sp500["Close"]).astype(int)
```


```python
sp500
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
      <th>Open</th>
      <th>High</th>
      <th>Low</th>
      <th>Close</th>
      <th>Volume</th>
      <th>Tomorrow</th>
      <th>Target</th>
    </tr>
    <tr>
      <th>Date</th>
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
      <th>1927-12-30 00:00:00-05:00</th>
      <td>17.660000</td>
      <td>17.660000</td>
      <td>17.660000</td>
      <td>17.660000</td>
      <td>0</td>
      <td>17.760000</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1928-01-03 00:00:00-05:00</th>
      <td>17.760000</td>
      <td>17.760000</td>
      <td>17.760000</td>
      <td>17.760000</td>
      <td>0</td>
      <td>17.719999</td>
      <td>0</td>
    </tr>
    <tr>
      <th>1928-01-04 00:00:00-05:00</th>
      <td>17.719999</td>
      <td>17.719999</td>
      <td>17.719999</td>
      <td>17.719999</td>
      <td>0</td>
      <td>17.549999</td>
      <td>0</td>
    </tr>
    <tr>
      <th>1928-01-05 00:00:00-05:00</th>
      <td>17.549999</td>
      <td>17.549999</td>
      <td>17.549999</td>
      <td>17.549999</td>
      <td>0</td>
      <td>17.660000</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1928-01-06 00:00:00-05:00</th>
      <td>17.660000</td>
      <td>17.660000</td>
      <td>17.660000</td>
      <td>17.660000</td>
      <td>0</td>
      <td>17.500000</td>
      <td>0</td>
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
    </tr>
    <tr>
      <th>2023-09-01 00:00:00-04:00</th>
      <td>4530.600098</td>
      <td>4541.250000</td>
      <td>4501.350098</td>
      <td>4515.770020</td>
      <td>3246260000</td>
      <td>4496.830078</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2023-09-05 00:00:00-04:00</th>
      <td>4510.060059</td>
      <td>4514.290039</td>
      <td>4496.009766</td>
      <td>4496.830078</td>
      <td>3526250000</td>
      <td>4465.479980</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2023-09-06 00:00:00-04:00</th>
      <td>4490.350098</td>
      <td>4490.350098</td>
      <td>4442.379883</td>
      <td>4465.479980</td>
      <td>3418850000</td>
      <td>4451.140137</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2023-09-07 00:00:00-04:00</th>
      <td>4434.549805</td>
      <td>4457.810059</td>
      <td>4430.459961</td>
      <td>4451.140137</td>
      <td>3763760000</td>
      <td>4457.490234</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2023-09-08 00:00:00-04:00</th>
      <td>4451.299805</td>
      <td>4473.529785</td>
      <td>4448.379883</td>
      <td>4457.490234</td>
      <td>3259290000</td>
      <td>NaN</td>
      <td>0</td>
    </tr>
  </tbody>
</table>
<p>24037 rows × 7 columns</p>
</div>




```python
sp500 = sp500.loc["1990-01-01":].copy()
```


```python
sp500
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
      <th>Open</th>
      <th>High</th>
      <th>Low</th>
      <th>Close</th>
      <th>Volume</th>
      <th>Tomorrow</th>
      <th>Target</th>
    </tr>
    <tr>
      <th>Date</th>
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
      <th>1990-01-02 00:00:00-05:00</th>
      <td>353.399994</td>
      <td>359.690002</td>
      <td>351.980011</td>
      <td>359.690002</td>
      <td>162070000</td>
      <td>358.760010</td>
      <td>0</td>
    </tr>
    <tr>
      <th>1990-01-03 00:00:00-05:00</th>
      <td>359.690002</td>
      <td>360.589996</td>
      <td>357.890015</td>
      <td>358.760010</td>
      <td>192330000</td>
      <td>355.670013</td>
      <td>0</td>
    </tr>
    <tr>
      <th>1990-01-04 00:00:00-05:00</th>
      <td>358.760010</td>
      <td>358.760010</td>
      <td>352.890015</td>
      <td>355.670013</td>
      <td>177000000</td>
      <td>352.200012</td>
      <td>0</td>
    </tr>
    <tr>
      <th>1990-01-05 00:00:00-05:00</th>
      <td>355.670013</td>
      <td>355.670013</td>
      <td>351.350006</td>
      <td>352.200012</td>
      <td>158530000</td>
      <td>353.790009</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1990-01-08 00:00:00-05:00</th>
      <td>352.200012</td>
      <td>354.239990</td>
      <td>350.540009</td>
      <td>353.790009</td>
      <td>140110000</td>
      <td>349.619995</td>
      <td>0</td>
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
    </tr>
    <tr>
      <th>2023-09-01 00:00:00-04:00</th>
      <td>4530.600098</td>
      <td>4541.250000</td>
      <td>4501.350098</td>
      <td>4515.770020</td>
      <td>3246260000</td>
      <td>4496.830078</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2023-09-05 00:00:00-04:00</th>
      <td>4510.060059</td>
      <td>4514.290039</td>
      <td>4496.009766</td>
      <td>4496.830078</td>
      <td>3526250000</td>
      <td>4465.479980</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2023-09-06 00:00:00-04:00</th>
      <td>4490.350098</td>
      <td>4490.350098</td>
      <td>4442.379883</td>
      <td>4465.479980</td>
      <td>3418850000</td>
      <td>4451.140137</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2023-09-07 00:00:00-04:00</th>
      <td>4434.549805</td>
      <td>4457.810059</td>
      <td>4430.459961</td>
      <td>4451.140137</td>
      <td>3763760000</td>
      <td>4457.490234</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2023-09-08 00:00:00-04:00</th>
      <td>4451.299805</td>
      <td>4473.529785</td>
      <td>4448.379883</td>
      <td>4457.490234</td>
      <td>3259290000</td>
      <td>NaN</td>
      <td>0</td>
    </tr>
  </tbody>
</table>
<p>8487 rows × 7 columns</p>
</div>




```python
from sklearn.ensemble import RandomForestClassifier

model = RandomForestClassifier(n_estimators=100, min_samples_split=100, random_state=1)

train = sp500.iloc[:-100]
test = sp500.iloc[-100:]

predictors = ["Close", "Volume", "Open", "High", "Low"]
model.fit(train[predictors],train["Target"])
```




<style>#sk-container-id-1 {color: black;}#sk-container-id-1 pre{padding: 0;}#sk-container-id-1 div.sk-toggleable {background-color: white;}#sk-container-id-1 label.sk-toggleable__label {cursor: pointer;display: block;width: 100%;margin-bottom: 0;padding: 0.3em;box-sizing: border-box;text-align: center;}#sk-container-id-1 label.sk-toggleable__label-arrow:before {content: "▸";float: left;margin-right: 0.25em;color: #696969;}#sk-container-id-1 label.sk-toggleable__label-arrow:hover:before {color: black;}#sk-container-id-1 div.sk-estimator:hover label.sk-toggleable__label-arrow:before {color: black;}#sk-container-id-1 div.sk-toggleable__content {max-height: 0;max-width: 0;overflow: hidden;text-align: left;background-color: #f0f8ff;}#sk-container-id-1 div.sk-toggleable__content pre {margin: 0.2em;color: black;border-radius: 0.25em;background-color: #f0f8ff;}#sk-container-id-1 input.sk-toggleable__control:checked~div.sk-toggleable__content {max-height: 200px;max-width: 100%;overflow: auto;}#sk-container-id-1 input.sk-toggleable__control:checked~label.sk-toggleable__label-arrow:before {content: "▾";}#sk-container-id-1 div.sk-estimator input.sk-toggleable__control:checked~label.sk-toggleable__label {background-color: #d4ebff;}#sk-container-id-1 div.sk-label input.sk-toggleable__control:checked~label.sk-toggleable__label {background-color: #d4ebff;}#sk-container-id-1 input.sk-hidden--visually {border: 0;clip: rect(1px 1px 1px 1px);clip: rect(1px, 1px, 1px, 1px);height: 1px;margin: -1px;overflow: hidden;padding: 0;position: absolute;width: 1px;}#sk-container-id-1 div.sk-estimator {font-family: monospace;background-color: #f0f8ff;border: 1px dotted black;border-radius: 0.25em;box-sizing: border-box;margin-bottom: 0.5em;}#sk-container-id-1 div.sk-estimator:hover {background-color: #d4ebff;}#sk-container-id-1 div.sk-parallel-item::after {content: "";width: 100%;border-bottom: 1px solid gray;flex-grow: 1;}#sk-container-id-1 div.sk-label:hover label.sk-toggleable__label {background-color: #d4ebff;}#sk-container-id-1 div.sk-serial::before {content: "";position: absolute;border-left: 1px solid gray;box-sizing: border-box;top: 0;bottom: 0;left: 50%;z-index: 0;}#sk-container-id-1 div.sk-serial {display: flex;flex-direction: column;align-items: center;background-color: white;padding-right: 0.2em;padding-left: 0.2em;position: relative;}#sk-container-id-1 div.sk-item {position: relative;z-index: 1;}#sk-container-id-1 div.sk-parallel {display: flex;align-items: stretch;justify-content: center;background-color: white;position: relative;}#sk-container-id-1 div.sk-item::before, #sk-container-id-1 div.sk-parallel-item::before {content: "";position: absolute;border-left: 1px solid gray;box-sizing: border-box;top: 0;bottom: 0;left: 50%;z-index: -1;}#sk-container-id-1 div.sk-parallel-item {display: flex;flex-direction: column;z-index: 1;position: relative;background-color: white;}#sk-container-id-1 div.sk-parallel-item:first-child::after {align-self: flex-end;width: 50%;}#sk-container-id-1 div.sk-parallel-item:last-child::after {align-self: flex-start;width: 50%;}#sk-container-id-1 div.sk-parallel-item:only-child::after {width: 0;}#sk-container-id-1 div.sk-dashed-wrapped {border: 1px dashed gray;margin: 0 0.4em 0.5em 0.4em;box-sizing: border-box;padding-bottom: 0.4em;background-color: white;}#sk-container-id-1 div.sk-label label {font-family: monospace;font-weight: bold;display: inline-block;line-height: 1.2em;}#sk-container-id-1 div.sk-label-container {text-align: center;}#sk-container-id-1 div.sk-container {/* jupyter's `normalize.less` sets `[hidden] { display: none; }` but bootstrap.min.css set `[hidden] { display: none !important; }` so we also need the `!important` here to be able to override the default hidden behavior on the sphinx rendered scikit-learn.org. See: https://github.com/scikit-learn/scikit-learn/issues/21755 */display: inline-block !important;position: relative;}#sk-container-id-1 div.sk-text-repr-fallback {display: none;}</style><div id="sk-container-id-1" class="sk-top-container"><div class="sk-text-repr-fallback"><pre>RandomForestClassifier(min_samples_split=100, random_state=1)</pre><b>In a Jupyter environment, please rerun this cell to show the HTML representation or trust the notebook. <br />On GitHub, the HTML representation is unable to render, please try loading this page with nbviewer.org.</b></div><div class="sk-container" hidden><div class="sk-item"><div class="sk-estimator sk-toggleable"><input class="sk-toggleable__control sk-hidden--visually" id="sk-estimator-id-1" type="checkbox" checked><label for="sk-estimator-id-1" class="sk-toggleable__label sk-toggleable__label-arrow">RandomForestClassifier</label><div class="sk-toggleable__content"><pre>RandomForestClassifier(min_samples_split=100, random_state=1)</pre></div></div></div></div></div>




```python
from sklearn.metrics import precision_score

preds = model.predict(test[predictors])
```


```python
import pandas as pd

preds = pd.Series(preds, index = test.index)
```


```python
precision_score(test["Target"], preds)
```




    0.546875




```python
combined = pd.concat([test["Target"], preds], axis=1)
```


```python
combined.plot()
```




    <Axes: xlabel='Date'>




    
![png](output_19_1.png)
    



```python
def predict(train, test, predictors, model):
    model.fit(train[predictors], train["Target"])
    preds = model.predict(test[predictors])
    preds = pd.Series(preds, index=test.index, name="Predictions")
    combined = pd.concat([test["Target"], preds], axis=1)
    return combined
```


```python
def backtest(data, model, predictors, start=2500, step=250):
    all_predictions = []

    for i in range(start, data.shape[0], step):
        train = data.iloc[0:i].copy()
        test = data.iloc[i:(i+step)].copy()
        predictions = predict(train, test, predictors, model)
        all_predictions.append(predictions)
    return pd.concat(all_predictions)
```


```python
predictions = backtest(sp500, model, predictors)
```


```python
predictions["Predictions"].value_counts()
```




    Predictions
    0    3435
    1    2552
    Name: count, dtype: int64




```python
precision_score(predictions["Target"], predictions["Predictions"])
```




    0.5286050156739812




```python
predictions["Target"].value_counts() / predictions.shape[0]
```




    Target
    1    0.533656
    0    0.466344
    Name: count, dtype: float64




```python
horizons = [2,5,60,250,1000]
new_predictors = []

for horizon in horizons:
    rolling_averages = sp500.rolling(horizon).mean()

    ratio_column = f"Close_Ratio_{horizon}"
    sp500[ratio_column] = sp500["Close"] / rolling_averages["Close"]


    trend_column = f"Trend_{horizon}"
    sp500[trend_column] = sp500.shift(1).rolling(horizon).sum()["Target"]

    new_predictors += [ratio_column, trend_column]
```


```python
sp500 = sp500.dropna()
```


```python
sp500
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
      <th>Open</th>
      <th>High</th>
      <th>Low</th>
      <th>Close</th>
      <th>Volume</th>
      <th>Tomorrow</th>
      <th>Target</th>
      <th>Close_Ratio_2</th>
      <th>Trend_2</th>
      <th>Close_Ratio_5</th>
      <th>Trend_5</th>
      <th>Close_Ratio_60</th>
      <th>Trend_60</th>
      <th>Close_Ratio_250</th>
      <th>Trend_250</th>
      <th>Close_Ratio_1000</th>
      <th>Trend_1000</th>
    </tr>
    <tr>
      <th>Date</th>
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
      <th>1993-12-14 00:00:00-05:00</th>
      <td>465.730011</td>
      <td>466.119995</td>
      <td>462.459991</td>
      <td>463.059998</td>
      <td>275050000</td>
      <td>461.839996</td>
      <td>0</td>
      <td>0.997157</td>
      <td>1.0</td>
      <td>0.996617</td>
      <td>1.0</td>
      <td>1.000283</td>
      <td>32.0</td>
      <td>1.028047</td>
      <td>127.0</td>
      <td>1.176082</td>
      <td>512.0</td>
    </tr>
    <tr>
      <th>1993-12-15 00:00:00-05:00</th>
      <td>463.059998</td>
      <td>463.690002</td>
      <td>461.839996</td>
      <td>461.839996</td>
      <td>331770000</td>
      <td>463.339996</td>
      <td>1</td>
      <td>0.998681</td>
      <td>0.0</td>
      <td>0.995899</td>
      <td>1.0</td>
      <td>0.997329</td>
      <td>32.0</td>
      <td>1.025151</td>
      <td>126.0</td>
      <td>1.172676</td>
      <td>512.0</td>
    </tr>
    <tr>
      <th>1993-12-16 00:00:00-05:00</th>
      <td>461.859985</td>
      <td>463.980011</td>
      <td>461.859985</td>
      <td>463.339996</td>
      <td>284620000</td>
      <td>466.380005</td>
      <td>1</td>
      <td>1.001621</td>
      <td>1.0</td>
      <td>0.999495</td>
      <td>2.0</td>
      <td>1.000311</td>
      <td>32.0</td>
      <td>1.028274</td>
      <td>127.0</td>
      <td>1.176163</td>
      <td>513.0</td>
    </tr>
    <tr>
      <th>1993-12-17 00:00:00-05:00</th>
      <td>463.339996</td>
      <td>466.380005</td>
      <td>463.339996</td>
      <td>466.380005</td>
      <td>363750000</td>
      <td>465.850006</td>
      <td>0</td>
      <td>1.003270</td>
      <td>2.0</td>
      <td>1.004991</td>
      <td>3.0</td>
      <td>1.006561</td>
      <td>32.0</td>
      <td>1.034781</td>
      <td>128.0</td>
      <td>1.183537</td>
      <td>514.0</td>
    </tr>
    <tr>
      <th>1993-12-20 00:00:00-05:00</th>
      <td>466.380005</td>
      <td>466.899994</td>
      <td>465.529999</td>
      <td>465.850006</td>
      <td>255900000</td>
      <td>465.299988</td>
      <td>0</td>
      <td>0.999431</td>
      <td>1.0</td>
      <td>1.003784</td>
      <td>2.0</td>
      <td>1.005120</td>
      <td>32.0</td>
      <td>1.033359</td>
      <td>128.0</td>
      <td>1.181856</td>
      <td>513.0</td>
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
    </tr>
    <tr>
      <th>2023-08-31 00:00:00-04:00</th>
      <td>4517.009766</td>
      <td>4532.259766</td>
      <td>4507.390137</td>
      <td>4507.660156</td>
      <td>3946360000</td>
      <td>4515.770020</td>
      <td>1</td>
      <td>0.999201</td>
      <td>1.0</td>
      <td>1.008011</td>
      <td>4.0</td>
      <td>1.013441</td>
      <td>32.0</td>
      <td>1.103704</td>
      <td>121.0</td>
      <td>1.168580</td>
      <td>531.0</td>
    </tr>
    <tr>
      <th>2023-09-01 00:00:00-04:00</th>
      <td>4530.600098</td>
      <td>4541.250000</td>
      <td>4501.350098</td>
      <td>4515.770020</td>
      <td>3246260000</td>
      <td>4496.830078</td>
      <td>0</td>
      <td>1.000899</td>
      <td>1.0</td>
      <td>1.004878</td>
      <td>4.0</td>
      <td>1.014321</td>
      <td>33.0</td>
      <td>1.105050</td>
      <td>122.0</td>
      <td>1.170226</td>
      <td>531.0</td>
    </tr>
    <tr>
      <th>2023-09-05 00:00:00-04:00</th>
      <td>4510.060059</td>
      <td>4514.290039</td>
      <td>4496.009766</td>
      <td>4496.830078</td>
      <td>3526250000</td>
      <td>4465.479980</td>
      <td>0</td>
      <td>0.997899</td>
      <td>1.0</td>
      <td>0.997843</td>
      <td>3.0</td>
      <td>1.009300</td>
      <td>32.0</td>
      <td>1.099782</td>
      <td>122.0</td>
      <td>1.164868</td>
      <td>531.0</td>
    </tr>
    <tr>
      <th>2023-09-06 00:00:00-04:00</th>
      <td>4490.350098</td>
      <td>4490.350098</td>
      <td>4442.379883</td>
      <td>4465.479980</td>
      <td>3418850000</td>
      <td>4451.140137</td>
      <td>0</td>
      <td>0.996502</td>
      <td>0.0</td>
      <td>0.992302</td>
      <td>2.0</td>
      <td>1.001639</td>
      <td>31.0</td>
      <td>1.091596</td>
      <td>121.0</td>
      <td>1.156308</td>
      <td>531.0</td>
    </tr>
    <tr>
      <th>2023-09-07 00:00:00-04:00</th>
      <td>4434.549805</td>
      <td>4457.810059</td>
      <td>4430.459961</td>
      <td>4451.140137</td>
      <td>3763760000</td>
      <td>4457.490234</td>
      <td>1</td>
      <td>0.998392</td>
      <td>0.0</td>
      <td>0.991925</td>
      <td>1.0</td>
      <td>0.998004</td>
      <td>30.0</td>
      <td>1.087617</td>
      <td>120.0</td>
      <td>1.152163</td>
      <td>530.0</td>
    </tr>
  </tbody>
</table>
<p>7486 rows × 17 columns</p>
</div>




```python
model = RandomForestClassifier(n_estimators=200, min_samples_split=50, random_state=1)
```


```python
def predict(train, test, predictors, model):
    model.fit(train[predictors], train["Target"])
    preds = model.predict_proba(test[predictors])[:,1]
    preds[preds >= .6] = 1
    preds[preds < .6] = 0
    preds = pd.Series(preds, index=test.index, name="Predictions")
    combined = pd.concat([test["Target"], preds], axis=1)
    return combined
```


```python
predictions = backtest(sp500, model, new_predictors)
```


```python
predictions["Predictions"].value_counts()
```




    Predictions
    0.0    4164
    1.0     822
    Name: count, dtype: int64




```python
precision_score(predictions["Target"], predictions["Predictions"])
```




    0.5693430656934306




```python
predictions
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
      <th>Target</th>
      <th>Predictions</th>
    </tr>
    <tr>
      <th>Date</th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2003-11-14 00:00:00-05:00</th>
      <td>0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>2003-11-17 00:00:00-05:00</th>
      <td>0</td>
      <td>1.0</td>
    </tr>
    <tr>
      <th>2003-11-18 00:00:00-05:00</th>
      <td>1</td>
      <td>1.0</td>
    </tr>
    <tr>
      <th>2003-11-19 00:00:00-05:00</th>
      <td>0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>2003-11-20 00:00:00-05:00</th>
      <td>1</td>
      <td>1.0</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>2023-08-31 00:00:00-04:00</th>
      <td>1</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>2023-09-01 00:00:00-04:00</th>
      <td>0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>2023-09-05 00:00:00-04:00</th>
      <td>0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>2023-09-06 00:00:00-04:00</th>
      <td>0</td>
      <td>1.0</td>
    </tr>
    <tr>
      <th>2023-09-07 00:00:00-04:00</th>
      <td>1</td>
      <td>1.0</td>
    </tr>
  </tbody>
</table>
<p>4986 rows × 2 columns</p>
</div>




```python

```
