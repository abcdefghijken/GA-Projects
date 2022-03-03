# Project 1: Standardized Test Analysis

## Problem Statement

In the U.S., different states administer different tests for high school students to take. There are states that mandate either ACT or SAT, and there are students who would take both. However, there are states that do not require students to take either ACT or SAT. In order to foster and improve the education system, recommendations are made to discuss if a state has to mandate either ACT or SAT, or to remain as it is (to allow students to freely take both or either). The purpose of this mandate is to provide all students to have a chance to get into college admissions, and even encouraging students who have not planned ahead to have the opportunity to progress academically with at least 1 educational syllabus.

### Data Sets and Methods:

[SAT 2017](https://blog.collegevine.com/here-are-the-average-sat-scores-by-state/)
[SAT 2018](https://reports.collegeboard.org/sat-suite-program-results/state-results)
[ACT 2017](https://blog.prepscholar.com/act-scores-by-state-averages-highs-and-lows)
[ACT 2018](http://www.act.org/content/dam/act/unsecured/documents/cccr2018/Average-Scores-by-State.pdfZ)

- Outside Research
[States that Require the ACT](https://blog.collegevine.com/states-that-require-the-act/)
[States that Mandate ACT/SAT](https://testive.com/state-sat-act/)
[Good ACT Score](https://www.crimsoneducation.org/sg/blog/test-prep/good-ACT-score/#:~:text=What%20is%20considered%20a%20'good,Reading%2021.2%3B%20and%20Science%2020.6.)
[NCES](https://nces.ed.gov/programs/digest/)
- Data Import and Cleaning
- Exploratory Data Analysis
- Data Visualization
- Conclusion and Recommendations


### Data Dictionary


### Non-Merged Data Sets
|Feature|Type|Dataset|Description|
|---|---|---|---|
|state|object|ACT|The name of the State in which ACT is conducted|
|state|object|SAT|The name of the State in which SAT is conducted|
|participation|float|ACT|Participation rate of ACT|
|participation|float|SAT|Participation rate of SAT|
|composite|float|ACT|Average score of all 4 Tests (English, Math, Reading, Science)|
|english|float|ACT|Average score of the English|
|math|float|ACT|Average score of the Math|
|math|float|SAT|Average score of the Math|
|reading|float|ACT|Average score of the Reading|
|science|float|ACT|Average score of the Science|
|total|float|SAT|Average score of all 2 Tests (EBRW and Math)|
|ebrw|float|SAT|Average score of the Evidence-based Reading and Writing|

### Merged Data Sets
|Feature|Type|Dataset|Description|
|---|---|---|---|
|state|object|ACT/SAT|The name of the State in which ACT or SAT is conducted|
|act_participation|float|ACT|Participation rate of ACT|
|sat_participation|float|SAT|Participation rate of SAT|
|act_composite|float|ACT|Average score of all 4 Tests (English, Math, Reading, Science)|
|sat_ebrw|float|SAT|Average score of the Evidence-based Reading and Writing|
|sat_math|float|SAT|Average score of the Math|
|sat_total|float|SAT|Average score of all 2 Tests (EBRW and Math)|
|act_english|float|ACT|Average score of the English|
|act_math|float|ACT|Average score of the Math|
|act_reading|float|ACT|Average score of the Reading|
|act_science|float|ACT|Average score of the Science|
|participation_2017|float|ACT/SAT|Participation rate of ACT/SAT 2017|
|composite_2017|float|ACT|Average score of all 4 Tests (English, Math, Reading, Science) for year 2017|
|participation_2018|float|ACT/SAT|Participation rate of ACT/SAT 2018|
|composite_2018|float|ACT|Average score of all 4 Tests (English, Math, Reading, Science) for year 2018|
|ebrw_2017|float|SAT|Average score of the Evidence-based Reading and Writing 2017|
|math_2017|float|SAT|Average score of the Math 2017|
|total_2017|float|SAT|Average score of all 2 Tests (EBRW and Math) 2017|
|ebrw_2018|float|SAT|Average score of the Evidence-based Reading and Writing 2018|
|math_2018|float|SAT|Average score of the Math 2018|
|total_2018|float|SAT|Average score of all 2 Tests (EBRW and Math) 2018|
|act_participation_2017|float|ACT|Participation rate of ACT 2017|
|sat_participation_2017|float|SAT|Participation rate of SAT 2017|
|act_participation_2018|float|ACT|Participation rate of ACT 2018|
|sat_participation_2018|float|SAT|Participation rate of SAT 2018|
|act_composite_2017|float|ACT|Average score of all 4 Tests (English, Math, Reading, Science) 2017|
|sat_ebrw_2017|float|SAT|Average score of the Evidence-based Reading and Writing 2017|
|sat_math_2017|float|SAT|Average score of the Math 2017|
|sat_total_2017|float|SAT|Average score of all 2 Tests (EBRW and Math) 2017|
|act_english_2017|float|ACT|Average score of the English 2017|
|act_math_2017|float|ACT|Average score of the Math 2017|
|act_reading_2017|float|ACT|Average score of the Reading 2017|
|act_science_2017|float|ACT|Average score of the Science 2017|
|act_composite_2018|float|ACT|Average score of all 4 Tests (English, Math, Reading, Science) 2018|
|sat_ebrw_2018|float|SAT|Average score of the Evidence-based Reading and Writing 2018|
|sat_math_2018|float|SAT|Average score of the Math 2018|
|sat_total_2018|float|SAT|Average score of all 2 Tests (EBRW and Math) 2018|
|act_english_2018|float|ACT|Average score of the English 2018|
|act_math_2018|float|ACT|Average score of the Math 2018|
|act_reading_2018|float|ACT|Average score of the Reading 2018|
|act_science_2018|float|ACT|Average score of the Science 2018|


### Conclusion and Recommendations

### Participation Rate
<b>Histogram for SAT in 2017 and 2018</b>: The participation rate for all states are extremely high or extremely low with more states leaning towards 0%.

<b>Histogram for ACT in 2017 and 2018</b>: There are almost no changes to states that are in almost 100% participation rate. In 2017, there is a significant number of states that fall below 50%. The situation starts to get better in 2018 in which less states fall below 50%, but still within the range.

<b>Heatmap</b>: There is a strong negative correlation between participation rate. As one increases, the other tend to decreases.

<b>Scatter Plot for SAT in 2017 and 2018</b>: Evidenced by the Heatmap, the participation rate for SAT increases, the participation rate for ACT decreases. The states with higher participation rate in SAT will tend to have lower participation rate in ACT.

<b>Scatter Plot for ACT in 2017 and 2018</b>: Similarly, the participation rate for ACT increases, the participation rate for SAT decreases. The states with higher participation rate in ACT will tend to have lower participation rate in SAT.

<b>Box Plot for SAT 2017 and 2018</b>: The larger portion participate rate fall in the Q1 for SAT, indicating that the participation rate is low.

<b>Box Plot for ACT 2017 and 2018</b>: 75th - 100th percentile fall under 100% participation rate.

### Composite/Total Scores against Participation Rate
<b>Heatmap</b>: Interestingly, in <u>both years and in both tests</u>, there are <b>strong negative correlations</b> between <b>subject scores/total score and participation rate</b>. As such, from the data, it can be denoted that as the participation rate goes up, the scores will be negatively correlated.

In terms of individual subjects and total composites/scores, there is a positive correlation between them (makes sense since the individual test scores make up the total/composite).

<b>Scatter Plot for SAT Total Score against Participation Rate in 2017 and 2018</b>: Evidenced by the Heatmap, the participation rate for SAT increases, the average total score for SAT decreases. The states with higher participation rate in SAT will tend to have lower total score in SAT.

<b>Scatter Plot for ACT Composite Score against Participation Rate in 2017 and 2018</b>: Similarly, the participation rate for ACT increases, the composite score for ACT decreases. The states with higher participation rate in ACT will tend to have lower composite score in ACT.

### Composite/Total Scores

<b>Box Plot for SAT and ACT Total/Composite Score in 2017 and 2018</b>: There is a larger range for SAT test score from 2017 to 2018 in the Q3, which may suggest that states' average total score is higher than ACT.

### Recommendations
The participation rate for ACT has been performing well, which may indicate that more states are leading towards taking ACT rather than SAT.

The SAT test has a large range of average test scores, as such, it may show that students who do well in SAT will do very well and vice versa.

Even with a higher number of participation rates, ACT results have been consistent with its disparity less than SAT which may indicate that ACT has more consistency in its difficulty and grading.

Participation Rates are negative correlated and there are a number of states with mandatory ACT and SAT tests.

My recommendation is to remain as it is, as there are no benefits in mandating either ACT or SAT based on the data.

Collect more data!
<ul>
    <li>Student data - include students who take neither or both</li>
    <li>Income</li>
    <li>City level participation rate and scores</li>
</ul>

