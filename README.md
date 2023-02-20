# Flights: Airline on-time performance
## by RICHARD KAMGANG

### Skill
- Exploratory visualizations with matplotlib and seaborn libraries

## Dataset

> Our work here focuses on finding one or more potential factor(s) that would be related to the delay or cancellation of commercial flights. Our dataset contains millions of rows of airline (commercial) punctuality data in the United States between October 1987 and April 2008 available [here](https://dataverse.harvard.edu/dataset.xhtml?persistentId=doi:10.7910/DVN/HG7NV7) (for memory reasons, we will only work with data from the year 2007).

> In this first part, I will proceed to the collection of the dataset, then to the data-wrangling and finally to the exploratory analysis.
The processing consists of removing duplicates and defining the data types in the columns.

The data structure is made up as follows:

1. **Year** : 2007 
2. **Month** : 1-12 
3. **DayofMonth** :  1-31 
4. **DayOfWeek** : 1 (Monday) - 7 (Sunday) 
5. **DepTime** : actual departure time (local, hhmm)
6. **CRSDepTime** : scheduled departure time (local, hhmm)
7. **ArrTime** : actual arrival time (local, hhmm) 
8. **CRSArrTime** : scheduled arrival time (local, hhmm) 
9. **UniqueCarrier** : unique carrier code

| Code | UA | US | WN | MQ | NW | OO | XE | DL | EV | FL |
|:-----|:---|:---|:---|:---|:---|:---|:---|:---|:---|:---|
|**Description**|United Air Lines Inc. |US Airways Inc. |Southwest Airlines Co. |Envoy Air |Northwest Airlines Inc. |Northwest Airlines Inc. |SkyWest Airlines Inc. |Delta Air Lines Inc. |ExpressJet Airlines LLC |AirTran Airways Corporation |


| Code | AA | AS | B6 | CO | HA | OH | F9 | YV | AQ | 9E |
|:-----|:---|:---|:---|:---|:---|:---|:---|:---|:---|:---|
|**Description**|American Airlines Inc. |Alaska Airlines Inc. |JetBlue Airways |Continental Air Lines Inc. |Hawaiian Airlines Inc. |PSA Airlines Inc. |Frontier Airlines Inc. |Mesa Airlines Inc. |Aloha Airlines Inc. |Endeavor Air Inc. |

10. **FlightNum** : flight number
11. **TailNum** : plane tail number
12. **ActualElapsedTime** : Elapsed Time of Flight in minutes 
13. **CRSElapsedTime** : CRS Elapsed Time of Flight in minutes (flight time estimated by the computer reservation system - CRS)
14. **AirTime** : Flight Time in minutes 
15. **ArrDelay** : arrival delay, in minutes 
16. **DepDelay** : departure delay, in minutes 
17. **Origin** : origin IATA airport code
18. **Dest** : destination IATA airport code
19. **Distance** : distance between airports in miles
20. **TaxiIn** : the time elapsed between wheels down and arrival at the destination airport gate in minutes 
21. **TaxiOut** : the time elapsed between departure from the origin airport gate and wheels off in minutes
22. **Cancelled** : cancelled Flight Indicator (1=yes, 0=no) 
23. **CancellationCode** : reason for cancellation (A = carrier, B = weather, C = NAS, D = security)
| Code | A  | B  | C  | D  |
|:-----|:---:|:---:|:---:|:---:|
|**Meaning**|Carrier |Weather | National Air System (NAS) |Security|

24. **Diverted** : diverted Flight Indicator (1=Yes, 0=no)
25. **CarrierDelay** : carrier Delay in minutes (data starts 6/2003)
26. **WeatherDelay** : Weather Delay in minutes (data starts 6/2003)
27. **NASDelay** : National Air System Delay in minutes (data starts 6/2003)
28. **SecurityDelay** : Security Delay in minutes (data starts 6/2003)
29. **LateAircraftDelay** : Late Aircraft Delay in minutes (data starts 6/2003)
30. **LateArr** : YES, if ArrDelay > 15 min and NO if ArrDelay < 15 min
31. **LateDep** : YES, if DepDelay > 15 min and NO if DepDelay < 15 min


## Summary of Findings

The DepDelay and ArrDelay variables are right-skewed and have modes around zero.
Regarding the distribution of the days of the week, the distribution is skewed towards the end of the week. We also notice that Southwest Airlines Co. (WN) has more flights than the others, followed by American Airlines Inc. (AA).
Another interesting note is that carriers are the main cause of flight cancellations, more than the weather.
The delay before take-off almost systematically leads to the delay on arrival, this is clearly represented. Nevertheless less it remains true that a flight departing on time can arrive at destination with a delay due to several factors during the flight and at landing. we then think of weather conditions, the National Air System (NAS) and others.
Although most flights take off on time and land on time, there are some who wait long hours before departure.
It is also clear that the best times to start a trip are the months of May, September, October and November, preferably on Saturdays and Tuesdays.
Regarding the rate of delay and rate of cancellation, some carriers exceed 4%.

## Key Insights for Presentation

For the overview, I'm focusing on features that have more to do with timelines. First I present the distribution of delays and then I show which airlines have the most average delays. Next, And finally, I show how the days of the week influence the delays.
