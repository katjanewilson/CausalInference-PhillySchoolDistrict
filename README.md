# Philadelphia School District Retention

Trending videos on YouTube do not simply increase viewership, they also inspire new content and engagement from creators. With such a large and diverse dataset of videos, product teams rely on unsupervised learning methods to find similar features among trending videos. Using a large dataset of YouTube videos, we explore trends to guide the marketing team.


<p align="center">
<img src="https://github.com/katjanewilson/WhartonAnalytics-YouTube/blob/master/images/youtube_logo.png"
  alt="Size Limit comment in pull request about bundle size changes"
  width="400" height="200">
</p>

## Data

The initial data set consisted of 16,013 unique, 7,014 of whom we have information on exiting the school system. A total of 356 unique teachers who participated in TIP. After checking for missing data, 4 observations in teacher exits were coded as duplicates, and 2 observations in the TIP participation variables set were duplicates. Of the demographic variables, 43 observations were NA (missing). Of the total teachers set, 32 observations were NA. After removing the NA values, the analytic file included 16,005 unique teachers.
Upon merging the datasets, it became apparent that some unique teacher IDs were present in certain datasets but missing from others. Specifically, using the anti-merge function in our code, we can see the observations that are included in the information on exits but not in the information on total teachers. There are 1,067 teachers who exited, and who were also missing from the total teachers data. We removed these missing values from the merge of teacher exits with the total teachers.
We proceeded to merge the deidentified TIP IDs with the complete teachers file. Of the TIP participants, 44 unique teachers were missing from the total teachers set. This brings our final number of unique teachers who participated in TIP (with complete covariate information) down from 358 to 314. After removing two duplicates, the final number of unique TIP participants in the dataset is 312.
In the descriptive statistics and statistical analyses below, we use a final analytic file that consists of 16,005 teachers, of which 312 participated in TIP. This information is based on the 8-year period from 2010 – 2018.
Variable Definitions
For each teacher in the dataset, we created the indicator variable, “Participated,” that equals 1 for a TIP participant and 0 otherwise. The outcome variable of interest is the binary indicator, “Retained,” which is equal to 1 if the teacher remained in SDP for the duration of the study period and 0 otherwise. Additionally, we created variables that tracked the number of times a teacher changed schools, changed titles, etc., but remained within SDP. Because there were 9 observations with missing gender information, the following statistical models were run on a sample of 16,003 teachers, of whom 312 participated in TIP.


## Packages

* [Tidyverse](https://cran.r-project.org/web/packages/tidyverse/tidyverse.pdf)
* [MatchIt](https://cran.r-project.org/web/packages/ClusterR/ClusterR.pdf)

## How It Works

1. 

2.

3.

## Logistic Regression

Phase 1 began with a visualization and descriptive analysis of the breakdown of teacher strata and retention. After that, we analyzed the significance of participation in TIP on retention through a logistic regression. Participating in TIP is associated with an increase in the log odd likelihood of retention. Specifically, the coefficient was .35, meaning that participating in TIP was associated with a .35 increase in retention.

## Causal Analysis

In Phase 2, we add rigor to the logistic regression by asking if there is a causal relationship between participation in TIP and retention. We match teachers based on available and measured covariates, such as years in the classroom, gender, or title (classroom teacher or administration). By matching, we reduce the chance that these factors (whether or not the teacher is a male or female, for instance) explain retention. Instead, the variable of causal interest (whether or not the teacher participated in the intervention) is isolated.
We spent ample time exploring the differences in groups for each measured covariates, since the goal of balancing will depend on the raw differences in the sample size representation of each of these covariates. Appendix A includes differences in covariate groups among TIP and non-TIP teachers. The impacts of each covariate on the percent balance improvement among TIP and non-TIP teachers was considered, and in the end we chose to trim the sample to include only the ages of teachers who participated in TIP.
To be more specific, certain ages of teachers are represented in the non-TIP sample, yet not represented in the Treatment (TIP) sample. The ages that are not represented in the TIP samples are: 32, 38, and 40+. Especially in the context of our study, where the question of interest is teacher retention, then an important confounder of staying in the classroom is age of the teacher. Therefore, matching on age without taking into account these non-representative ages may affect the balance allowed on other variables (specifically gender and ethnicity). 300 non-participating teachers were not matched in the age of the TIP participating teachers.
Trimming the sample has the effect of improving percent balance improvement for Gender and the other category of Ethnicity. In fact, all of the variables now have sufficient percent balance improvement. Appendix A includes the original matching model with all covariates included, and describes how the percent balance improvement informed the selection of covariates in our final matching model, presented below. This final model includes the trimmed TIP sample so
8
that we only include TIP teachers with Years of experience that are matched in the other sample of non-TIP teachers.


## Evaluation

## Discussion

In conjunction with Phase 1 of the study, Phase 2 implies that participation in TIP may have a causal effect on the retention of teachers in the Philadelphia school district, when teachers are matched on the measured covariates. All else things being equal that are associated with retention (gender, ethnicity, age, years in the classroom, and title), then those who participate in TIP are more likely to be retained, within the time period of our study. Limitations to this conclusion include the small sample size of TIP participants, and a myriad of other confounders that could have been measured.
In broader implications of the study, we first consider the associations in ethnicity found in Phase 1 that may be of interest to certain minority groups. From a psychological standpoint, students who have a teacher who “looks like them” (such as similar gender or Ethnicity) are predicted to build stronger relationships in the classroom, and relationship building is frequently tied to academic performance and interest. One study looked at this so called “Teacher Match” on students’ academic perceptions and attitudes. The study found that demographically similar teachers, “especially in gender matches” are significant in the quality of student-teacher
1
Further research would likewise do well to explore this interaction between ethnicity, age, and gender. White teachers are more represented in the 20s and 30s group of teachers than non-white teachers (about 23% of teachers in their 20s are nonwhite, and 26% of teachers in their 20s are
1
communication and college aspiration.
reducing disparities in education among certain ethnic and gender groups, then better understanding how different programs lead to disparate outcomes of retention for different groups of teachers (gender/ethnicity) would be an important next step for TIP.
If retaining those groups of teachers is a driver in
  Egalite, Anna J., and Brian Kisida. "The effects of teacher match on students’ academic
 perceptions and attitudes." Educational Evaluation and Policy Analysis 40.1 (2018): 59-81.
9
non-white, while 75% of teachers in their 50s are non-white), but the limitations of this study in sample size of ethnicity and gender prevent that question from being directly addressed.
A second broader implication is from the teacher, rather than the student, perspective. Teacher
23
retention is a much studied topic , and programs like TIP, which enable teachers to pursue
university-level study, thereby bringing new content to students and increasing teachers’ morale, are rooted in the mission to keep teachers helping those students who need them most. Both authors of this study were public school teachers themselves, and know that “intellectual engagement” is certainly as important as “purpose” in a career. One possible explanation behind the increased retention of teachers who participate in TIP may by this intellectual engagement that the program offers.
There remains unanswered questions in this domain that the TIP organization can continue to pursue and work to address. Specifically, what are the outcomes of teachers who do leave the district, after participating in TIP? Our study was limited to a binary variable of retained or not retained. This lacks a very important other possibility, which is that teachers left their role in SDP to pursue other intellectually engaging and purpose driven opportunities, such as a doctorate in education or starting their own computer programming boot-camp for minority students in Philadelphia. It is hard to argue that these teachers are contributing to educational inequity by leaving their classroom positions. TIP can continue to reach out to teachers who leave to learn qualitatively about the specifics of roles that former teachers are pursuing outside of the classroom role, and whether or not participating in TIP actually encouraged them to seek these roles that are equally as influential as the work of a classroom teacher.
