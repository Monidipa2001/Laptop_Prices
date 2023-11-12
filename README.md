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
1.Brand: Established brands tend to be pricier but often offer better build quality and support.
2.Specifications: Higher RAM, faster processors, dedicated graphics, and premium features contribute to higher prices.
3.Purpose: Gaming laptops and those designed for content creation generally come with a higher price tag.
4.Market Trends: Prices can fluctuate based on market demand, availability, and technological advancements.

Tips for Buyers:

1.Research: Compare prices, read reviews, and consider user feedback before making a purchase.
2.Future-Proofing: Invest in a laptop that meets your current needs and has some room for future upgrades.
3.Warranty and Support: Check the warranty period and the availability of service centers for the chosen brand.

# Laptop_Prices

1.Creating schema on MySQL 

SELECT * FROM project.laptop_prices;

2.Select laptops with a screen size greater than 17 inches: 

SELECT * FROM project.laptop_Prices
WHERE Inches > 17;

3.Select laptops with a price less than $41025.6: 

SELECT Company, Price FROM project.laptop_Prices
WHERE Price < 41025.6;

4.Count the number of laptops in the table: 

SELECT COUNT(*) AS TotalLaptops
FROM project.laptop_Prices;

5.Find the average price of all laptops:

SELECT AVG(Price) AS AveragePrice
FROM project.laptop_Prices;

6.Find the laptop with the highest price: 

SELECT *
FROM project.laptop_Prices
ORDER BY Price DESC
LIMIT 1;

7.Find the laptop with the lowest price: 

SELECT *
FROM project.laptop_prices
ORDER BY Price ASC
LIMIT 1;

8.Group laptops by Company and calculate the average price for each company: 

SELECT Company, AVG(Price) AS AveragePrice
FROM project.laptop_prices
GROUP BY Company;

9.Find laptops with a specific CPU type: 

SELECT *
FROM project.laptop_Prices
WHERE Cpu = 'Intel Core i5 2.3GHz';

10.Find laptops with a specific GPU: 

SELECT *
FROM project.laptop_Prices
WHERE Gpu = 'Intel UHD Graphics 620';

11.Find laptops with a specific operating system (e.g., Windows 10): 

SELECT *
FROM project.laptop_Prices
WHERE OpSys = 'Windows 10';

12.Calculate the total RAM available across all laptops: 

SELECT SUM(Ram) AS TotalRAM
FROM project.laptop_Prices;

13.Find laptops with a specific screen resolution (e.g., '2560x1440'): 

SELECT *
FROM project.laptop_Prices
WHERE ScreenResolution = '2560x1440';

14.Find laptops with a specific memory type (e.g., '1TB HDD'): 

SELECT Company,Memory
FROM project.laptop_Prices
WHERE Memory = '1TB HDD';

15.Find laptops with a specific company and CPU type: 

SELECT Company, Ram, Cpu
FROM project.laptop_Prices
WHERE Company = 'Apple' AND Cpu = 'Intel Core M m3 1.2GHz';

16.Find laptops with a specific company and GPU: 

SELECT *
FROM project.laptop_Prices
WHERE Company = 'Acer' AND Gpu = 'NVIDIA GeForce MX150';

17.Calculate the total weight of all laptops: 

SELECT SUM(Weight) AS TotalWeight
FROM project.laptop_Prices;

18.Find laptops with a specific screen size and RAM combination: 

SELECT Company, Inches, Ram
FROM project.laptop_Prices
WHERE Inches = 14 AND Ram = 8;

19.Find laptops with a specific company and a price range: 

SELECT *
FROM project.laptop_Prices
WHERE Company = 'Apple' AND Price BETWEEN 40000 AND 80000;

20.Select laptops with a specific operating system and RAM size: 

SELECT *
FROM project.laptop_Prices
WHERE OpSys = 'macOS' AND Ram = 16;

21.Find laptops with a specific company and screen resolution: 

SELECT *
FROM project.laptop_Prices
WHERE Company = 'Chuwi' AND ScreenResolution = 'Full HD 1920x1080';

22.Calculate the average screen size of laptops: 

SELECT AVG(Inches) AS AverageScreenSize
FROM project.laptop_Prices;

23.Find laptops with a specific company and a GPU with at least Nvidia GeForce 940MX: 

SELECT *
FROM project.laptop_Prices
WHERE Company = 'HP' AND Gpu LIKE '%Nvidia GeForce 930MX%';

24.Find laptops with a specific company and screen size greater than 15 inches: 

SELECT *
FROM project.laptop_Prices
WHERE Company = 'Samsung' AND Inches > 15;

25.Find laptops with a specific company and weight less than 3.5 kg: 

SELECT *
FROM project.laptop_Prices
WHERE Company = 'LG' AND Weight < 3.5;

26.Find Total laptop Prices of specific companies:  

SELECT Company, 
			SUM(Price) AS Total_laptop_prices
FROM project.laptop_Prices
GROUP BY Company;

27.Find the Average, Maximum and Minimum prices of Laptop according to Company :

SELECT Company,
             AVG(Price) AS “Average_laptop_price”,
             MAX(Price) AS "Maximum_laptop_prices",
             MIN(Price) AS "Minimum_laptop_prices"
FROM   project.laptop_Prices
WHERE  weight >= 2.8
GROUP BY Company;

28.Find CPU of all Companies starting with” Intel Core i5”: 

SELECT Company, TypeName, Cpu
FROM project.laptop_Prices
WHERE Cpu LIKE 'Intel Core i5%';

29.Find laptop prices in descending order: 

SELECT 
  Company,
  TypeName,
  Inches,
  RANK() OVER (ORDER BY Price DESC) as laptop_prices
FROM project.laptop_prices
ORDER BY Price;

30.Find retrieval of duplicate combination of values in the specified columns: 

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

31.  Find the cumulative price of a laptop: 
       
SELECT Company, Price, SUM(Price) OVER (ORDER BY Company) AS cumulative_price
FROM project.laptop_prices;

32.  Find the average price of the laptop: 
    
WITH laptop_price AS (
  SELECT Company, TypeName
  FROM project.laptop_prices
  WHERE Company = 'Apple'
)
SELECT AVG(price) AS avg_price
FROM project.laptop_prices;




