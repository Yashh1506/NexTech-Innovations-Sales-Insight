# Atliq-Sales-Insight

### Dashboard Link : https://app.powerbi.com/groups/me/reports/20a50d01-ba7c-47ef-9996-9222fc284133/fe4b5b84cd7c03308e32?experience=power-bi

## Problem Statement

This dashboard helps Atliq pvt ltd to go through their sales from 2017 to 2020. Atliq pvt ltd is a computer hardware manufacturing company that has customers all over the indian subcontinent, in this report we'll be focusing on its sales in India. As the market is growing dynamically Atliq product started selling at a faster rate than before, and they are unable to monitor their sales in this growing market.When asked for report they get multiple excel files that are unable to provide the complete insight, they needed a interactive dashboard that would navigate them through the overall sales. Thus we will be using Power BI to generate an interactive dashboard that would help them to make data driven decisions to cope up with the market trend.


### Steps followed 

- Step 1 : Load data into Power BI Desktop, the data was provided as a sql dump file with sales database consisting of 5 tables
- Step 2 : Database consist of 5 tables "sales transaction","sales product","sales markets","sales customers","sales day"
           These table consist of
           1) sales transaction : product code, customer code, market code, order date, sales quantity, sale amount and sales amount.
           2) sales product : product code and product type.
           3) sales market : market code, market name and zone.
           4) sales customer : customer code, customer name and customer type.
           5) sales date : Dates on which the product was sold.
- Step 3 : Data Modelling,the database represents a star schema, every table has a connection with the "sales transaction" table
- Step 4 : There were some blank values in "sales market" table in zone attribute, it was observed that New York and Paris market did'nt have any entry in "sales transaction" thus they were dropped from market 
           table
- Step 5 : In "sales transaction" table, some entries had "[sales_amount<=0]" which is not possible, thus they were filtered.
- Step 6 : Two currencies were found in the data INR and USD, to normalize the sales amount, amount in USD was converted into INR.
- Step 7 : Duplicate rows were found in "sales transaction" table, they were dropped
- Step 8 : New measures were calculated i.e Revenue and Total Sales Quantity.
- Step 9 : Two cards were included in the visualization one representing the total revenue and other total sales quantity. 
- Step 10 : Dashboard consist of two visual filters (Slicers) to one filtering year and other month.
- Step 11 : Four horizontal barcharts are included to represent , Top 5 customers by revenue, Top 5 products by revenue, Revenue per market and total sale quantity per market.
- Step 12 : Finally the dashboard consist of Line chart that represent the Revenue trend
        
Snap of new calculated column , that was added to normalise the sales amount

![Screenshot 2024-07-20 111517](https://github.com/user-attachments/assets/ec8049f4-ea44-4635-9aa4-24e49f3af45c)

Following DAX expression was written to calculte revenue and total sales quantity,
        
        Revenue = SUM('sales transactions'[sales_amount])
        Sales Qty = SUM('sales transactions'[sales_qty])
        
Card visuals were used to represent Revenue and Sales Qty.

![Screenshot 2024-07-20 121243](https://github.com/user-attachments/assets/ae0cf4bc-8fa3-416f-a2e1-e0a11240bdab)

Snap of Top 5 Customers and Products by Revenue

![Screenshot 2024-07-20 121514](https://github.com/user-attachments/assets/fb087e02-a21c-4538-8888-023fb00d1472)

Snap of Revenue and Sale Quantity by Market

![Screenshot 2024-07-20 121942](https://github.com/user-attachments/assets/64d0422b-c0f7-44a0-9b80-83c39505f081)

 
 - Step 13 : The report was then published to Power BI Service.

 Snap of Dashboard

![image](https://github.com/user-attachments/assets/8c9d69e3-bdb7-4a94-9c01-d6a07b989582)


# Insights

- Total number of customers : 38
- Total number of products : 279
- Total number of market places : 17
- Total revenue : 986565766
- Total sales quantity : 2444415
           
