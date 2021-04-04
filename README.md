 cognitiveclass.ai logo
Final Assessment - Growth of Corona
Objectives
After completing this lab you will be able to:

Be confident about your machine learning skills
Welcome to the final assigment. Please import this notebook into IBM Watson Studio. This Notebook displays growth of Corona cases. Please change the Country to anything other than "United_States_of_America". A list of available countries is given in the next cell. You can change the country in the cell after the next cell. Once finished, please share the notebook for grading.

import pandas as pd
import seaborn as sns

url = 'https://www.ecdc.europa.eu/sites/default/files/documents/COVID-19-geographic-disbtribution-worldwide-2020-03-26.xlsx'
df_raw = pd.read_excel(url)

df_raw['Countries and territories'].unique()

df = df_raw

df = df[df['Countries and territories']=='Indonesia']

df = df.sort_values(['Year', 'Month' ,'Day'], ascending=[1, 1, 1])

df['ts'] = pd.to_datetime(df[['Year', 'Month' ,'Day']])


chart = sns.lineplot(x='ts', y='Cases', data=df, hue='Countries and territories')
chart.set_xticklabels(df['ts'],rotation=45)

Thank you for completing this lab!
Author
Romeo Kienzler

Other Contributors
Lavanya

Change Log
Date (YYYY-MM-DD)	Version	Changed By	Change Description
2020-09-01	2.0	Lavanya	Moved lab to course repo in GitLab
