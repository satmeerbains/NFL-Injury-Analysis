## 1. Abstract
Recent investigations of lower limb injuries among football athletes have indicated significantly higher injury rates on synthetic turf compared with natural turf (Mack et al., 2018; Loughran et al., 2019). In conjunction with the epidemiologic investigations, biomechanical studies of football cleat-surface interactions have shown that synthetic turf surfaces do not release cleats as readily as natural turf and may contribute to the incidence of non-contact lower limb injuries (Kent et al., 2015). Given these differences in cleat-turf interactions, it has yet to be determined whether other measures of player performance differ across playing surfaces and how these may contribute to the incidence of lower limb injury. 

The goal of this project is to investigate the relationship between the playing surface and the injury and performance of National Football League (NFL) athletes and to examine factors that may contribute to lower extremity injuries. In the NFL, 12 stadiums have fields with synthetic turf.

## 2. Exploratory Data Analysis (EDA)
This section focused on understanding the structure, quality, and scope of three datasets - 
* Injury Record: The injury record file in .csv format contains information on 105 lower-limb injuries that occurred during regular season games over the two seasons. Injuries can be linked to specific records in a player history using the PlayerKey, GameID, and PlayKey fields.

* Play List: The play list file contains the details for the 267,005 player-plays that make up the dataset. Each play is indexed by PlayerKey, GameID, and PlayKey fields. Details about the game and play include the player’s assigned roster position, stadium type, field type, weather, play type, position for the play, and position group.

* Player Track Data: player level data that describes the location, orientation, speed, and direction of each player during a play recorded at 10 Hz (i.e. 10 observations recorded per second).

Insights such as the number of unique players, games, and plays, then reshapes the data into a cleaner game-level format. Environmental variables such as stadium type, temperature, and weather conditions are standardized and cleaned to ensure consistency. These steps prepare the dataset for reliable visualization and modeling.

## 3. Visualizations
A variety of visualizations were generated to showcase relationships between player injury and a variety of factors such as environmental, play types, etc. Spatial heatmaps show where players spend the most time on the field and where injuries most frequently occur. Additional plots explore injury counts, injury locations, and player timelines leading up to injury events, providing intuitive visual context for later statistical findings.
<img width="468" height="208" alt="image" src="https://github.com/user-attachments/assets/f164d68e-95fc-4b58-bb05-6ae407edcca9" />
<img width="468" height="185" alt="image" src="https://github.com/user-attachments/assets/fc47fd07-9141-44b9-81c9-8b820e55c2d7" />
<img width="327" height="217" alt="image" src="https://github.com/user-attachments/assets/c1632b84-b99a-43ed-9ebd-affc39edd31f" />
<img width="1251" height="702" alt="image" src="https://github.com/user-attachments/assets/4a047985-82e6-466d-a9f0-6c140ba32888" />
<img width="740" height="451" alt="image" src="https://github.com/user-attachments/assets/32b283fa-ffdf-4711-a3e1-4e0f02cc2932" />

## 4. Statistical Analysis of Player Injuries
This section transitions from visual insights to quantitative analysis of player injury. After preparing modeling-ready datasets, correlations are examined between injuries and environmental factors like temperature and stadium type, as well as number of games played and play types. However, no significant correlations were found. 

Hypothesis testing was also used to evaluate whether injury risk differs significantly between natural grass and synthetic turf; resulting in not rejecting the null hypothesis: 
The likelihood of a player experiencing an injury on natural grass is less than or equal to the probability of the injury on synthetic turf.

## 4. Machine Learning – Predicting Player Injury
A predictive modeling pipeline was developed to estimate the likelihood of player injury and to determine importatnt features that contribute to it. First the merged injury and plays list datasets were split into training and test using a stratified fold method to evenly distribute class labels. Following this the data was resampled due to the fact that injuries are relatively rare events, the model was trained using XGB Boost classifier. Despite having underperformed it was used to determine feature importance, which represent environmental conditions, player usage etc. The following shows the most important of these features. 

<img width="1610" height="849" alt="image" src="https://github.com/user-attachments/assets/85e2e23d-557b-4a10-ba6a-ec3203d57951" />

## 5. Synthetic vs Natural Turf Analysis
After learning that the hypothesis that there is a statistical backing that injuries are more likely to occur on synthetic turf, this section dived deeper into how turf type interacts with other conditions. It compares injury rates on natural and synthetic surfaces under varying weather and temperature scenarios, including specific hypothesis tests for rainy conditions. The analysis also examines whether certain player positions are more affected by synthetic turf, helping clarify how surface type and context combine to influence injury risk. This analysis showed that the position of defensive back experiences injury at a far greater rate when compared to other positions stratified into natural vs synthetic turf.

<img width="1251" height="702" alt="image" src="https://github.com/user-attachments/assets/f5aef7a3-8476-4125-9680-3039919d4f91" />


## 7. Conclusion
The goal of this analysis was determine if there is a relationship between the playing surface and the injury/performance of National Football League (NFL) athletes and to examine factors that may contribute to lower extremity injuries. In the NFL, 12 stadiums have fields with synthetic turf.

The conclusions drawn from this analysis are as follows:
* There is a higher risk of injury when playing on the synthetic turf in all conditions except rain
* Defensive Backs tend to be at the highest risk of injury on synthetic turf
* A temperature increase is not related to an increased risk of injury

In the future, it would potentially of value to explore how player movements effect the likelihood of injury on the field.
