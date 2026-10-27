# Ecommerce Analytics Project

## Problem Statement

This dashboard helps the Stakeholders understand their customers better. It helps the stakeholders know if their customers are satisfied with their services. Through different ratings, they get to know their improvement area, & thus they can improve their services by identifying these area. It also lets them know the percentage of orders returned,cancelled,pending & Net sales by country,monthly orders trend,Net Sales by product category,net sales by shipping status,net sales by marketing channel,top 5 product according to customers and what amount spent in marketing to attract new customers and percentage of returning customers,how much new  and returning customers,top 10 product by margin,net margin by age distribution,Impact of delivery status on net margin,net margin through shipping , thus since by using this dashboard they have identified this problem, they can further work on factors responsible for these unwanted delays.

Since delivery On time then net margin 61.08% and when delivery delayed then net margin reduced to 11.86%

Also when orders delivers on time it take 4 days & when it delayed it takes 7 days so they get to their improvement area.

### Steps followed 

- Step 1 : Load data into Power BI Desktop, dataset is a csv file.
- Step 2 : Open power query editor & in view tab under Data preview section, check "column distribution", "column quality" & "column profile" options and then transform data corrects data type ,handles missing values,clean data before loading to data model then i perform data modeling star schema was used.
- Step 3 : Also since by default, profile will be opened only for 1000 rows so i  select "column profiling based on entire dataset".
- Step 4 : It was observed that in none of the columns errors & empty values were present except column named "delivery days","Customer rating","Customer Review"
- Step 5 : For calculating average delay time in delivery , i fill where it contains empty values(less then 18 %)
- Step 6 : In the report view, under the view tab, theme was selected.
- Step 7 : first Page of report tells Overview of Ecommerce Performance,including Total orders,average order value,total unit sold,total profit margin,net sales. 
- Step 8 : Visual filters (Slicers) were added for four fields named "Month", "Year", "Shipping status" , "Product Category","Payment Method","Region","Country".
- Step 9 : Five card visuals were added to the canvas, one representing Total Orders ,other representing average order value,other used to represent Total units sold,other used to represent Total profit margin,net sales.
           Using visual level filter from the filters pane, basic filtering was used for consideration into calculation.
  
         
- Step 10 : A stacked bar chart was also added to the report design area representing the number of total orders by product category and units ordered by product category.

<img width="431" height="229" alt="{93BA0A1F-EA77-4AD0-88A3-CB82F434C17F}" src="https://github.com/user-attachments/assets/65257b48-d5db-4b27-b2bc-899f9c265972" />

  

- Step 11 : to represent top 5 product according to customer rating.I use clustered bar chart.


<img width="322" height="528" alt="{F788F9E8-9577-4EA0-B7F1-95A29BAD159F}" src="https://github.com/user-attachments/assets/8711a263-d92b-4bb1-935b-d688f289bcba" />


- Step 12 : In the report view, under the insert tab, two text boxes were added to the canvas, in one of them name Executive overview was mentioned & in the other one navigator button was mention.

- Step 13 : To represent monthly orders trends i used line chart.

<img width="456" height="198" alt="{D35DC2BA-23A4-405D-A361-B44E6054AF5E}" src="https://github.com/user-attachments/assets/1565da9d-37dc-4ea3-8b0d-eac434ab10c0" />


- Step 14 : Calculated column was created in which, customers were grouped into various age groups.

for creating new column following DAX expression was written;
       
        Age Breakdown = 
           IF('customers_dim'[customer_age]>=50,"Elder",
           IF('customers_dim'[customer_age]>=40,"Adult",
           "Young Adult"
           
           )
           
           )
Snap of new calculated column ,

<img width="163" height="702" alt="{43877BCE-A53B-4CA2-9AF0-DDE7E88013E2}" src="https://github.com/user-attachments/assets/7fad38b7-8fbe-4949-bf86-b4de0cdc044c" />

        
- Step 15 : New measure was created to find total count of return orders.

Following DAX expression was written for the same,
        
        Total Returns1 = CALCULATE(COUNTROWS('fact_table1'),'fact_table1'[order_status] = "Returned")
A stacked column chart visual was used to represent count of returns orders by product category.

<img width="613" height="236" alt="{CD0C404D-1F37-48A2-A97F-AB2048F83F56}" src="https://github.com/user-attachments/assets/0e5da61e-bfb6-481e-bd1f-8d2308ee2659" />


        
 - Step 16 : New measure was created to find  year wise sales(YTD),
 
 Following DAX expression was written to find % of customers,
 
         YTD = TOTALYTD(SUM(fact_table1[profit_margin_percentage]),'fact_table1'[order_date].[Date])
 
 - Step 17 : To represent net sales by shipping status line and stacked column chart used.

<img width="504" height="264" alt="{615DA6CF-8DA9-45F9-8B6E-CA21014B2F83}" src="https://github.com/user-attachments/assets/0d40dafb-3e27-44df-b4ed-2338cbd56757" />

 - Step 18 : to represent net margin through shipping status donut chart used.
 
<img width="361" height="237" alt="{12D65E20-4306-44FB-A5C5-0C92148C31BB}" src="https://github.com/user-attachments/assets/e9423942-73af-4aae-a4c8-487876478431" />


# First Page of report.
<img width="1377" height="768" alt="{00A9606F-F4BD-43FB-AE29-0403EA4AD209}" src="https://github.com/user-attachments/assets/3234b299-88de-48c4-894f-f4fedecff89b" />



# Second Page of report.
<img width="1366" height="756" alt="{86743FEE-B7B1-46EE-A2D8-2918108C7494}" src="https://github.com/user-attachments/assets/09f6e7df-8778-456e-9cbf-59527b3d4c98" />




# Third Page of report.

<img width="1373" height="769" alt="{B49F2B73-B452-4BF4-BA5E-389742B18CB0}" src="https://github.com/user-attachments/assets/bbe154e0-fea3-4dc9-893e-8ce7e95a6cf1" />




# Fourth Page of report.
<img width="1293" height="722" alt="{B897B550-CB6F-4874-83DD-B0AB6C739901}" src="https://github.com/user-attachments/assets/ba438442-2720-4e45-9e32-7f5d9ba3f94f" />



# Fial Page of report.
<img width="1367" height="762" alt="{A442F328-BE9E-4CBE-B4D5-4737768D8779}" src="https://github.com/user-attachments/assets/f6a8e53c-0cf8-4270-b65c-4b60ae366d4f" />


# Insights

A five page report was created on Power BI Desktop & it was then published to Power BI Service.

Following inferences can be drawn from the report;

### [1] Total Number of Orders = 1,38000
### distribution of orders by shipping status.

   Number of orders completed  = 1,13,559 (82.22 %)

   Number of orders returned  = 9,462 (6.85 %)

   Number of cancelled orders = 8,398 (6.08 %)

   Number of pending orders= 6,697 (4.85 %)


           thus, higher number of orders are completed.
           
### [2] Top 5 Product category by Customer Ratings

    a) Baby & Kids - 3.06/5
    b) Spots & outdoors - 3.05/5
    c) Fashion - 3.05/5
    d) Toys & games - 3.05/5
    e) Jewellery - 3.04/5
  
  
  while calculating average rating, null values have been ignored as they were not relevant for some customers. 
  
  These ratings will change if different visual filters will be applied.  
  
  ### [3] Average Delay 
  
      a) Average delay  when orders delivered early - 3 days
      a) Average delay  when orders delivered on time - 4 days
      a) Average delay  when orders  delayed - 7 days
      a) Average delay  when orders cancelled - 15 days
  
Average delay will change if different visual filters will be applied.

 ### [4] Some other insights
 
 #### Net margin by different age groups.           

 1.1) Net margin by Elders  - 33.35 %
 
 1.2) Net margin by young adults - 33.33 %
 
 1.3) Net margin by adults - 33.32 %
 

 
         thus, maximum margin comes from age group elders.
 
 ### Net margin by shipping status
 

      a) Net margin when orders delivered to customers - 79.8 %
      a) Net margin when orders returns - 8.21 % 
      a) Net margin when orders cancelled - 7.32  %
      a) Net margin when orders in pending - 4.67  %
    
 
         thus, maximum margin comes from when orders completed.
         
### Customer loyalty overview

3.1) Loyal customers - 1,29,447.

3.2) 8,355 customers have customer type 'returning'.

3.3) New Customers - 334
       
       thus, we have more customers loyal.

### Returning customers by gender

4.1) 47.99 % male customers returning .

4.2) 48.81 % female customers returning .

4.3) 3.09 % non binary customers returning .


        thus, more female customers "returning".

### Customer Acquisition Cost breakdown.

#### amount spent in marketing for different age groups.

5.1) Avg acquisition cost for young adults - $42.26(33.43 % ).

5.2) Avg acquisition cost for  adults - $42.02(33.24 % ).

5.3) Avg acquisition cost for elders - $42.13(33.33 % ).


     while max net margin comes from age group elders.

### Quarterly net margin .

6.1) net margin in quarter 1 - $12,81,794.81

6.2) net margin in quarter 2 - $14,07,509.35

6.3) net margin in quarter 3 - $14,03,081.59

6.4) net margin in quarter 4 - $16,06,149.71

    thus max net margin increased in quarter -  4


### Net margin by top 10 product category.

7.1) Sports & outdoors - 10.81 %

7.2) Books  &  Media   - 10.73 %

7.3) Health & wellness - 10.41 %

7.4) Beauty & personal care - 10.34 %

7.5) Office Supplies - 10.17%

7.6) Grocery - 9.86 %

7.7) Toys & games- 9.78 %

7.8) Baby & kids - 9.43 %

7.9) Pet & supplies - 9.26 %

7.10) Automotive - 9.21 %

      thus max net margin comes from Sports & outdoors.


### Customer Breakdown.

8.1) Customer type consumer - 75,636

8.2) VIP customers - 13,957

8.3) Premium customers - 34,746           

8.4) Customers own their business - 13,777

      thus we have max consumers.

### Yearly margin.

9.1) In 2021 net margin - $1.24 millions

9.2) In 2022 net margin - $1.24 millions

9.3) In 2023 net margin - $1.24 millions

9.4) In 2024 net margin - $1.26 millions

9.5) In 2025 net margin - $1.25 millions

    thus yearly margin maximum in 2024.





        
