# Superstore

-- Objective :- Perform ‘Exploratory Data Analysis’ on dataset ‘SampleSuperstore’ .As a business manager, try to find out the weak areas where you can work to make more profit.

-- *** Get the price part Unit
-- *** State with Category has the Highest profit
-- *** Region with the Highest profit
-- *** Total Profit per categories
-- *** Total Profit per Sub-Categories 




CREATE DATABASE `Superstore`;
USE `Superstore`;

ALTER TABLE `samplesuperstore`
RENAME `superstore`;

SELECT * FROM `superstore`;

-- *** Get the price part Unit

SELECT * , `Sales` DIV `Quantity` AS `Price_per_unit` FROM `superstore`;

-- *** State with Category has the Highest profit

-- SELECT `Country`,`Sales`, `Quantity` ,`Category`, SUM(`Profit`) AS `Highest_Profit` FROM `superstore`
-- WHERE `Category` = 'Furniture' OR `Category` = 'Office Supplies' OR `Category` = 'Technology'
-- GROUP BY `Country` , `Sales`, `Quantity`, `Category`
-- ORDER BY `Category` ASC;


SELECT `Category`, SUM(`Profit`) AS `Total_Category` FROM `superstore`
GROUP BY `Category` ;

-- *** State with Sub-category has the Highest profit

SELECT `Sub-category`, SUM(`Profit`) AS `Total_Sub_category` FROM `superstore`
GROUP BY `Sub-Category` ;


-- *** Region with the Highest profit

SELECT `Region`, SUM(`Profit`) AS `Total_Profit_Per_Region` FROM `superstore`
GROUP BY `Region`;

-- *** State with the Highest profit

SELECT `State`, SUM(`Profit`) AS `Total_Profit_Per_State` FROM `superstore`
GROUP BY `State`;

