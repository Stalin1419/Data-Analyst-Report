ecommerce-sales-analysis/
│
├── data/
│   └── ecommerce_sales.csv
│
├── notebooks/
│   └── sales_analysis.ipynb
│
├── sql/
│   └── sales_queries.sql
│
├── reports/
│   └── sales_report.pdf
│
├── images/
│   ├── monthly_sales.png
│   ├── category_sales.png
│   └── regional_sales.png
│
└── README.md


Your ecommerce_sales.csv could contain:

Order_ID	Order_Date	Customer	Region	Category	Product	Quantity	Unit_Price	Sales	Profit
ORD001	2025-01-05	Customer 01	South	Electronics	Laptop	1	55000	55000	6500
ORD002	2025-01-08	Customer 02	North	Furniture	Chair	4	3500	14000	2200
ORD003	2025-01-12	Customer 03	West	Electronics	Mobile	2	18000	36000	4000
ORD004	2025-01-18	Customer 04	East	Clothing	Jacket	3	2500	7500	1500
ORD005	2025-02-02	Customer 05	South	Electronics	Tablet	2	22000	44000	5200
ORD006	2025-02-10	Customer 06	North	Clothing	Shoes	2	3000	6000	1200
ORD007	2025-02-15	Customer 07	West	Furniture	Table	1	8500	8500	1300
ORD008	2025-02-22	Customer 08	East	Electronics	Headphones	5	2000	10000	2500
ORD009	2025-03-03	Customer 09	South	Furniture	Sofa	1	25000	25000	3500
ORD010	2025-03-11	Customer 10	North	Electronics	Laptop	2	55000	110000

-- Total Sales
SELECT SUM(Sales) AS Total_Sales
FROM ecommerce_sales;

-- Total Profit
SELECT SUM(Profit) AS Total_Profit
FROM ecommerce_sales;

-- Sales by Category
SELECT Category,
       SUM(Sales) AS Total_Sales
FROM ecommerce_sales
GROUP BY Category
ORDER BY Total_Sales DESC;

-- Sales by Region
SELECT Region,
       SUM(Sales) AS Total_Sales
FROM ecommerce_sales
GROUP BY Region
ORDER BY Total_Sales DESC;
