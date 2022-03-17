# Project 2 - Ames Housing Data and Kaggle Challenge

<h3>Problem Statement:</h3>
    <li>Predict the price of homes at sale for the Ames Iowa Housing dataset.</li>
    <li>Based on model, find out the top features affecting prices.</li>
    
<h3>Content:</h3>
<ul>
    <li>Overview</li>  
    <li>Data Dictionary</li>   
    <li>Checking of Null Values</li>   
    <li>Exploratory Data Analysis</li>   
    <li>Data Cleaning</li>   
    <li>Feature Engineering</li>   
    <li>Modelling</li>   
    <li>Conclusion</li>   
    <li>Kaggle Submission</li>   
</ul>

<center><h1>Data Dictionary</h1></center><BR>
    <p>A list of columns used from the .csv. Data types and descriptions about columns are displayed.</p>
    <li>http://jse.amstat.org/v19n3/decock/DataDocumentation.txt</li>

|Feature|Type|Description|
|---|---|---|
 |PID          |int64  |Parcel identification number  - can be used with city web site for parcel review.|
 |Ms Subclass  |int64  |Identifies the type of dwelling involved in the sale.|
 |Ms Zoning    |object |Identifies the general zoning classification of the sale.|
 |Lot Frontage |float64|Linear feet of street connected to property.|
 |Lot Area     |int64  |Lot size in square feet.|
 |Street       |object |Type of road access to property.|
 |Alley        |object |Type of alley access to property.|
 |Lot Shape    |object |General shape of property.|
 |Land Contour |object |Flatness of the property.|
 |Utilities    |object |Type of utilities available.|
 |Lot Config   |object |Lot configuration.|
 |Land Slope   |object |Slope of property.|
 |Neighborhood |object |Physical locations within Ames city limits (map available).|
 |Condition 1  |object |Proximity to various conditions.|
 |Condition 2  |object |Proximity to various conditions (if more than one is present).|
 |Bldg Type    |object |Type of dwelling.|
 |House Style  |object |Style of dwelling.|
 |Overall Qual |int64  |Rates the overall material and finish of the house.|
 |Overall Cond |int64  |Rates the overall condition of the house.|
 |Year Built   |int64  |Original construction date.|
 |Year Remod/Add|int64  |Remodel date (same as construction date if no remodeling or additions).|
 |Roof Style   |object |Type of roof.|
 |Roof Matl    |object |Roof material.|
 |Exterior 1st |object |Exterior covering on house.|
 |Exterior 2nd |object |Exterior covering on house (if more than one material).|
 |Mas Vnr Type |object |Masonry veneer type.|
 |Mas Vnr Area |float64|Masonry veneer area in square feet.|
 |Exter Qual   |object |Evaluates the quality of the material on the exterior.|
 |Exter Cond   |object |Evaluates the present condition of the material on the exterior.|
 |Foundation   |object |Type of foundation.|
 |Bsmt Qual    |object |Evaluates the height of the basement.|
 |Bsmt Cond   |object |Evaluates the general condition of the basement.|
 |Bsmt Exposure|object |Refers to walkout or garden level walls.|
 |BsmtFin Type 1|object |Rating of basement finished area.|
 |BsmtFin SF 1 |float64|Type 1 finished square feet.|
 |BsmtFin Type 2|object |Rating of basement finished area (if multiple types).|
 |BsmtFin SF 2 |float64|Type 2 finished square feet.|
 |Bsmt Unf SF  |float64|Unfinished square feet of basement area.|
 |Total Bsmt SF|float64|Total square feet of basement area.|
 |Heating      |object |Type of heating.|
 |Heating QC   |object |Heating quality and condition.|
 |Central Air  |object |Central air conditioning.|
 |Electrical   |object |Electrical system.|
 |1st Flr SF   |int64  |First Floor square feet.|
 |2nd Flr SF   |int64  |Second Floor square feet.|
 |Low Qual Fin SF|int64  |Low quality finished square feet (all floors).|
 |Gr Liv Area  |int64  |Above grade (ground) living area square feet.|
 |Bsmt Full Bath|float64|Basement full bathrooms.|
 |Bsmt Half Bath|float64|Basement half bathrooms.|
 |Full Bath    |int64  |Full bathrooms above grade.|
 |Half Bath    |int64  |Half bathrooms above grade.|
 |Bedroom AbvGr|int64  |Bedrooms above grade (does NOT include basement bedrooms).|
 |Kitchen AbvGr|int64  |Kitchens above grade.|
 |Kitchen Qual |object |Kitchen quality.|
 |TotRms AbvGrd|int64  |Total rooms above grade (does not include bathrooms).|
 |Functional   |object |Home functionality (Assume typical unless deductions are warranted).|
 |Fireplaces   |int64  |Number of fireplaces.|
 |Fireplace Qu |object |Fireplace quality.|
 |Garage Type  |object |Garage location.|
 |Garage Yr Blt|float64|Year garage was built.|
 |Garage Finish|object |Interior finish of the garage.|
 |Garage Cars  |float64|Size of garage in car capacity.|
 |Garage Area  |float64|Size of garage in square feet.|
 |Garage Qual  |object |Garage quality.|
 |Garage Cond  |object |Garage condition.
 |Paved Drive  |object |Paved driveway.|
 |Wood Deck SF |int64  |Wood deck area in square feet.|
 |Open Porch SF|int64  |Open porch area in square feet.|
 |Enclosed Porch|int64  |Enclosed porch area in square feet.|
 |3Ssn Porch   |int64  |Three season porch area in square feet.|
 |Screen Porch |int64  |Screen porch area in square feet.|
 |Pool Area    |int64  |Pool area in square feet.|
 |Pool QC      |object |Pool quality.|
 |Fence        |object |Fence quality.|
 |Misc Feature |object |Miscellaneous feature not covered in other categories.|
 |Misc Val     |int64  |$ Value of miscellaneous feature.|
 |Mo Sold      |int64  |Month Sold (MM).|
 |Yr Sold      |int64  |Year Sold (YYYY).|
 |Sale Type    |object |Type of sale.|
 |SalePrice    |int64  |Sale price $$.|

## Checking of Null Values

### Notable Columns: Alley, Pool QC, Fence, Misc Feature and Fireplace QC, PID, Id
Since the data set has 2000+ rows in total, it might be safe to drop columns with too many null values. However, we would need to gather the meaning of these missing values to safely assume we would not require them. Further analysis would be made to ensure that missing values are not neglected, it will be done at a later stage.

<center><h3>Things to take note of</h3></center><br>
Columns like <code>Alley</code>, <code>Fireplace Qu</code> have LOTS of missing values in both data frames. For smaller quantities in <code>Total Bsmt SF</code>, <code>Garage Cars</code>, we could safely replace these rows with values from other rows.
    
<center><h2>Identifying Ordinal Columns, Null Values Analysis</h2></center><br>
<h3>Objectives:</h3>
<ul>
    <li>Identify columns with possible ordinal transformation</li>
    <li>Identify and analyze null values to assign values or drop</li>
    <li>Map Ordinal Dictionary to categories for dummification</li>
</ul><br>

<center><h3>Ordinal Dictionary</h3></center>

<h2>List of Converted Ordinal Columns:</h2>
<ul>
    <li>Bsmt Qual</li>
    <li>Bsmt Cond</li>
    <li>Fireplace Qu</li>
    <li>Garage Qual</li>
    <li>Garage Cond</li>
</ul>

|Value|Description|Ordinal Number|
|---|--|---|
|Ex|Excellent|5|
|Gd|Good|4|
|TA|Average|3|
|Fa|Fair|2|
|Po|Poor|1|
|NA|No <-->|0|

<ul>
    <li>Exter Qual</li>
    <li>Exter Cond</li>
    <li>HeatingQC</li>
    <li>Kichen Qual</li>
</ul>

|Value|Description|Ordinal Number|
|---|--|---|
|Ex|Excellent|4|
|Gd|Good|3|
|TA|Average|2|
|Fa|Fair|1|
|Po|Poor|0|

<ul>
    <li>Bsmt Exposure</li>
</ul>

|Value|Description|Ordinal Number|
|---|--|---|
|Gd|Good Exposure|4|
|Av|Average Exposure|3|
|Mn|Minimum Exposure|2|
|No|No Exposure|1|
|NA|No Basement|0|

<ul>
    <li>Pool QC</li>
</ul>

|Value|Description|Ordinal Number|
|---|--|---|
|Ex|Excellent|4|
|Gd|Good|3|
|TA|Average/Typical|2|
|Fa|Fair|1|
|NA|No No Pool|0|

<ul>
    <li>Lot Shape</li>
</ul>

|Value|Description|Ordinal Number|
|---|--|---|
|Reg|Regular|3|	
|IR1|Slightly irregular|2|
|IR2|Moderately Irregular|1|
|IR3|Irregular|0|

<ul>
    <li>Utilities</li>
</ul>

|Value|Description|Ordinal Number|
|---|--|---|
|AllPub|All public Utilities (E,G,W,& S)|3|	
|NoSewr|Electricity, Gas, and Water (Septic Tank)|2|
|NoSeWa|Electricity and Gas Only|1|
|ELO|Irregular|0|

<ul>
    <li>Land Slope</li>
</ul>

|Value|Description|Ordinal Number|
|---|--|---|	
|Gtl|Gentle slope|2|
|Mod|Moderate Slope|1|
|Sev|Severe Slope|0|

<ul>
    <li>BsmtFin Type 1</li>
    <li>BsmtFin Type 2</li>
</ul>

|Value|Description|Ordinal Number|
|---|--|---|	
|GLQ|Good Living Quarters|6|
|ALQ|Average Living Quarters|5|
|BLQ|Below Average Living Quarters|4|
|Rec|Average Rec Room|3|
|LwQ|Low Quality|2|
|Unf|Unfinished|1|
|NA|No Basement|0|

<ul>
    <li>Electrical</li>
</ul>

|Value|Description|Ordinal Number|
|---|--|---|	
|SBrkr|Standard Circuit Breakers & Romex|4|
|FuseA|Fuse Box over 60 AMP and all Romex wiring (Average)|3|
|FuseF|60 AMP Fuse Box and mostly Romex wiring (Fair)|2|
|FuseP|60 AMP Fuse Box and mostly knob & tube wiring (poor)|1|
|Mix|Mixed|0|

<ul>
    <li>Functional</li>
</ul>

|Value|Description|Ordinal Number|
|---|--|---|	
|Typ|Typical Functionality|7|
|Min1|Minor Deductions 1|6|
|Min2|Minor Deductions 2|5|
|Mod|Moderate Deductions|4|
|Maj1|Major Deductions 1|3|
|Maj2|Major Deductions 2|2|
|Sev|Severely Damaged|1|
|Sal|Salvage only|0|

<ul>
    <li>Garage Finish</li>
</ul>

|Value|Description|Ordinal Number|
|---|--|---|	
|Fin|Finished|3|
|Rfn|Rough Finished|2|
|Unf|Unfinished|1|
|NA|No Garage|0|

<ul>
    <li>Paved Drive</li>
</ul>

|Value|Description|Ordinal Number|
|---|--|---|	
|Y|Paved|2|
|P|Partial Pavement|1|
|N|Dirt/Gravel|0|

<ul>
    <li>Fence</li>
</ul>

|Value|Description|Ordinal Number|
|---|--|---|
|GdPrv|Good Privacy|4|
|MnPrv|Minimum Privacy|3|
|GdWo|Good Wood|2|
|MnWw|Minimum Wood/Wire|1|
|NA|No Fence|0|

## EDA

<h1><center>EDA - Numerical Columns</center></h1>

For these numerical columns, some of the informatics in the scatterplots have shown us very interesting relationship between each column and <code>SalePrice</code>. Let's take a look at a few noticable examples:

<h3>Rating-Related Relationships</h3>
<ul>
    <li><code>Overall Cond</code> - (House) overall condition of the house.</li>
    It is clearly shown in the graph that it has a negative correlation to prices?<br><br>
    
<li><code>Overall Qual</code> - (House) rates the overall material and finish of the house.</li>
    It is clearly shown in the graph that higher quality means higher price, but doesn't it affect <code>Overall Cond</code>?
<br>
</ul>

<h3>Area-Related Relationships</h3>
<ul>
    <li><code>Garage Area</code> - (Garage Size) size calculation in square feet.</li>
    Unlike in Singapore, apparently most houses have garage area attached to their homes. The size of this affects the prices by a significant amount.
<br><br>
    <li><code>Gr Liv Area</code> - (Living Space) size calculation in square feet</li>
    Living area refers to the size of the home in square feet. It makes sense because as your house is bigger, it is going to cost more.
    
In my honest opnion, it seems to me that everything related to area size should be related to <code>SalePrice</code>, like <code>1st Flr SF</code>. However, this is not the case. A lot of houses have 0.0 (bef. data cleaning: Null) indicating they do not have like <code>2nd Flr SF</code>, but have high <code>SalePrice</code>. No obvious patterns to indicate other Area-related columns have strong correlation.
</ul>

<h3>Facility-Related Relationships</h3>
<ul>
<li><code>Fireplaces</code> - (Fireplace) quantity (2)</li><br>
<li><code>Full Bath</code> - (Bathroom) quantity (2)</li><br>
<li><code>Half Bath</code> - (Bathroom) quantity (1)</li><br>
<li><code>Kitchen AbvGr</code> - (Kitchen) quantity (1)</li><br>
<li><code>Garage Cars</code> - (Garage) quantity (3)</li><br>
Interestingly, these facilities correlate with prices on specific quantity. Example: Having too many <code>Fireplaces</code> or kitchen might be too bad? This column could be related to <code>Garage Area</code> as well since it relates to how many cars you can keep.
</ul>

    
<h3>Time-Related Relationships</h3>
<ul>
<li><code>Year Built</code> - (House) original construction date</li>
    Newer houses tend to cost more, as seen from the graph, from 2000.
<br><br>
<li><code>Garage Yr Blt</code> - (Garage) year garage was built</li>
    <code>SalePrice</code> shoots up from 2000.
</ul>

However, <code>Mo Sold</code> and <code>Yr Sold</code> don't seem to have any obvious trend.

<h1><center>EDA - Numerical Columns</center></h1>

For these numerical columns, some of the informatics in the scatterplots have shown us very interesting relationship between each column and <code>SalePrice</code>. Let's take a look at a few noticable examples:

<h3>Rating-Related Relationships</h3>
<ul>
    <li><code>Overall Cond</code> - (House) overall condition of the house.</li>
    It is clearly shown in the graph that it has a negative correlation to prices?<br><br>
    
<li><code>Overall Qual</code> - (House) rates the overall material and finish of the house.</li>
    It is clearly shown in the graph that higher quality means higher price, but doesn't it affect <code>Overall Cond</code>?
<br>
</ul>

<h3>Area-Related Relationships</h3>
<ul>
    <li><code>Garage Area</code> - (Garage Size) size calculation in square feet.</li>
    Unlike in Singapore, apparently most houses have garage area attached to their homes. The size of this affects the prices by a significant amount.
<br><br>
    <li><code>Gr Liv Area</code> - (Living Space) size calculation in square feet</li>
    Living area refers to the size of the home in square feet. It makes sense because as your house is bigger, it is going to cost more.
    
In my honest opnion, it seems to me that everything related to area size should be related to <code>SalePrice</code>, like <code>1st Flr SF</code>. However, this is not the case. A lot of houses have 0.0 (bef. data cleaning: Null) indicating they do not have like <code>2nd Flr SF</code>, but have high <code>SalePrice</code>. No obvious patterns to indicate other Area-related columns have strong correlation.
</ul>

<h3>Facility-Related Relationships</h3>
<ul>
<li><code>Fireplaces</code> - (Fireplace) quantity (2)</li><br>
<li><code>Full Bath</code> - (Bathroom) quantity (2)</li><br>
<li><code>Half Bath</code> - (Bathroom) quantity (1)</li><br>
<li><code>Kitchen AbvGr</code> - (Kitchen) quantity (1)</li><br>
<li><code>Garage Cars</code> - (Garage) quantity (3)</li><br>
Interestingly, these facilities correlate with prices on specific quantity. Example: Having too many <code>Fireplaces</code> or kitchen might be too bad? This column could be related to <code>Garage Area</code> as well since it relates to how many cars you can keep.
</ul>

    
<h3>Time-Related Relationships</h3>
<ul>
<li><code>Year Built</code> - (House) original construction date</li>
    Newer houses tend to cost more, as seen from the graph, from 2000.
<br><br>
<li><code>Garage Yr Blt</code> - (Garage) year garage was built</li>
    <code>SalePrice</code> shoots up from 2000.
</ul>

However, <code>Mo Sold</code> and <code>Yr Sold</code> don't seem to have any obvious trend.

## Feature Engineering
    
<p>Feature Engineering is the process of selecting, manipulating and transforming raw data into features. With Kaggle's Data Dictionary made publicly opened, there could be some features that could be better. I have tried several combinations and found out that the followings are effective for the model. Many of them are drafted with common sense, but were further supported by the results of my models.</p>
    
<ul>
<li><h3>Total SF = Total Bsmt SF + 1st Flr SF + 2nd Flr SF</h3></li>
<li><h3>Total Bath = Full Bath + Bsmt Full Bath + (Half Bath + Bsmt Half Bath)/2</h3></li>
<li><h3>House Age = Year Remod/Add - Year Built</h3></li>    
</ul>

<p>It is intuitive to think that people would be interested in total square feet of the whole house instead, and also how long has the house been around ever since it was built/renovated.</p>
    
<ul>
<li><h3>Garage Area</h3></li>
<code>Garage Cars</code> are directly related to <code>Garage Area</code>, and since <code>Garage Area</code> has less correlation, I have decided to drop it.
<li><h3>Garage Yr Blt</h3></li>
Similar to <code>Year Built</code>, so it is dropped.

<li><h3>Mo Sold</h3></li>
Dropping Time columns as our features do not compute Time.
<li><h3>Yr Sold</h3></li>    
Dropping Time columns as our features do not compute Time.
</ul>

<center><h3>Elimination through Lasso</h3></center><br>
Aside from common sense, in the labs, I have noticed that we could use Lasso to select optimal features as well. We will try to do Lasso with the newly engineered features and see what are the highly beneficial columns.
    
## Modelling
<center><h2>Linear Regression</h2></center><br>
<center><h2>Lasso Regression</h2></center><br>
<center><h2>Ridge Regression</h2></center><br>
<center><h2>Elastic Net</h2></center><br>
    
## Conclusion    

In conclusion, Lasso Regression has the lowest score. There are 66 features that we are using and even though I feel like it is a lot, it could be done better in my opinion. I find out that Feature Engineering is a very important concept to eliminate noise and improve predictions.

My Kaggle score was about 23k (Private) and 33k (Public). It is a huge improvement from (80k) the initial score. However, there are many more prediction techniques out there which I have not employed in my project 2. I was also surprised to see that Lasso Model was doing well rather than Ridge Model. In my labs, I have constantly dealt with Ridge Model as they turn out to be better. 

Despite brute-forcing many sections of the project, there is a clear distinction in which experience comes in. Many of the results are obtained by various numerical parameters obtained from labs and solution-code, even though it was mentioned that parameters are usually chosen by us.
    
The top 5 features in our model currently consist of <code>Gr Liv Area</code>, <code>Overall Qual</code>, <code> Neighborhood_NridgHt</code>, <code>Misc Val</code> and <code>Neighborhood_StoneBr</code>. The living area and overall quality make sense, because those were key factors which can directly influence <code>SalePrice</code>. However, in the context of this Kaggle project, I went to research on <code>Neighborhood_NridgHt</code>, <code>Misc Val</code> and <code>Neighborhood_StoneBr</code>. I found out that <code>Misc Val</code> includes facilities such as elevator, additional garage, tennis court or other facilities. This would justify the influence of <code>SalePrice</code> as these are costly upgrades.

Out of curiosity, I googled the neighborhood locations <code>Neighborhood_NridgHt</code> and <code>Neighborhood_StoneBr</code>.
