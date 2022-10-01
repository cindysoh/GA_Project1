# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Project 1: Standardized Test Analysis

### Overview

The SAT and ACT are standardized tests that many colleges and universities in the United States require for their admissions process. This score is used along with other materials such as grade point average (GPA) and essay responses to determine whether or not a potential student will be accepted to the university.

The SAT has two sections of the test: Evidence-Based Reading and Writing and Math ([*source*](https://www.princetonreview.com/college/sat-sections)). The ACT has 4 sections: English, Mathematics, Reading, and Science, with an additional optional writing section ([*source*](https://www.act.org/content/act/en/products-and-services/the-act/scores/understanding-your-scores.html)). They have different score ranges, which you can read more about on their websites or additional outside sources (a quick Google search will help you understand the scores for each test):
* [SAT](https://collegereadiness.collegeboard.org/sat)
* [ACT](https://www.act.org/content/act/en.html)

Standardized tests have long been a controversial topic for students, administrators, and legislators. Since the 1940's, an increasing number of colleges have been using scores from sudents' performances on tests like the SAT and the ACT as a measure for college readiness and aptitude ([*source*](https://www.minotdailynews.com/news/local-news/2017/04/a-brief-history-of-the-sat-and-act/)). Supporters of these tests argue that these scores can be used as an objective measure to determine college admittance. Opponents of these tests claim that these tests are not accurate measures of students potential or ability and serve as an inequitable barrier to entry.

---

### Problem Statement

The participation rate for the state of California for ACT is significantly lower than SAT for year 2017 to 2019. This project aim to identify the relationship between the applicants, colleges and college major so that the schools in California will be able to advise high school students which test to take.

---

### Datasets

We will need to use the following datasets for analying the trend in participation rate for both SAT and ACT in the state of California:
* act_2017.csv (2017 ACT Scores by State)
* act_2018.csv (2018 ACT Scores by State)
* act_2019.csv (2019 ACT Scores by State)
* sat_2017.csv (2017 SAT Scores by State)
* sat_2018.csv (2018 SAT Scores by State)
* sat_2019.csv (2019 SAT Scores by State)
    
After understanding the trend, we can deep dive into the school in California and the number of test taker versus enrolled. We will be using:
* act_2019_ca.csv (2019 ACT Scores in California by School)
* sat_2019_ca.csv (2019 SAT Scores in California by School)
    
We will then use the test taker's score to identify which major and college will be have a higher success rate from taking SAT or ACT. We will be using:
* sat_2019_by_intended_college_major.csv (2019 SAT Scores by Intended College Major)
* sat_act_by_college.csv (Ranges of Accepted ACT & SAT Student Scores by Colleges)

---

### Data Dictionary

#### 1. 'act_cali.csv' This dataset shows ACT test data for State of California from year 2017 to 2019

|Feature|Type|Dataset|Description|
|---|---|---|---|
|state|object|act_cali|Name of the State in America|
|participation_rate|float|act_cali|The percentage of test takers over graduates<br> (units percent to two decimal places 0.31 means 31%)|
|composite|float|act_cali|Mean ACT Composite score|
|year|object|act_cali|The year of the ACT Test|

#### 2. 'sat_cali.csv' This dataset shows SAT test data for State of California from year 2017 to 2019

|Feature|Type|Dataset|Description|
|---|---|---|---|
|state|object|sat_cali|Name of the State in America|
|participation_rate|float|sat_cali|The percentage of test takers over graduates<br> (units percent to two decimal places 0.53 means 53%)|
|ebrw|int|sat_cali|Mean SAT Evidence-Based Reading & Writing score|
|math|int|sat_cali|Mean SAT Math score|
|total|int|sat_cali|Total SAT score of both Evidence-Based Reading & Writing<br> and Math score|
|year|object|sat_cali|The year of the SAT Test|

#### 3. 'act19ca.csv' This dataset shows ACT test data for State of California for year of 2019 with school, district and county details.

|Feature|Type|Dataset|Description|
|---|---|---|---|
|cds|int|act19ca|This 14-digit code is the official, unique identification of a school within California.<br> The first two digits identify the county, the next five digits identify the school district,<br> and the last seven digits identify the school.|
|rtype|object|act19ca|The type of record. S is school record, D is district record, C is county record, X is state record.|
|school|object|act19ca|Name of the school in State of California|
|district|object|act19ca|Name of the district the school is in|
|county|object|act19ca|Name of the county the school district is in|
|enrolled|int|act19ca|The number of graduates that enrolled in ACT Test for year 2019|
|testtakers|int|act19ca|The number of graduates that participate in ACT Test for year 2019|
|reading_avg|int|act19ca|Mean ACT Reading score|
|english_avg|int|act19ca|Mean ACT English score|
|math_avg|int|act19ca|Mean ACT Math score|
|science_avg|int|act19ca|Mean ACT Science score|
|graduate_number_21|int|act19ca|The number of graduates score 21 and above|
|graduate_percentage_21|int|act19ca|The percentage of graduates score 21 and above|

#### 4. 'sat19ca.csv' This dataset shows SAT test data for State of California for year of 2019 with school, district and county details.

|Feature|Type|Dataset|Description|
|---|---|---|---|
|cds|int|sat19ca|This 14-digit code is the official, unique identification of a school within California.<br> The first two digits identify the county, the next five digits identify the school district,<br> and the last seven digits identify the school.|
|rtype|object|sat19ca|The type of record. S is school record, D is district record, C is county record, X is state record.|
|school|object|sat19ca|Name of the school in State of California|
|district|object|sat19ca|Name of the district the school is in|
|county|object|sat19ca|Name of the county the school district is in|
|enrolled|int|sat19ca|The number of graduates that enrolled in SAT Test for year 2019|
|testtakers|int|sat19ca|The number of graduates that participate in SAT Test for year 2019|
|erw_number_bm|int|sat19ca|The number of participant that score above benchmark in Evidence-Based Reading & Writing<br> of Grade 12 students|
|erw_percent_bm|float|sat19ca|The percentage of participant that score above benchmark in Evidence-Based Reading & Writing<br> of Grade 12 students (units percent to two decimal places 30.39 means 30.39%)|
|math_number_bm|int|sat19ca|The number of participant that score above benchmark in Math of Grade 12 students|
|math_percent_bm|float|sat19ca|The percentage of participant that score above benchmark in Math of Grade 12 students<br> (units percent to two decimal places 13.73 means 13.73%)|
|total_number_bm|int|sat19ca|The number of participant that score above benchmark in both Evidence-Based Reading & Writing<br> and Math of Grade 12 students|
|total_percent_bm|int|sat19ca|The percentage of participant that score above benchmark in both Evidence-Based Reading & Writing<br> and Math of Grade 12 students (units percent to two decimal places 13.73 means 13.73%)|

#### 5. 'sat19_col.csv' This dataset shows SAT score in relevance to the intended college major for year 2019

|Feature|Type|Dataset|Description|
|---|---|---|---|
|college_major|object|sat19_col|List of the intended college major|
|testtakers|int|sat19_col|The number of test takers for the particular college major|
|percent|float|sat19_col|The percantage of test takers for the particular college major out of all the test takers in 2019<br> (units percent to two decimal places 0.01 means 1%)|
|total|int|sat19_col|Total SAT score of both Evidence-Based Reading & Writing and Math score for the particular college major|
|readingwriting|int|sat19_col|Mean SAT Evidence-Based Reading & Writing score for the particular college major|
|math|int|sat19_col|Mean SAT Math score for the particular college major|

#### 6. 'sat_act_col.csv' This dataset shows the ranges of accepted ACT & SAT Student Scores by Colleges

|Feature|Type|Dataset|Description|
|---|---|---|---|
|school|object|sat_act_col|List of colleges|
|test_optional|object|sat_act_col|'Yes' or 'No' value. Yes, if the particular college has adopt test optional policy|
|test_optional_year|object|sat_act_col|For school that are test optional. List of year(s) that the school will adopt<br> test optional policy, or remain permanent|
|policy_details|object|sat_act_col|The detail of school test optional policy|
|number_of_applicants|int|sat_act_col|The number of applicants for each school|
|accept_rate|int|sat_act_col|The accptance rate for each school<br> (units percent to three decimal places 0.043 means 4.3%)|
|sat_low|float|sat_act_col|The range of SAT total score within the lower percentile|
|sat_high|float|sat_act_col|The range of SAT total score within the higher percentile|
|act_low|float|sat_act_col|The range of ACT total score within the lower percentile|
|act_high|float|sat_act_col|The range of ACT total score within the higher percentile|

---

### Conclusion and Recommendation

From our findings and analysis, we can deduce that the decrease in trend for state of California participation rate in ACT test might be due to the fact that the average composite of ACT test from state of California is 21.3 which then shows only 29 county out of 57 manange to secure more than average number of college. 

SAT test in 2019 show that the state of California did better in ERW rather than Math which effected the total benchmark percentage. Although this might be troubling, but we still see an upside in participation rate. This might be due to the fact that 28 out of 38 colleges majors accept students with lower ERW score, rather than Math. Thus they would have more option and higher chance of getting the major of their choice.

In order to be secure above average number of college, for ACT participant is it recommended to score at least 27.3 and for SAT test at least 1263. On top of the, if participant has a particular major in mind that has a lower benchmark for ERW, it is safe to say that the recommended test will be SAT Test.


---

### Other Resources

ACT Sample Data: https://www.act.org/content/dam/act/unsecured/documents/2021-2022-Student-Rpt-with-Write-sample-data.pdf 
<br>
SAT Benchmarks: https://www.nwea.org/content/uploads/2020/10/MAP-SAT-College-Readiness-Benchmarks_NWEA_linkingstudy.pdf
<br>
SAT Benchmarks: https://www.nwea.org/content/uploads/2020/10/MAP-College-Readiness-Benchmarks-Research-Brief.pdf
<br>
California school/district filling structure: https://www.cde.ca.gov/ds/si/ds/fspubschls.asp
<br>
Good SAT score in 2020? article: https://blog.collegevine.com/what-is-a-good-sat-score-in-2020/
<br>
College & Career Readiness 2019 California: https://www.act.org/content/dam/act/unsecured/documents/cccr-2019/California-CCCR-2019.pdf
<br>
ACT Scores and Participation Rates: https://www.act.org/content/dam/act/unsecured/documents/Statewide-Adoption.pdf
<br>

---