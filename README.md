# Ex.No: 1B                     CONVERSION OF NON STATIONARY TO STATIONARY DATA
# Date: 17.02.2024

### AIM:
To perform regular differncing,seasonal adjustment and log transformatio on international airline passenger data
### ALGORITHM:
1. Import the required packages like pandas and numpy
2. Read the data using the pandas
3. Perform the data preprocessing if needed and apply regular differncing,seasonal adjustment,log transformation.
4. Plot the data according to need, before and after regular differncing,seasonal adjustment,log transformation.
5. Display the overall results.
### PROGRAM:
## Regular Differencing
```
import numpy as np
import matplotlib.pyplot as plt
import pandas as pd
data=pd.read_csv("/content/AirPassengers.csv",parse_dates=['Month'],index_col='Month')
data.head()
passengers['shifted_value']=passengers['#Passengers'].shift(1)
passengers['difference_value']=passengers['#Passengers']-passengers['shifted_value']
passengers.dropna(inplace=True)
print(passengers)
passengers.plot(kind='line')
```

## Seasonal Adjustment
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from statsmodels.tsa.seasonal import seasonal_decompose
data=pd.read_csv("/content/AirPassengers.csv",parse_dates=['Month'],index_col='Month')
passengers=pd.DataFrame(data)
result=seasonal_decompose(passengers['#Passengers'],model='additive',period=1)
seasonal=result.seasonal
passengers['Seasonal_value']=passengers['#Passengers']-seasonal
passengers.dropna(inplace=True)
print(passengers)
passengers.plot(kind='line')
```
## Log Transformation
```
import numpy as np
import pandas as pd
data= pd.read_csv('AirPassengers.csv')
data.head()
data.dropna(inplace=True)
x=data['Month']
y=data['#Passengers']
data_log=np.log(data['#Passengers'])
X=data['Month']
Y=data_log
import matplotlib.pyplot as plt
plt.plot(x,y)
plt.xlabel('Original Data')
plt.plot(X,Y)
plt.xlabel('Log- Transformed data')
```

### OUTPUT:

REGULAR DIFFERENCING:

![image](https://github.com/vikashsenthil21/TSA_EXP1B/assets/119433834/5853e44d-54ec-45f0-bea8-695711416c97)





SEASONAL ADJUSTMENT:
![image](https://github.com/vikashsenthil21/TSA_EXP1B/assets/119433834/88efc5c3-dddb-4f0d-bfa1-3057d896fa29)



LOG TRANSFORMATION:
![image](https://github.com/vikashsenthil21/TSA_EXP1B/assets/119433834/3221aa43-117b-4584-b1b7-007932e2fbfe)

![image](https://github.com/vikashsenthil21/TSA_EXP1B/assets/119433834/64674116-971e-4b43-91bd-c978dcac9af0)






### RESULT:
Thus we have created the python code for the conversion of non stationary to stationary data on international airline passenger
data.
