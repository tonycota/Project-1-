# Project-1-
A Washington State elctric vehicle trend slideshow by Holly and Tony

This is a study examining electric vehicle trends in Washington State. The scope of the study:
Age of vehicles currently in circulation
Electric ranges of the vehicles
The impact of car rebates, federal and local incentives (if any) on purchasing electric vehicles
Visualize and demonstrate the exponential rise in electric vehicles in Washington State
Deliver information regarding major manufacturers plans to convert to full lines of EV's, ultimately outdating internal combustion vehicles obsolete\



ANALYSIS OF ELECTRIC VEHICLES IN WASHINGTON STATE
Data is sourced from Data obtained from https://catalog.data.gov/dataset/electric-vehicle-population-data
Information provided is a high level summary for electric vehicles in the state of Washington
graphs include information regarding trends over the past 3 decades
graphs discuss data regarding tax incentives/rebates/exemptions for purchasing an electric vehicle
slideshow demonstrates major car maufacturers expected EV lineup dates
presentation shows location of EV's in WA and their electric range
slides demonstrate null hypothesis to be true over initial hypothesis





<!-- Source code (Holly):

#How to create a seaborn correlation heatmap in Python?.Geeks for Geeks. (https://www.geeksforgeeks.org/how-to-create-a-seaborn-correlation-heatmap-in-python/). (Accessed on February 6, 2024).
data = electric_vehicle_df[['Electric Range', 'Model Year']]
correlation_matrix = data.corr()
plt.figure(figsize=(10,6))
sns.heatmap(data.corr(), cmap='coolwarm', annot=True)
plt.title('Correlation Matrix between Electric Range and Model Year')
plt.savefig('correlation_range_modelyearpng')
plt.show()

#Chatgpt personal communication February 6, 2024
from sklearn.preprocessing import LabelEncoder
label_encoder = LabelEncoder()
electric_vehicle_df['Make_encoded'] = label_encoder.fit_transform(electric_vehicle_df['Make'])
correlation_coefficient = electric_vehicle_df['Electric Range'].corr(electric_vehicle_df['Make_encoded'], method='pearson')
print("Pearson Correlation Coefficient:", correlation_coefficient)
plt.savefig('EV_Range_vs_Car_Manufacturer_Scatterplot.png')
plt.show()

#Matplotlib. Plyplot tutorial. Retrieved from https://matplotlib.org/stable/tutorials/pyplot.html#sphx-glr-tutorials-pyplot-py. (Accessed on January 25, 2024).
make_counts = electric_vehicle_df['Make'].value_counts()
top_10 = make_counts.head(10)
plt.figure(figsize=(10, 6))
top_10.plot(kind='barh', color='purple')
plt.title('Top 10 Manufactures of EV Vehicles')
plt.xlabel('Manufacture')
plt.ylabel('Total EVs')
plt.xticks(rotation=45, ha='right')
plt.tight_layout()
plt.savefig('highest_manufacture.png')
plt.show()

#Chatgpt personal communication February 1, 2024
from datetime import datetime
current_year = datetime.now().year
electric_vehicle_df['Age'] = current_year - electric_vehicle_df['Model Year']
grouped_cars_df = electric_vehicle_df.groupby(['Make', 'Model Year', 'Age']).size().reset_index(name='Count')

Chatgpt personal communication January 31, 2024
electric_vehicle_df.replace({'Legislative District': {'NA': np.nan, '': np.nan}}, inplace=True)
electric_vehicle_df.dropna(subset=['Legislative District'], inplace=True)
electric_vehicle_df.dropna(subset=['City'], inplace=True)
electric_vehicle_df.dropna(subset=['County'], inplace=True)

plotting_groups_solution in class exercise
Python Software Foundation. (2020). Python Language Reference, version 3.12.1. Available at [https://docs.python.org/3.8/.](https://docs.python.org/3/index.html)

Credits:
https://matplotlib.org/stable/index.html
Data obtained from https://catalog.data.gov/dataset/electric-vehicle-population-data
Python Software Foundation. (2024). Python Language Reference, version 3.12.1. Available at [https://docs.python.org/3.8/.](https://docs.python.org/3/index.html)
Images courtesy of https://unsplash.com/s/photos/electric-car -->


graphs requested:
![Alt text](tonys_code/ev_county_graph.png)
![Alt text](tonys_code/ev_trend.png)
![Alt text](tonys_code/washington_map_visual.jpeg)

![Alt text](Holly_Plots_Final/highest_manufacture.png)
Used the Pearson correlation coefficient to determine if there was a correlation between car manufacture and electrical vehicle range
Weak positive correlation Pearson Correlation Coefficient: 0.07193586773978594
![Alt text](Holly_Plots_Final/Distribution_Ranges_Car_Makes_plot1.png)

Used the Cramer's V:0 chi-square test provided there is no correlation between the two variables of total EVs in circulation and car manufacture
![Alt text](Holly_Plots_Final/highest_manufacture.png)

Used the Pearson's Correlation Coefficient found no correlation between age and count of EVs in circulation.  -0.12888215071722858 shows a weak negative correlation
![Alt text](Holly_Plots_Final/EV_By_Age_Make_plot1.png)