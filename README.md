# ecommerce_shipping_data

## Overview

This project involves analyzing ecommerce shipping data using SQL queries. The objective is to extract and manipulate structured data from a database to gain insights into shipping costs, order statuses, and customer information.

## Tools Used

- **Database Management System**: MySQL
- **Development Environment**: MySQL Workbench

## Dataset

The dataset used for this analysis is a simulated ecommerce shipping data set, which includes the following tables:

1. **shipping_data**
   - `order_id`: INT (Primary Key)
   - `customer_id`: INT
   - `shipping_cost`: DECIMAL
   - `order_date`: DATE
   - `delivery_date`: DATE
   - `status`: VARCHAR

2. **customers**
   - `customer_id`: INT (Primary Key)
   - `customer_name`: VARCHAR

## SQL Queries

The following SQL queries were executed to analyze the data:

1. **Select All Data**
   ```sql
   SELECT * FROM shipping_data;
   ```

2. **Filter Data by Status**
   ```sql
   SELECT * FROM shipping_data WHERE status = 'Delivered';
   ```

3. **Order Data by Shipping Cost**
   ```sql
   SELECT * FROM shipping_data ORDER BY shipping_cost DESC;
   ```

4. **Calculate Total Shipping Cost by Status**
   ```sql
   SELECT status, SUM(shipping_cost) AS total_shipping_cost
   FROM shipping_data
   GROUP BY status;
   ```

5. **Join Query to Combine Shipping and Customer Data**
   ```sql
   SELECT s.order_id, c.customer_name, s.shipping_cost
   FROM shipping_data s
   INNER JOIN customers c ON s.customer_id = c.customer_id;
   ```

6. **Subquery to Find Orders with Shipping Cost Greater than Average**
   ```sql
   SELECT * FROM shipping_data
   WHERE shipping_cost > (SELECT AVG(shipping_cost) FROM shipping_data);
   ```

7. **Create a View for Delivered Orders**
   ```sql
   CREATE VIEW delivered_orders AS
   SELECT * FROM shipping_data WHERE status = 'Delivered';
   ```

8. **Optimize Queries with Indexes**
   ```sql
   CREATE INDEX idx_customer_id ON shipping_data(customer_id);
   ```

## Screenshots

Screenshots of the output for each query have been included in this repository to demonstrate the results of the analysis.
![Screenshot 2025-04-10 160746](https://github.com/user-attachments/assets/ebe882b2-9668-4810-83ff-5fd76ca753ce)
![Screenshot 2025-04-10 160836](https://github.com/user-attachments/assets/b0b2a928-f23a-4be5-842f-006f0a966db5)
![Screenshot 2025-04-10 160909](https://github.com/user-attachments/assets/40f1a842-7456-4125-998d-f01616d5b6c1)
![Screenshot 2025-04-10 160939](https://github.com/user-attachments/assets/14115bb2-1383-409a-bec9-2747288e2c6c)
![Screenshot 2025-04-10 161034](https://github.com/user-attachments/assets/a6260c70-8224-4b72-a260-35794612e474)
![Screenshot 2025-04-10 161115](https://github.com/user-attachments/assets/cd316e82-2412-45ea-bfe1-8aa5964a8b0a)
![Screenshot 2025-04-10 161235](https://github.com/user-attachments/assets/d07c235a-83a1-421e-b044-8a2b8e8b0854)




## Conclusion

This project provided hands-on experience in using SQL for data analysis, including data extraction, manipulation, and optimization techniques. The insights gained from the analysis can help in understanding shipping costs and customer behavior in an ecommerce context.

