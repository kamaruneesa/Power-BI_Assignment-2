# Power-BI_Assignment-2
# Dax & Data Visualization
## Power-BI Desktop Window ➡️ Get Data ➡️Transform ➡️Text/csv ➡️Select files➡️clean files
  


 **Calculated Columns:**
 
 - **Create a Calculated Column for 'Category Type':**
    - Table tools➡️ New column ➡️ Category Type = 'Order Details '[Category] & " - "& 'Order Details '[Sub-Category]
 - **Calculate Revenue per Order in Order Details Table:**
    - Table tools➡️ New column ➡️Revenue = 'Order Details '[Amount]*'Order Details '[Quantity]
 - **Create a Calculated Column to Categorize Sales:**
    -  Table tools➡️ New column ➡️Sales Category = IF('Order Details '[Amount]>AVERAGE('Order Details '[Amount]),"Above             Average","Below Average")
  
 **Calculated Measures:**
 
  - **Calculate Order Count:**
     - Table tools➡️ New measures ➡️Total Orders = COUNT('Order Details '[Order ID])
  - **Calculate Average Profit in Delhi:**
    -  Table tools➡️ New measures ➡️Delhi Average Profit = CALCULATE(AVERAGE('Order Details '[Profit] ),'List of Orders               '[State]="Delhi")
  - **Calculate Year-to-Date (YTD) Sales:**
     -  - Table tools➡️ New measures ➡️max date:Max date = MAX('List of Orders '[Order Date])
        -  Table tools➡️ New measures ➡️min date:min date = MIN('List of Orders '[Order Date])
        -   Table tools➡️ New measures ➡️Total sales amount = SUM('Order Details '[Amount])
        - Table tools➡️ New measures ➡️sales YTD = TOTALYTD([Total sales amount],'List of Orders '[Order Date])=65K  
