# Following are the list of queries we applied on our sales data to extract meaningful insight

#sort by ascending order
SELECT * FROM sales_data
ORDER BY total ASC;

#Get sales from a specific branch (e.g., 'A'):
SELECT * FROM sales_data
WHERE branch = 'A';

#Filter sales where the total amount is greater than 1000:
SELECT * FROM sales_data
WHERE total > 1000;

#Filter by multiple conditions (e.g., branch 'B' and rating higher than 4):
SELECT * FROM sales_data
WHERE branch = 'B' AND rating > 4;


SELECT * FROM sales_data
WHERE branch = 'A';


SELECT * FROM sales_data
WHERE total > 1000;


SELECT * FROM sales_data
WHERE branch = 'B' AND rating > 4;



SELECT sd.*
FROM sales_data sd
JOIN (
    SELECT total
    FROM sales_data
    ORDER BY total DESC
    LIMIT 3
) AS top_sales
ON sd.total = top_sales.total;







SELECT * FROM sales_data
WHERE branch = 'A';


SELECT * FROM sales_data
WHERE total > 1000;


SELECT * FROM sales_data
WHERE branch = 'B' AND rating > 4;



SELECT sd.*
FROM sales_data sd
JOIN (
    SELECT total
    FROM sales_data
    ORDER BY total DESC
    LIMIT 3
) AS top_sales
ON sd.total = top_sales.total;
