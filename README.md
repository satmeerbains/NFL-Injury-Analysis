## 1. Abstract
Recent investigations of lower limb injuries among football athletes have indicated significantly higher injury rates on synthetic turf compared with natural turf (Mack et al., 2018; Loughran et al., 2019). In conjunction with the epidemiologic investigations, biomechanical studies of football cleat-surface interactions have shown that synthetic turf surfaces do not release cleats as readily as natural turf and may contribute to the incidence of non-contact lower limb injuries (Kent et al., 2015). Given these differences in cleat-turf interactions, it has yet to be determined whether player movement patterns and other measures of player performance differ across playing surfaces and how these may contribute to the incidence of lower limb injury. 

The goal of this project is to investigate the relationship between the playing surface and the injury and performance of National Football League (NFL) athletes and to examine factors that may contribute to lower extremity injuries. In the NFL, 12 stadiums have fields with synthetic turf.


## 2. Exploratory Data Analysis (EDA)
This section focuses on understanding the structure, quality, and scope of the data. It identifies the number of unique players, games, and plays, then reshapes the data into a cleaner game-level format. Environmental variables such as stadium type, temperature, and weather conditions are standardized and cleaned to ensure consistency. These steps prepare the dataset for reliable visualization and modeling.

## 3. Visualizations
A variety of visualizations are used to reveal patterns in gameplay and injuries. The analysis looks at how games are distributed across different environments and weather conditions, how player workload varies by position, and how different play types are represented. Spatial heatmaps show where players spend the most time on the field and where injuries most frequently occur. Additional plots explore injury counts, injury locations, and player timelines leading up to injury events, providing intuitive visual context for later statistical findings.
<img width="468" height="208" alt="image" src="https://github.com/user-attachments/assets/f164d68e-95fc-4b58-bb05-6ae407edcca9" />


## 4. Statistical Analysis of Player Injuries
This section transitions from visual insights to quantitative analysis. After preparing modeling-ready datasets, correlations are examined between injuries and environmental factors like temperature and stadium type, as well as play characteristics and cumulative workload. Formal hypothesis testing is used to evaluate whether injury risk differs significantly between natural grass and synthetic turf, providing statistical backing for observed trends.

## 4. Machine Learning – Predicting Player Injury
A predictive modeling pipeline is developed to estimate the likelihood of player injury. Features are engineered from gameplay, environmental conditions, and player usage. Because injuries are relatively rare events, resampling techniques are applied to address class imbalance. An XGBoost classifier is trained and evaluated, and feature importance analysis highlights which variables contribute most strongly to injury prediction.

## 5. Synthetic vs Natural Turf Analysis

This focused section dives deeper into how turf type interacts with other conditions. It compares injury rates on natural and synthetic surfaces under varying weather and temperature scenarios, including specific hypothesis tests for rainy conditions. The analysis also examines whether certain player positions are more affected by synthetic turf, helping clarify how surface type and context combine to influence injury risk.

## 7. Conclusion
The project concludes by summarizing key findings from the visual, statistical, and machine learning analyses. It highlights the environmental and gameplay factors most associated with injuries and discusses how these insights could inform player safety strategies, field management decisions, and future research into injury prevention.
