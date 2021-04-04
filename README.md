 

Final Assessment - Growth of Corona
Objectives
After completing this lab you will be able to:

Be conﬁdent about your machine learning skills


Welcome to the ﬁnal assigment. Please import this notebook into IBM Watson Studio. This Notebook displays growth of Corona cases. Please change the Country to anything other than "United_States_of_America". A list of available countries is given in the next cell. You can change the country in the cell after the next cell. Once ﬁnished, please share the notebook for grading.

In [ ]:import pandas as pd 
import seaborn as sns

url = 'https://www.ecdc.europa.eu/sites/default/files/documents/COVID-19
-geographic-disbtribution-worldwide-2020-03-26.xlsx' df_raw = pd.read_excel(url)

df_raw['Countries and territories'].unique()
![image](https://user-images.githubusercontent.com/79148207/113502399-afbd3380-951b-11eb-9807-911a0c6b1988.png)

In [ ]:df = df_raw
df = df[df['Countries and territories']=='United_States_of_America'] df = df.sort_values(['Year', 'Month' ,'Day'], ascending=[1, 1, 1])
df['ts'] = pd.to_datetime(df[['Year', 'Month' ,'Day']])
![image](https://user-images.githubusercontent.com/79148207/113502404-b9469b80-951b-11eb-8f33-b793eaa684c5.png)

In [ ]:chart = sns.lineplot(x='ts', y='Cases', data=df, hue='Countries and terr itories')
chart.set_xticklabels(df['ts'],rotation=45)
![image](https://user-images.githubusercontent.com/79148207/113502408-bf3c7c80-951b-11eb-98b6-e7fa65ecdd72.png)

 
Thank you for completing this lab!

Author
Romeo Kienzler

Other Contributors
Lavanya

Change Log
Date (YYYY-MM-DD) Version Changed By	Change Description
2020-09-01	2.0	Lavanya   Moved lab to course repo in GitLab


© IBM Corporation 2020. All rights reserv
![image](https://user-images.githubusercontent.com/79148207/113502389-9b793680-951b-11eb-9031-4122751d1287.png)
