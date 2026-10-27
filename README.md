# Power-BI_Assignment-2
# Dax & Data Visualization
## Power-BI Desktop Window ➡️ Get Data ➡️Transform ➡️Text/csv ➡️Select files➡️clean files
  
  -"the 'List of order 'table originally had 501 rows ,which was cleaned and reduces to 193 rows" 

 **Calculated Columns:**
 
 - **Create a Calculated Column for 'Category Type':**
    - Table tools➡️ New column ➡️ Category Type = 'Order Details '[Category] & " - "& 'Order Details '[Sub-Category]
 - **Calculate Revenue per Order in Order Details Table:**
    - Table tools➡️ New column ➡️Revenue = 'Order Details '[Amount]*'Order Details '[Quantity]
 - **Create a Calculated Column to Categorize Sales:**
    -  Table tools➡️ New column ➡️Sales Category = IF('Order Details '[Amount]>AVERAGE('Order Details '[Amount]),"Above             Average","Below Average")
  
 **Calculated Measures:**
 
  - **Calculate Order Count:**
     - Table tools➡️ New measures ➡️Total Orders = DISTINCTCOUNT('Order Details '[Order ID])
  - **Calculate Average Profit in Delhi:**
    -  Table tools➡️ New measures ➡️Delhi Average Profit = CALCULATE(AVERAGE('Order Details '[Profit] ),'List of Orders               '[State]="Delhi")
  - **Calculate Year-to-Date (YTD) Sales:**
     -  - Table tools➡️ New measures ➡️max date:Max date = MAX('List of Orders '[Order Date])
        -  Table tools➡️ New measures ➡️min date:min date = MIN('List of Orders '[Order Date])
        -   Table tools➡️ New table ➡️Date_table = ADDCOLUMNS(CALENDAR(DATE(2018,4,1),DATE(2019,3,12)),"year",YEAR([Date]),"month number",MONTH([Date]),"month name",FORMAT([Date],"mmmm"),"Quater","Q" & QUARTER([Date]),"Day",DAY([Date]),"Day NAME",FORMAT([Date],"DDDD"))
        -   Table tools➡️ New measures ➡️Total sales amount = SUM('Order Details '[Amount])
        - Table tools➡️ New measures ➡️sales YTD = TOTALYTD([Total sales amount],'List of Orders '[Order Date])=65K
      

**Data Visualization:**

 - **Sales Target Achievement by Category:**
     -  clustered column chart: report view ➡️ select chart ➡️X-axis: category ,Y-axis: sum of amount, Target sales

- **Max Profit Margin by Sub-Category:**
     -  Table tools➡️ New measures ➡️ 
     - Profit margin = DIVIDE(SUM('Order Details '[Profit]),SUM('Order Details '[Amount]),0)
     - Max profit margin = MAXX(VALUES('Order Details '[Sub-Category]),[Profit margin])
    -  Donut chart: report view ➡️ select chart ➡️legend: sub-category,

- **Comparison of Profit and Quantity by Sub-Category:**
    -  line chart: report view ➡️ select chart ➡️ x-axis :order date (month), y-axis :sum of amount
 
- **Comparison of Profit and Quantity by Sub-Category:**
     -  scatter chart: report view ➡️ select chart ➡️ values : sub-category ,x-axis :sum of quantity ,y-axis: sum of profit

- **Comparison of Total Sales Amount and Target:**
     - minimum target:min target = MIN('Sales target '[Target])
     - multi-row card :select➡️ sum of target, total sales amount, min target 
- **Sales Performance Matrix:**
    - Matrix: report view ➡️ select chart ➡️ rows: category , column: month ,values: sum of amount ,sum of target
- **Geographic Sales Analysis:**
     - map :report view ➡️ select chart ➡️ location: city,  legend:  sum of amount
     - Kashmir  :not a city , causing incorrect map placement ,
     - order B225962: missing city name (blank), leading to location errors

- **Sales Distribution by Sub-Category:**
   - tree map: category :sub- category ,values:   sum ofamount
- **Order Count Analysis by State:**
   - funnel chart: category :state ,values :total orders
 
       
           
