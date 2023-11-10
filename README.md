Welcome to my GitHub repository! Here's a brief overview of laptop prices in India to help you make informed decisions:

Overview:
India's laptop market offers a diverse range of options catering to various needs and budgets. Laptop prices can vary based on specifications, brand reputation, and the intended usage. As of the last available information in 2023, here's a general breakdown:

Entry-Level Laptops:
Price Range: ₹20,000 to ₹40,000
Specifications: Basic processors, sufficient RAM for everyday tasks, and moderate storage capacity.
Usage: Ideal for casual use, web browsing, and basic productivity tasks.
Mid-Range Laptops:

Price Range: ₹40,000 to ₹80,000
Specifications: Mid-tier processors, ample RAM, and better storage options.
Usage: Suitable for moderate gaming, content creation, and multitasking.
High-End Laptops:

Price Range: ₹80,000 and above
Specifications: Powerful processors, dedicated graphics cards, ample RAM, and high-capacity SSDs.
Usage: Designed for gaming, professional content creation, and resource-intensive applications.

Factors Influencing Prices:
Brand: Established brands tend to be pricier but often offer better build quality and support.
Specifications: Higher RAM, faster processors, dedicated graphics, and premium features contribute to higher prices.
Purpose: Gaming laptops and those designed for content creation generally come with a higher price tag.
Market Trends: Prices can fluctuate based on market demand, availability, and technological advancements.


# Laptop_Prices

SELECT * FROM project.laptop_prices;

SELECT * FROM project.laptop_Prices
WHERE Inches > 17;

SELECT Company, Price FROM project.laptop_Prices
WHERE Price < 41025.6;

SELECT COUNT(*) AS TotalLaptops
FROM project.laptop_Prices;

SELECT AVG(Price) AS AveragePrice
FROM project.laptop_Prices;

SELECT *
FROM project.laptop_Prices
ORDER BY Price DESC
LIMIT 1;

SELECT *
FROM project.laptop_prices
ORDER BY Price ASC
LIMIT 1;

SELECT Company, AVG(Price) AS AveragePrice
FROM project.laptop_prices
GROUP BY Company;

SELECT *
FROM project.laptop_Prices
WHERE Cpu = 'Intel Core i5 2.3GHz';

SELECT *
FROM project.laptop_Prices
WHERE Gpu = 'Intel UHD Graphics 620';

SELECT *
FROM project.laptop_Prices
WHERE OpSys = 'Windows 10';

SELECT SUM(Ram) AS TotalRAM
FROM project.laptop_Prices;

SELECT *
FROM project.laptop_Prices
WHERE ScreenResolution = '2560x1440';

SELECT Company,Memory
FROM project.laptop_Prices
WHERE Memory = '1TB HDD';

SELECT Company, Ram, Cpu
FROM project.laptop_Prices
WHERE Company = 'Apple' AND Cpu = 'Intel Core M m3 1.2GHz';

SELECT *
FROM project.laptop_Prices
WHERE Company = 'Acer' AND Gpu = 'NVIDIA GeForce MX150';

SELECT SUM(Weight) AS TotalWeight
FROM project.laptop_Prices;

SELECT Company, Inches, Ram
FROM project.laptop_Prices
WHERE Inches = 14 AND Ram = 8;

SELECT *
FROM project.laptop_Prices
WHERE Company = 'Apple' AND Price BETWEEN 40000 AND 80000;

SELECT *
FROM project.laptop_Prices
WHERE OpSys = 'macOS' AND Ram = 16;

SELECT *
FROM project.laptop_Prices
WHERE Company = 'Chuwi' AND ScreenResolution = 'Full HD 1920x1080';

SELECT AVG(Inches) AS AverageScreenSize
FROM project.laptop_Prices;

SELECT *
FROM project.laptop_Prices
WHERE Company = 'HP' AND Gpu LIKE '%Nvidia GeForce 930MX%';

SELECT *
FROM project.laptop_Prices
WHERE Company = 'Samsung' AND Inches > 15;

SELECT *
FROM project.laptop_Prices
WHERE Company = 'LG' AND Weight < 3.5;

SELECT Company, 
			SUM(Price) AS Total_laptop_prices
FROM project.laptop_Prices
GROUP BY Company;

SELECT Company,
             AVG(Price) AS “Average_laptop_price”,
             MAX(Price) AS "Maximum_laptop_prices",
             MIN(Price) AS "Minimum_laptop_prices"
FROM   project.laptop_Prices
WHERE  weight >= 2.8
GROUP BY Company;

SELECT Company, TypeName, Cpu
FROM project.laptop_Prices
WHERE Cpu LIKE 'Intel Core i5%';

SELECT 
  Company,
  TypeName,
  Inches,
  RANK() OVER (ORDER BY Price DESC) as laptop_prices
FROM project.laptop_prices
ORDER BY Price;

SELECT Company,
  TypeName,
  Inches,
  ScreenResolution,
  Cpu,
  Price
FROM project.laptop_Prices
GROUP BY   
  Company,
  TypeName,
  Inches,
  ScreenResolution,
  Cpu,
  Price
HAVING COUNT(*) > 1;

SELECT Company, Price, SUM(Price) OVER (ORDER BY Company) AS cumulative_price
FROM project.laptop_prices;

WITH laptop_price AS (
  SELECT Company, TypeName
  FROM project.laptop_prices
  WHERE Company = 'Apple'
)
SELECT AVG(price) AS avg_price
FROM project.laptop_prices;




