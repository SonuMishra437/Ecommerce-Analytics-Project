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

<img width="425" height="229" alt="{7982809C-5991-4CA2-8528-C40C9695DA8E}" src="https://github.com/user-attachments/assets/12131734-f485-4923-a7ff-016ccbb880de" />

  

- Step 11 : to represent top 5 product according to customer rating.i use clustered bar chart.


<img width="331" height="549" alt="{A7CF28E9-9411-4DF3-A093-A5F3A606ACCA}" src="https://github.com/user-attachments/assets/5b378af1-668a-416e-8dd4-ac8afc4f6f3f" />


- Step 12 : In the report view, under the insert tab, two text boxes were added to the canvas, in one of them name Executive overview was mentioned & in the other one navigator button was mention.
- Step 13 : To represent monthly orders trends i used line chart.

<img width="466" height="202" alt="{96691630-5AB0-42AC-8064-8AF738D9AF00}" src="https://github.com/user-attachments/assets/1513379d-d326-4f5c-bed7-3b41869d2ec3" />

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

<img width="580" height="222" alt="{D3228399-B3AF-4C43-A985-18D6D33F8909}" src="https://github.com/user-attachments/assets/f7ec3fe6-16bf-4630-ab5e-4936e89ef7f9" />


        
 - Step 16 : New measure was created to find  year wise sales(YTD),
 
 Following DAX expression was written to find % of customers,
 
         YTD = TOTALYTD(SUM(fact_table1[profit_margin_percentage]),'fact_table1'[order_date].[Date])
 
 - Step 17 : To represent net sales by shipping status line and stacked column chart used.

<img width="466" height="247" alt="{331959CB-F4CD-4C11-ADD9-B5CAD459868E}" src="https://github.com/user-attachments/assets/de18c594-dbd7-49a6-bbe5-e6a5f1ecd096" />

 - Step 18 : to represent net margin through shipping status donut chart used.
 
<img width="361" height="237" alt="{12D65E20-4306-44FB-A5C5-0C92148C31BB}" src="https://github.com/user-attachments/assets/e9423942-73af-4aae-a4c8-487876478431" />


# First Page of report.
<img width="1437" height="777" alt="{33F5189A-18F1-4DFB-BB48-72C7DE85243F}" src="https://github.com/user-attachments/assets/5c386364-f73a-403b-be58-010cd235e0ce" />


# Second Page of report.
<img width="1425" height="771" alt="{CFFC66B5-7D4A-477A-A8D9-2B4E7A5A3583}" src="https://github.com/user-attachments/assets/9a7c0d63-ef3e-410a-8315-219f5729168f" />



# Third Page of report.

<img width="1423" height="764" alt="{F66710C0-D93F-4380-AA99-015AE60B833A}" src="https://github.com/user-attachments/assets/144758aa-1575-4e92-88f3-c28ce046bd60" />



# Fourth Page of report.
<img width="1428" height="777" alt="{C56CFA7D-3855-4E80-BEE3-AB598AE0D7D3}" src="https://github.com/user-attachments/assets/e26b8096-99cc-4fe1-904e-57bb9d797e91" />



# Fial Page of report.
<img width="1373" height="731" alt="{47106745-70F2-45FD-AB8A-3DCB651D8AA3}" src="https://github.com/user-attachments/assets/19a98e83-fb33-4630-a8f7-ffe52ee4eadb" />


 
 # Project video 

 


[2026-10-16 23-26-50.zip](https://github.com/user-attachments/files/33567198/2026-10-16.23-26-50.zip)











# Insights

A single page report was created on Power BI Desktop & it was then published to Power BI Service.

Following inferences can be drawn from the dashboard;

### [1] Total Number of Customers = 129880

   Number of satisfied Customers (Male) = 28159 (21.68 %)

   Number of satisfied Customers (Female) = 28269 (21.76 %)

   Number of neutral/unsatisfied customers (Male) = 35822 (27.58 %)

   Number of neutral/unsatisfied customers (Female) = 37630 (28.97 %)


           thus, higher number of customers are neutral/unsatisfied.
           
### [2] Average Ratings

    a) Baggage Handling - 3.63/5
    b) Check-in Service - 3.31/5
    c) Cleanliness - 3.29/5
    d) Ease of online booking - 2.88/5
    e) Food & Drink - 3.21/5
    f) In-flight Entertainment - 3.36/5
    g) In-flight service - 3.64/5
    h) In-flight Wifi service - 2.81/5
    i) Leg room service - 3.37/5
    j) On-board service - 3.38/5
    k) Online boarding - 3.33/5
    l) Seat comfort - 3.44/5
    m) Departure & arrival convenience - 3.22/5
  
  while calculating average rating, null values have been ignored as they were not relevant for some customers. 
  
  These ratings will change if different visual filters will be applied.  
  
  ### [3] Average Delay 
  
      a) Average delay in arrival(minutes) - 15.09
      b) Average delay in departure(minutes) - 14.71
Average delay will change if different visual filters will be applied.

 ### [4] Some other insights
 
 ### Class
 
 1.1) 47.87 % customers travelled by Business class.
 
 1.2) 44.89 % customers travelled by Economy class.
 
 1.3) 7.25 % customers travelled by Economy plus class.
 
         thus, maximum customers travelled by Business class.
 
 ### Age Group
 
 2.1)  21.69 % customers belong to '0-25' age group.
 
 2.2)  52.44 % customers belong to '25-50' age group.
 
 2.3)  25.57 % customers belong to '50-75' age group.
 
 2.4)  0.31 % customers belong to '75-100' age group.
 
         thus, maximum customers belong to '25-50' age group.
         
### Customer Type

3.1) 18.31 % customers have customer type 'First time'.

3.2) 81.69 % customers have customer type 'returning'.
       
       thus, more customers have customer type 'returning'.

### Type of travel

4.1) 69.06 % customers have travel type 'Business'.

4.2) 30.94 % customers have travel type 'Personal'.

        thus, more customers have travel type 'Business'.
