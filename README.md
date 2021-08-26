# Optimal Location for Opening a Japanese Restaurant


# Introduction
While opening a restaurant can be a very lucrative business, a lack of demand causes many restaurants to close within the first year of opening. There are many different factors that can account for a restaurant’s success such as location, competition and quality of the food. This is an important question that every business owner must face when choosing whether to open a restaurant or not, as well as location of the business.

To demonstrate the process of picking a location for a client opening a business, the project will focus on answering the following question: “If the client wanted to open an Japanese Restaurant in Toronto, what areas are the best options to open the restaurant?” For an Japanese Restaurant, the location and competition are both determined by where the restaurant is opened. If there are too many Japanese Restaurants in the local vicinity, the profitability of the restaurant will be severely decreased. Additionally, starting a restaurant in a location with higher income would increase the profitability of the business over starting in a poorer area.

# Data
To answer the business problem, the following factors have to be extracted from various data sources:

Population & Ethnic Distribution of Each Neighborhood (Wellbeing Toronto)<p>
Income Distribution of Each Neighborhood (Wellbeing Toronto)<p>
Number of Restaurants in Each Neighborhood (Foursquare API)<p>
Number of Japanese Restaurants in Each Neighborhood (Foursquare API)<p>
The Wellbeing Toronto data was extracted from http://map.toronto.ca/wellbeing/#eyJ0b3Itd2lkZ2V0LWNsYXNzYnJlYWsiOsSAcGVyY2VudE9wYWNpdHnElzcwfSwiY3VzxIJtYcSTYcSXxIBuZWlnaGJvdXJob29kc8S2fcSrxIHEg8SFxIfEicSLdGFixYXEmCLEo3RpdmVUxZBJZMSXxYnEhMWPYi1pbmRpY2HEgnLFhcWIYWdzTWFwxLYiesWCbcSXMTPErHjEly04ODM3NzYzLjXGhDcyN8SsxKc6NTQxMjkzMS4yNMaDMjg1xYjFpMWmxajFqsWSxIDFmMWraW9uxJcyxKxzxaRnbGXFtMSucsSTxJ9UaW1lxZzEqMSsxZbGucajIjfFtMafxafFqcSDxZxzQcWlV8S5xLt0xZJbxIDEh8WeMTUwIsSsd8eNaHTFucSsxJPGpXNlUG%2FEjnLEpcaOZmFsx6LEq8eSxZ06IjEwNMeYIseaxLrHnMeeIsegxJvHosekx6bHqMSXx6rHrGXHriLHk8exOTXHtse4x47Hu8e9xavHo8elxLPIgjrIhMetLMevxZ45NsiNx5vHnToxx59lx6HIk8iBxKbIg8eryJnIm8exx7PHl8eZyKDIkMilx77Ip8iVyKnIl8iryIbImsiIx7DHgTPHtsiRx7%2FIlMenyLjImMiGXcWHxYjGvmXHosenyY3FhsSsxrPGtXRJxaXHhcWqTcWDxrHHscatbsavxrHFhw%3D%3D

# Methology 

The first step of the project was to combine the Toronto dataset, containing the postal code, borough, neighborhood name, latitude and longitude for each postal code in Toronto, and the demographics dataset(Wellbeing Toronto).

Using the income distribution for each neighborhood, the spending power of each area was calculated using the median of each category weighted by the number of people in that income category. Thus, the spending power represents the overall capital of each area (i.e. total income of the inhabitants). Since the spending power for each area is considerably large and the relative strength is difficult to visualize, the spending power for each area was standardized.

The next step was to visualize the location of the various postal codes within Toronto to obtain a general understanding the location. As seen from the map, the postal codes are densely clustered near downtown Toronto and spread out as the distance from downtown increases. This is important because while some postal codes might not have many restaurants, if the area is located near downtown, adjacent regions can heavily impact the profitability of the restaurant.
With the resulting data, the Postal Code, Borough name, Latitude, Longitude and Density columns of each region were dropped from the dataFrame. Then, the population, area, spending power, total number of restaurants and the number of japanese restaurants were used to train a k-Means clustering algorithm with 5 clusters.

 # Discussion
Amoung 5 clusters, cluster 1 has relatively higher average household income with less restaurants around. Therefore cluster 1 was further examed regarding population, total restaurants, total Japanese restaurants and average household income.
From the results of the clustering algorithm, it was determined that neighborhoods corresponding to cluster 1 were the best choice for opening an Japanese restaurant based on the spending power and population. This narrowed down possible locations to two different areas. Using the results in map above, Willowdale West and Hillcrest Village were eliminated due to the large number of restaurants in the area.

From the two remaining regions, I would recommend that the client open his/her restaurant in either. Both regions have very few restaurants and are farther away from the downtown area. Both have a higher spending power and populatio but Willowdale region has a higher percentage of Japanese and thus the optimal region to open the Japanese Restaurant.

# Conclusion
Opening a restaurant is a complex task that can lead to a large monetary loss if not done properly. Thus, extensive research about the area would greatly increase the likelihood of the restaurant succeeding. From the project above, I demonstrated the workflow necessary for a client to determine what area the restaurant should open. For specifically, I determined that the optimal location to open an Japanese restaurant in Toronto should be in the Willowdale region. 
