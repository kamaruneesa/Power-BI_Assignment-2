# Power-BI_Assignment-2
# Dax & Data Visualization


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
  - **
