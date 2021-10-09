# Conference Demographics and Footprint Changed by Virtual Platforms

**Corresponding Author:** 
**Dr. Manish Kumar**

The University of Texas at Austin

*manish.kumar@utexas.edu*

For comments or questions, please email me.



# Introduction

This repository contains scripts and data associated with the manuscript “Conference demographics and footprint change by virtual platforms.” The scripts process data for graphics and calculate the cost and carbon footprint of attendance for the ~7000 participants at the 2020 virtual meetings of the North American Membrane Society (NAMS), the International Conferences on Learning Representations (ICLR) and the American Astronomical Society (AAS) if the events had been held in-person at their originally planned locations. The script also calculates cost and carbon footprint for each participant to past in-person conferences for which data is available.



# Data Sources

Facilitating this analysis is registration and survey data collected from three legacy-turned-virtual conferences, ICLR, AAS, and NAMS. These conferences represent varying fields and community sizes and allow for comparisons across a range of STEM backgrounds. Specific data collected include registration and abstract information, spanning information such as the number and type of participants (e.g., students, industry personnel), geographic participation, institution, or gender. Additional data collected on webinar attendance and virtual platform activity were used to assess the efficacy with which the virtual conferences distributed content to attendees. Qualitative data was collected by asking participants to fill out polls as well as pre-and-post conference surveys designed to interrogate the participant experience and field suggestions for improvement.



# Methodology


### Carbon Footprint of Attendance ###

Scripts included in this repository were written to estimate the carbon footprint of three legacy-turned-virtual conferences. For each conference, the footprint was calculated for past conferences where data was available and for the 2020 virtual conference delegation if the event had been held in-person at the originally planned location. The carbon footprint of conference attendees was calculated as the cumulative emissions associated with the flights and hotel stays of conference participants. The script utilizes the origin location given by each attendee and uses an API to calculate the travel distance from the origin to the conference location and converts distance traveled to greenhouse gas emissions according to the methodology for the myclimate air travel emissions calculator1.  Based on attendee-specific sociodemographic data, the scripts also calculate carbon footprint per night for the attendee hotel stay using the Hotel Carbon Measurement Initiative (HCMI) rooms footprint per occupied room from the Hotel Sustainability Benchmarking Tool published by the Cornell Center of Hospitality Research2. The scripts fill missing data with average values and incorporate various assumptions i.e. students shared rooms, local attendees did not stay in hotels, etc.



### Cost of Attendance ###

The scripts calculate cost of attendance for individual attendees to historically in-person turned virtual conferences by calculating their cost of travel based on air travel distance and summing with the estimated cost of the hotel, food, and conference registration fees. Travel cost was calculated as the one-way air travel distance multiplied by the cost distance for air travel defined in3, and doubled to represent the cost of a round trip flight. To account for a potential overestimate of travel cost, a sensitivity analysis where the one-way flight cost is multiplied by 1.5 instead of 2 was conducted. Registration, hotel and food costs were taken from conference records or estimated based on relevant sources. The scripts fill missing data with average values and incorporate various assumptions i.e. local attendees do not have food costs, students shared rooms, etc. The scripts calculate cost of attendance to 2020 virtual events as the cost of registration for the virtual events as outlined in conference records.



### World Map Data Processing ###

The world_map data processing script takes participant origin coordinates and conference coordinates and incorporates them a great circle distance paths in a kml file4 for later use in producing Tableau maps of attendee flight paths.


# Results

### Demographic Impact ###

**Figure 1** illustrates themes seen across all datasets. The elimination of the travel and cost burdens realized with the virtual conference format resulted in a large increase in attendance at all events. The increase in attendance was particularly pronounced for international attendees. This trend can be explained by the decrease in costs as compared to in-person conferences.

![fig_1ab_final_final_v1-1](https://user-images.githubusercontent.com/78470390/107476172-f0f81f00-6b3a-11eb-9192-9d6d12b6b8e9.png)
**Fig 1 | 2020 virtual conferences were larger as well as more economically and geographically equitable than historical in-person conferences. (a)** The delegation for the 2019 in-person ICLR was global, but concentrated in the United States (n=2584). **(b)** The delegation for the 2020 virtual ICLR was larger and more geographically diverse than the 2019 in-person ICLR delegation and would have resulted in a larger number of attendees emitting greater amounts of carbon emissions if it had been held in the originally planned on-site location in Ethiopia (n=4980)

The cost of attending legacy conferences for international attendees was dominated by airfare **(Figure 2)**. Air travel cost was calculated by converting one-way travel distance to cost using a conversion factor described in Duda et al17 and doubling the value to obtain the cost for a round trip flight. When compared to US attendees, researchers from Africa paid 174% more, Asia paid 145% more, Europe paid 92% more, the Middle East paid 127% more, Oceania paid 203% more, and Other Americas  paid 7% more to attend legacy NAMS conferences. When placed in financial context, the cost of attendance for scientists from Africa to past in-person ICLR conferences (2018-2019), AAS (2016-2019) Conferences, and NAMS (2015-2019) conferences was on average 140%, 142% and 81% of their country’s annual per capita gross domestic product (GDP), compared to just 3% of per capita GDP for US participants **(Figure 2a)**. Cost of attendance for participants from Asia to past in-person ICLR (2018-2019), AAS (2016-2019), and NAMS (2015-2019) conferences was on average 16%, 15%, and 14% of their country’s per capita GDP **(Figure 2a)**. However, it is important to note that many conferences not included in this analysis have registration fees in excess of $700. For these events, registration fees can begin to compete with airfare as a significant contributing financial consideration.

By eliminating these travel and registration costs, the 2020 virtual ICLR, AAS and NAMS delegations were more geographically diverse. Notably, the audiences were 118%, 97% and 41% larger than the historical average for in-person conferences, respectively **(Figure 2b)**.  Attendance by scientists from NI>10 countries increased significantly from the historical average at legacy ICLR, AAS, and NAMS conferences (204, 11, and 50.3 attendees) to the 2020 virtual ICLR, AAS, and NAMS conferences (955, 64, and 65 attendees), respectively **(Figure 2b)**.

![fig_2abc_final_final_v1-1](https://user-images.githubusercontent.com/78470390/107476178-f3f30f80-6b3a-11eb-8fb7-41efa79cd262.png)
**Fig 2 | (a)** Regional average cost of attendance to legacy (Leg) in-person conferences as a percent of attendee country’s GDP per capita for ICLR (n=2), AAS (n=4), and NAMS (n=4) conferences was significantly higher for African participants, and very low for US participants. **(b)** The delegations for 2020 virtual ICLR (n=1), AAS (n=1), and NAMS (n=1) conferences generally represented more countries that were not in the top ten research countries as defined by the Nature Index12 (NI>10) and included a higher number of attendees from those countries compared to the average delegations from legacy conferences. **(c)** Average registration, food, hotel, and travel costs for a single attendee to past in-person ICLR (n=2), AAS (n=4), and NAMS (n=4) conferences totaled thousands of USD, compared to less than 200 USD for 2020 virtual ICLR (n=1), AAS (n=1), and NAMS (n=1) conferences.

### Environmental Impact ###

The carbon footprints of in-person conferences was defined as the warming potential in CO2 equivalents (CO2e) of the sum total of GHG emitted by the hotel stays and air travel of all conference participants. This value was dominated by air travel emissions and has increased over time **(Figure 6a, 6b)**. Given the increase in attendees at the virtual conferences, both absolute numbers and international participation, the theoretical GHG emissions for the 2020 virtual conferences would have significantly increased if they were held in-person. However, as expected, carbon footprints were practically negligible for online conferences.

As shown in **Figure 6b**, the carbon footprint for a single international attendee to the 2019 in-person ICLR, AAS or NAMS conferences is approaching the median global per capita carbon budget (3.26 tonnes CO2e) for the entire year of 2030 in a collection of proposed decarbonization pathways designed to limit global warming to 1.5 C with a small overshoot19. Therefore, the carbon footprint of a single attendee to an in-person conference is a substantial fraction of the recommended per capita annual carbon budgets, and many attendees attend multiple international events per year. For further context, the ~2.5 tons of CO2e emissions caused by an international attendee to one of these in-person conferences is roughly equivalent to the footprint of an average US passenger vehicle traveling ~10,000 km20.


![fig_6ab_final_final_v1-1](https://user-images.githubusercontent.com/78470390/107476185-f6ee0000-6b3a-11eb-884c-0dbea9841d8c.png)

**Fig. 6 | The cost and carbon footprint of in-person conferences are significant, increasing and inequitable. (a)** The total summed carbon footprints of air travel and accommodation for all attendees to past in-person ICLR, AAS, and NAMS conferences increased over time and the hypothetical 2020 in-person conference footprint (dotted line), calculated as the footprint if all virtual conference participants had attended an in-person conference at the originally chosen location, was far greater than any previous conferences, while virtual 2020 conferences had near zero footprint. **(b)** The average carbon footprint of attendance for domestic and international participants to the most recent in-person conferences (2019) (n=1 for ICLR, AAS, and NAMS) were significant compared to the proposed median global per capita annual carbon budgets for 2030 and 2050 in a collection of proposed decarbonization pathways designed to limit global warming to 1.5 C with a small overshoot19. 

Conversely, the total carbon footprints of the 2020 virtual ICLR, AAS, and NAMS conferences were 0.80, 0.17, and 0.10 tonnes CO2e, respectively, calculated as the GHG emitted due to computer processing13. The carbon footprints for 2020 virtual ICLR, AAS, and NAMS conferences represent only 0.005%, 0.013%, and 0.012% of the emissions that would have been released if the same delegation for the virtual events had attended in-person conferences at the originally planned locations. For further context, the cumulative footprints of the more than 7000 attendees to 2020 virtual ICLR, AAS, and NAMS conferences (1.07 tonnes CO2e) was comparable to the average footprint of a single attendee to one of these 2019 in-person conferences **(Figure 6b)**.

![All Days Attendees per Room v2_final_v4-1](https://user-images.githubusercontent.com/78470390/107473123-c6579780-6b35-11eb-8b11-6ffa0cb2bf92.png)
**Fig. S9 |** Number of attendees in each oral session and total percent of registrants participating in oral sessions throughout the 2020 virtual NAMS conference. (Total number of registrants=635)


# References

[1] The myclimate Flight Emission Calculator (Foundation myclimate, accessed October 30th,
2020);  2019; https://www.myclimate.org/

[2] Chong HG, Ricaurte EE. Hotel sustainability benchmarking tool 2015: energy, water, and
carbon. Cornell Hospitality Reports: Cornell University; 2015.

[3] Dudas G, Boros L, Pal V, Pernyesz P. Mapping cost distance using air traffic data. J Maps
2016, 12(4): 695-700.

[4] Battersby, S. & F. Ramseger. 2017. Flights of the World: How to map great circle routes in Tableau 10.4.

