## 1. Abstract
Recent investigations of lower limb injuries among football athletes have indicated significantly higher injury rates on synthetic turf compared to natural turf (Mack et al., 2018; Loughran et al., 2019). In conjunction with epidemiologic investigations, biomechanical studies of football cleat-surface interactions have shown that synthetic turf surfaces do not release cleats as readily as natural turf, which may contribute to the incidence of non-contact lower limb injuries (Kent et al., 2015). Given these differences in cleat-turf interactions, it has yet to be determined whether other measures of player performance differ across playing surfaces and how these may contribute to lower limb injury.

The goal of this project is to investigate the relationship between playing surfaces and the injury and performance of National Football League (NFL) athletes, and to examine factors that may contribute to lower extremity injuries. In the NFL, 12 stadiums currently utilize synthetic turf.

## 2. Exploratory Data Analysis (EDA)
This section focuses on understanding the structure, quality, and scope of three datasets:

* Injury Record: This .csv file contains information on 105 lower-limb injuries that occurred during regular-season games over two seasons. Injuries are linked to specific player history records using the PlayerKey, GameID, and PlayKey fields.

* Play List: This file contains details for the 267,005 player-plays in the dataset. Each play is indexed by PlayerKey, GameID, and PlayKey. Details include the player’s assigned roster position, stadium type, field type, weather, play type, and position group.

* Player Track Data: This player-level data describes the location, orientation, speed, and direction of each player during a play, recorded at 10 Hz (i.e., 10 observations per second).

This analysis identifies unique players, games, and plays, then reshapes the data into a cleaner game-level format. Environmental variables—such as stadium type, temperature, and weather—are standardized to ensure consistency, preparing the dataset for reliable visualization and modeling.
## 3. Visualizations
A variety of visualizations were generated to showcase the relationships between player injuries and various factors, such as environmental conditions and play types. Spatial heatmaps illustrate where players spend the most time on the field and where injuries most frequently occur. Additional plots explore injury counts, injury locations, and player timelines leading up to injury events, providing intuitive visual context for the subsequent statistical findings.
<img width="468" height="208" alt="image" src="https://github.com/user-attachments/assets/f164d68e-95fc-4b58-bb05-6ae407edcca9" />
<img width="468" height="185" alt="image" src="https://github.com/user-attachments/assets/fc47fd07-9141-44b9-81c9-8b820e55c2d7" />
<img width="327" height="217" alt="image" src="https://github.com/user-attachments/assets/c1632b84-b99a-43ed-9ebd-affc39edd31f" />
<img width="1251" height="702" alt="image" src="https://github.com/user-attachments/assets/4a047985-82e6-466d-a9f0-6c140ba32888" />
<img width="740" height="451" alt="image" src="https://github.com/user-attachments/assets/32b283fa-ffdf-4711-a3e1-4e0f02cc2932" />

## 4. Statistical Analysis of Player Injuries
This section transitions from visual insights to the quantitative analysis of player injuries. After preparing modeling-ready datasets, correlations were examined between injuries and environmental factors (e.g., temperature and stadium type), as well as the number of games played and play types. However, no significant correlations were found.

Hypothesis testing was also used to evaluate whether injury risk differs significantly between natural grass and synthetic turf. The results failed to reject the null hypothesis: the likelihood of a player experiencing an injury on natural grass is less than or equal to the probability of injury on synthetic turf.

## 4. Machine Learning – Predicting Player Injury
A predictive modeling pipeline was developed to estimate the likelihood of player injury and to determine the important features that contribute to it. First, the merged injury and play list datasets were split into training and test sets using a stratified fold method to ensure an even distribution of class labels. Because injuries are relatively rare events, the data was resampled before being trained using an XGBoost classifier. Although the model underperformed in predictive accuracy, it was used to determine feature importance, identifying key variables such as environmental conditions and player usage.

<img width="1610" height="849" alt="image" src="https://github.com/user-attachments/assets/85e2e23d-557b-4a10-ba6a-ec3203d57951" />

## 5. Synthetic vs Natural Turf Analysis
Building on the finding that there is limited statistical evidence for surface-only injury risk, this section dives deeper into how turf type interacts with other conditions. It compares injury rates on natural and synthetic surfaces under varying weather and temperature scenarios, including specific hypothesis tests for rainy conditions. The analysis also examines whether certain player positions are more affected by synthetic turf. The findings indicated that Defensive Backs experience injuries at a significantly higher rate on synthetic turf compared to other positions.
<img width="1251" height="702" alt="image" src="https://github.com/user-attachments/assets/f5aef7a3-8476-4125-9680-3039919d4f91" />


## 7. Conclusion
The goal of this analysis was to determine if a relationship exists between playing surfaces and the injury or performance of NFL athletes.


The conclusions drawn from this analysis are as follows:
* There is a higher risk of injury when playing on synthetic turf in all conditions except rain.
* Defensive Backs tend to be at the highest risk of injury on synthetic turf.
* Increased temperature is not significantly related to an increased risk of injury.

In the future, it would be valuable to explore how specific player movement patterns (kinematics) affect the likelihood of injury on the field.
