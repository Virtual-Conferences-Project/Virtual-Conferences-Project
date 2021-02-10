**Matthew Skiles**

Department of Civil, Architectural, and Environmental Engineering, University of Texas at Austin

*mskiles@utexas.edu*

For comments or questions, please email me.



### Introduction

This repository contains scripts and data associated with the manuscript “Beyond the carbon footprint: Virtual conferences increase diversity, equity and inclusion.” The scripts process data for graphics and calculate the cost and carbon footprint of attendance for the ~7000 participants at the 2020 virtual meetings of the North American Membrane Society (NAMS), the International Conferences on Learning Representations (ICLR) and the American Astronomical Society (AAS) if the events had been held in-person at their originally planned locations. The script also calculates cost and carbon footprint for each participant to past in-person conferences for which data is available.



### Data Sources

Facilitating this analysis is registration and survey data collected from three legacy-turned-virtual conferences, ICLR, AAS, and NAMS. These conferences represent varying fields and community sizes and allow for comparisons across a range of STEM backgrounds. Specific data collected include registration and abstract information, spanning information such as the number and type of participants (e.g., students, industry personnel), geographic participation, institution, or gender. Additional data collected on webinar attendance and virtual platform activity were used to assess the efficacy with which the virtual conferences distributed content to attendees. Qualitative data was collected by asking participants to fill out polls as well as pre-and-post conference surveys designed to interrogate the participant experience and field suggestions for improvement.



### Methodology


**Carbon Footprint of Attendance**

Scripts included in this repository were written to estimate the carbon footprint of three legacy-turned-virtual conferences. For each conference, the footprint was calculated for past conferences where data was available and for the 2020 virtual conference delegation if the event had been held in-person at the originally planned location. The carbon footprint of conference attendees was calculated as the cumulative emissions associated with the flights and hotel stays of conference participants. The script utilizes the origin location given by each attendee and uses an API to calculate the travel distance from the origin to the conference location and converts distance traveled to greenhouse gas emissions according to the methodology for the myclimate air travel emissions calculator1.  Based on attendee-specific sociodemographic data, the scripts also calculate carbon footprint per night for the attendee hotel stay using the Hotel Carbon Measurement Initiative (HCMI) rooms footprint per occupied room from the Hotel Sustainability Benchmarking Tool published by the Cornell Center of Hospitality Research2. The scripts fill missing data with average values and incorporate various assumptions i.e. students shared rooms, local attendees did not stay in hotels, etc.



**Cost of Attendance**

The scripts calculate cost of attendance for individual attendees to historically in-person turned virtual conferences by calculating their cost of travel based on air travel distance and summing with the estimated cost of the hotel, food, and conference registration fees. Travel cost was calculated as the one-way air travel distance multiplied by the cost distance for air travel defined in3, and doubled to represent the cost of a round trip flight. To account for a potential overestimate of travel cost, a sensitivity analysis where the one-way flight cost is multiplied by 1.5 instead of 2 was conducted. Registration, hotel and food costs were taken from conference records or estimated based on relevant sources. The scripts fill missing data with average values and incorporate various assumptions i.e. local attendees do not have food costs, students shared rooms, etc. The scripts calculate cost of attendance to 2020 virtual events as the cost of registration for the virtual events as outlined in conference records.



**World Map Data Processing**

The world_map data processing script takes participant origin coordinates and conference coordinates and incorporates them a great circle distance paths in a kml file for later use in producing Tableau maps of attendee flight paths.


### Results

![All Days Attendees per Room v2_final_v4-1](https://user-images.githubusercontent.com/78470390/107473123-c6579780-6b35-11eb-8b11-6ffa0cb2bf92.png)


![alt text](https://github.com/[username]/[reponame]/blob/[branch]/image.jpg?raw=true)

![alt text](https://github.com/Virtual-Conferences-Project/Virtual-Conferences-Project/blob/main/figures/All Days Attendees per Room v2_final_v4.pdf?raw=true)

![alt text](https://github.com/Virtual-Conferences-Project/Virtual-Conferences-Project/blob/main/figures/fig_1ab_final_final_v1.pdf?raw=true)

![fig_1ab_final_final_v1](https://github.com/Virtual-Conferences-Project/Virtual-Conferences-Project/figures/fig_1ab_final_final_v1.pdf)

## References

[1] The myclimate Flight Emission Calculator (Foundation myclimate, accessed October 30th,
2020);  2019; https://www.myclimate.org/

[2] Chong HG, Ricaurte EE. Hotel sustainability benchmarking tool 2015: energy, water, and
carbon. Cornell Hospitality Reports: Cornell University; 2015.

[3] Dudas G, Boros L, Pal V, Pernyesz P. Mapping cost distance using air traffic data. J Maps
2016, 12(4): 695-700.

