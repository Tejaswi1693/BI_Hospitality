# BI_Hospitality

**Synopsis**

AtliQ Grands is a well-established hospitality company that owns multiple five-star hotels across India. The company has been in the industry for the past 20 years and is known for its luxury and business hotels.

**PROBLEM STATEMENT**
AtliQ Grands owns multiple five-star hotels across India. They have been in the hospitality industry for the past 20 years. Due to strategic moves from other competitors and ineffective decision-making in management, AtliQ Grands are losing its market share revenue in the luxury/business hotels category.

Objective: To provide AtliQ Grands with insights from their historical data to regain their market share and revenue.

**SKILLS DEMONSTRATED**
This project exposed me to learn a lot using Microsoft Power BI.

· Multiple complex DAX formulas and Functions.

· Calculated columns

· Data Extraction, Cleaning, and Transformation (ETL)

· Data Modelling

· Data Visualization

**DATA SOURCING**

The dataset used for this analysis was collected from Code Basics’ website, I have uploaded the CSV files.

dim_date
dim_hotels
dim_rooms
fact_aggregated_bookings
fact_bookings

**DATA TRANSFORMATION**

Data Loading and Power Query Documentation

Create a folder in Desktop and store all the csv files related to hospitality challenge.

Open a Power BI file, and In "Get Data", select the option as folder and browse through the folder containing csv files.

Then go to Tranform data to expand each and every dataset.

Now, duplicate the data source 4 times and in each one, expand one dataset by clicking on "Binary" option. also, rename the tables accordingly.

**Power Query steps for tables:**
dim_date:

remove the column 'day_type' we are deleting this because, we got a feedback from the mock dashboard review that Friday and Saturday are considered as weekends in the industry and not sunday. But In our datasets, saturday and sunday are considered as weekends. So we delete this column and re-create day_type using calculated columns. dim_rooms

The column names are not captured here. We need to select "Use First Row as Headers" option .


<img width="827" height="334" alt="data_model" src="https://github.com/user-attachments/assets/869ca5c3-400a-40a1-9e3b-038613fa2e3e" />

**BUILDING DAX**

Calculated Column

Our first Calculated column is to get number from week_no column of dim_date into week_number and the formula is : week_number = WEEKNUM(dim_date[date])

Our Second Calculated column to get day_type from dim_date table. So, as we know in hospitality domain weekdays are Sunday to Thursday and weekends are Friday and Saturday. So, the formula to get day_type is : day_type = var wkd = WEEKDAY(dim_date[date]) return if(wkd>5,"Weekend","Weekday")

**MEASURES**

Revenue : To get the total revenue_realized : formula : Revenue = SUM(fact_bookings[revenue_realized]) : and the table is fact_bookings.

Total Bookings : To get the total number of bookings happened: Formula : Total Bookings = COUNT(fact_bookings[booking_id]): and the table is fact_bookings.

**INSIGHTS**

Mumbai generates the highest revenue (669 M) followed by Bangalore, Hyderabad and Delhi.
AtliQ Exotica performs better compared to all 7 type of properties with 320 Million revenue, rating 3.62, occupancy percentage 57 and cancellation rate as 24.4%.
AtliQ Bay has the highest occupancy of 66%.
Week 24 recorded the highest revenue among all, which is 139.6 Million.
Delhi tops both in occupancy and rating followed by Hyderabad, Mumbai, Bangalore.
AtliQ lost around 298 Million in cancellation.
Elite type rooms has the most booking and as well higher cancellation rate.
