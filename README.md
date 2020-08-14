# Philadelphia School District Retention

Report using observational data on a teacher intervention

## Data Cleaning Notes

Data kept private due to NDA

## Packages

* [Tidyverse](https://cran.r-project.org/web/packages/tidyverse/tidyverse.pdf)
* [MatchIt](https://cran.r-project.org/web/packages/MatchIt/index.html)


## Logistic Regression

Phase 1 began with a visualization and descriptive analysis of the breakdown of teacher strata and retention. After that, we analyzed the significance of participation in TIP on retention through a logistic regression. Participating in TIP is associated with an increase in the log odd likelihood of retention. Specifically, the coefficient was .35, meaning that participating in TIP was associated with a .35 increase in retention.

## Causal Analysis

In Phase 2, we add rigor to the logistic regression by asking if there is a causal relationship between participation in TIP and retention. We match teachers based on available and measured covariates, such as years in the classroom, gender, or title (classroom teacher or administration). By matching, we reduce the chance that these factors (whether or not the teacher is a male or female, for instance) explain retention. Instead, the variable of causal interest (whether or not the teacher participated in the intervention) is isolated. </br>
We spent ample time exploring the differences in groups for each measured covariates, since the goal of balancing will depend on the raw differences in the sample size representation of each of these covariates. Appendix A includes differences in covariate groups among TIP and non-TIP teachers. The impacts of each covariate on the percent balance improvement among TIP and non-TIP teachers was considered, and in the end we chose to trim the sample to include only the ages of teachers who participated in TIP. </br>
To be more specific, certain ages of teachers are represented in the non-TIP sample, yet not represented in the Treatment (TIP) sample. The ages that are not represented in the TIP samples are: 32, 38, and 40+. Especially in the context of our study, where the question of interest is teacher retention, then an important confounder of staying in the classroom is age of the teacher. Therefore, matching on age without taking into account these non-representative ages may affect the balance allowed on other variables (specifically gender and ethnicity). 300 non-participating teachers were not matched in the age of the TIP participating teachers. </br>
Trimming the sample has the effect of improving percent balance improvement for Gender and the other category of Ethnicity. In fact, all of the variables now have sufficient percent balance improvement. Appendix A includes the original matching model with all covariates included, and describes how the percent balance improvement informed the selection of covariates in our final matching model, presented below. This final model includes the trimmed TIP sample so
8
that we only include TIP teachers with Years of experience that are matched in the other sample of non-TIP teachers.


## Discussion
Teacher
retention is a much studied topic , and programs like TIP, which enable teachers to pursue
university-level study, thereby bringing new content to students and increasing teachers’ morale, are rooted in the mission to keep teachers helping those students who need them most. Both authors of this study were public school teachers themselves, and know that “intellectual engagement” is certainly as important as “purpose” in a career. One possible explanation behind the increased retention of teachers who participate in TIP may by this intellectual engagement that the program offers.
There remains unanswered questions in this domain that the TIP organization can continue to pursue and work to address. Specifically, what are the outcomes of teachers who do leave the district, after participating in TIP? Our study was limited to a binary variable of retained or not retained. This lacks a very important other possibility, which is that teachers left their role in SDP to pursue other intellectually engaging and purpose driven opportunities, such as a doctorate in education or starting their own computer programming boot-camp for minority students in Philadelphia. It is hard to argue that these teachers are contributing to educational inequity by leaving their classroom positions. TIP can continue to reach out to teachers who leave to learn qualitatively about the specifics of roles that former teachers are pursuing outside of the classroom role, and whether or not participating in TIP actually encouraged them to seek these roles that are equally as influential as the work of a classroom teacher.
