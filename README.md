# How-to-Reshape-Conjoint-Data
## Repository Description 
This repository serves as a tutorial for how to take survey data (from Qualtrics, for example) and reshape it to be compatible with `cjoint`. This tutorial uses simulated data taken from an experiment by S.R. Gubitz.

### The Data
The data are from a study on incivility by S.R. Gubitz. The simulated data are available for practice in this repository. I will keep this repository updated with the status of this paper as it progresses through the publication pipeline. 
<br><br>
This conjoint was programmed by Gubitz in Qualtrics, using survey flow and pipe text in order to create a conjoint design. This is not a typical conjoint, as there was no force choice design involved, but the reshaping process is similar. 

#### Data set-up 
To aid the reshaping process, it helps to recode the data columns using a systematic naming convention. I have found that the best convention is as follows: `variablename_taskiteration_index`. Take, for example, education of a candidate in a hypothetical conjoint design. For each task, we would code the variable as: `education_1`, `education_2`, `education_3`, until the last task. 
<br><br>
This coding scheme should also be used for respondent *answers* in each task iteration. For instance, if the respondent is asked to pick between two candidates, this variable should be coded: `choice_1`, `choice_2`, `choice_3`, until the last task. 
<br><br>
If the respondent is answering a *battery* of questions related to the candidate for each iteration, this variable can be captured in the `index` portion of the `variablename_taskiteration_index` scheme. For instance, if the respondent is asked in each iteration three questions on the leadership qualities of a candidate, this should be coded: `leadership_1_1`, `leadership_1_2`, `leadership_1_3`, for the first iteration. In the second iteration, it would be, `leadership_2_1`, `leadership_2_2`, and `leadership_2_3`. This pattern continues until the last iteration. 
<br><br>
It does not matter if one decides to recode the variables in this manner on the actual survey (i.e. in Qualtrics), or if one desides to do it in R. However, this format is essential for the following reshaping process. 

#### Reshaping 
