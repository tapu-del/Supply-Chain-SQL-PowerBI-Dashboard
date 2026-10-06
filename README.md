# Supply Chain Dashboard - SQL + Power BI

## Project Overview
Built an interactive Supply Chain Dashboard using PostgreSQL and Power BI to analyze supplier performance, product categories, and shipment status.

## Tools Used
- PostgreSQL (SQL)
- Power BI Desktop
- DAX

## What I Did
1. Created database in PostgreSQL
2. Designed 3 tables: Suppliers, Products, Shipments
3. Wrote SQL INSERT statements
4. Connected Power BI directly to SQL database
5. Built interactive dashboard with KPIs and charts

## Key Insights
- Total Shipments: 8
- Total Quantity: 200
- Average Delivery Days: 8.50
- Global Trade is the top supplier
- Electronics is 60% of total quantity
- Furniture is 40% of total quantity
- Delivered orders are higher than Pending

## Dashboard Visuals
- KPI Cards: Shipments, Quantity, Delivery Days
- Bar Chart: Quantity by Supplier
- Pie Chart: Quantity by Category
- Bar Chart: Quantity by Status
- Line Chart: Quantity by Date
- Slicer: Status

## Screenshot
DROP TABLE IF EXISTS shipments;
DROP TABLE IF EXISTS products;
DROP TABLE IF EXISTS suppliers;

CREATE TABLE suppliers (
    supplier_id INTEGER PRIMARY KEY,
    supplier_name VARCHAR(100),
    country VARCHAR(50),
    rating INTEGER
);

CREATE TABLE products (
    product_id INTEGER PRIMARY KEY,
    product_name VARCHAR(100),
    category VARCHAR(50),
    unit_price NUMERIC
);

CREATE TABLE shipments (
    shipment_id INTEGER PRIMARY KEY,
    supplier_id INTEGER,
    product_id INTEGER,
    quantity INTEGER,
    shipment_date DATE,
    delivery_days INTEGER,
    status VARCHAR(20)
);
INSERT INTO suppliers VALUES
(1, 'Tata Supplies', 'India', 4),
(2, 'Global Trade', 'China', 3),
(3, 'EuroParts', 'Germany', 5),
(4, 'US Tech', 'USA', 4),
(5, 'Asia Corp', 'Japan', 3);

INSERT INTO products VALUES
(101, 'Laptop', 'Electronics', 50000),
(102, 'Chair', 'Furniture', 5000),
(103, 'Monitor', 'Electronics', 15000),
(104, 'Desk', 'Furniture', 12000),
(105, 'Printer', 'Electronics', 20000);

INSERT INTO shipments VALUES
(1, 1, 101, 10, '2026-01-15', 5, 'Delivered'),
(2, 2, 102, 50, '2026-01-20', 12, 'Delivered'),
(3, 3, 103, 20, '2026-02-01', 7, 'Delivered'),
(4, 4, 104, 30, '2026-02-10', 10, 'Pending'),
(5, 5, 105, 15, '2026-02-15', 8, 'Delivered'),
(6, 1, 101, 25, '2026-03-01', 6, 'Delivered'),
(7, 2, 103, 40, '2026-03-05', 15, 'Pending'),
(8, 3, 105, 10, '2026-03-10', 5, 'Delivered');
INSERT 0 8

Query returned successfully in 222 msec.

<img width="1068" height="618" alt="image" src="https://github.com/user-attachments/assets/1e773086-6d31-409f-b874-0849787e7914" />

## How to Use
1. Download the .pbix file
2. Open in Power BI Desktop
3. Explore the dashboard
