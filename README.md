<p align="center">
  <img src="https://user-images.githubusercontent.com/23629340/40541063-a07a0a8a-601a-11e8-91b5-2f13e4e6b441.png" alt="Ironhack" />
</p>


# FIFA Moneyball

<!-- ABOUT THE PROJECT -->


### The Project

You are a team of scouts at Ironhack FC. You have been tasked with examining the attached dataset to understand which attributes are the best predictors of a football player's potential so that the club can sign future stars. Because the Chairman of Ironhack FC is a busy person, they have requested that you provide your findings in a short 10 minute presentation. The Chairman doesn't understand anything about coding, so has requested that there is no code shown in the presentation. Finally, the Chairman has asked you to provide the top three players that your model recommends signing under a budget of $100M.

### Objectives

Ask interesting and thoughtful questions and find the data to answer them.
Apply the statistical techniques we have learned.
Create multiple models and compare them, so that you can convince the Chairman that your final model is the best. 
Create useful and clear graphs.
5 min presentation in powerpoint/google slides

### Dataset

`fifa_train_data.csv` -> [Players full information](https://drive.google.com/file/d/135VtRTHscOmS7Nmy48kYkbxj_dUONfcI/view)

`fifa_test_data.csv` -> [Players to buy](https://drive.google.com/file/d/1Jo-wcoxOpbGkKZxHiowkBApyTXmOv1Gf/view)

### Summary

After cleaning the data, we were able to see the differences between the two datasets. 

* `bov` 
* `ova`
* `pot`

These three columns are found in `fifa_train_data.csv`, but not in `fifa_test_data.csv`.
With this information, `ova` was chosen as the base. 
We looked for categorical data that could be related to OVA. After finding, they were converted to numerical data. Columns that don't need to be analysed were removed (id, bov, pot).
Within each position, we examined columns yielding the best results and applied the linear regression model. Subsequently, we made predictions by filtering within the `buy_data` by position.
We aggregated the results from all positions to consolidate our findings.

We have developed a function to sort players in descending order based on their OVA predictions. This function initializes variables to track selected players and total cost. It iterates through the sorted DataFrame, checks if adding the player exceeds the budget, adds them to the list of selected players, updates the total cost, checks if we've selected three players, and finally converts the list of selected players into a DataFrame.

#### Our 3 Players

|   ID   |     Name    |   OVA  |  Country  |          Club            |  Position  |  Value  |
| ------ | ----------- | ------ | --------- | ------------------------ | ---------- | ------- |
| 216409 | M. Politano |   81   |   Italy   |           Napoli         |     RM     |   19M   |
| 211147 | V. Lazaro   |   80   |  Austria  | Borussia Mönchengladbach |     RM     |   16M   |
| 220477 | M. Caldara  |   79   |   Italy   |        Atalanta          |     CB     |   12M   | 

#### Total 47M
