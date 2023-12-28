# Create SQL Database


<h2>Description</h2>
The provided SQL code involves the normalization of a database schema for employee information. The original schema consists of a single table with redundant data, and the goal is to create separate tables for distinct entities to achieve better normalization.

<img src="https://i.imgur.com/K32dNam.jpg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />


<h2>Languages and Utilities Used</h2>

- <b>SQL</b> 

<h2>Environments Used </h2>

- <b>MySQL</b> 

<h2>Program walk-through:</h2>

<p align="left">
Create tables: <br/>
CREATE TABLE `dbemployee`.`employeeid` (
  `EmployeeID` INT NOT NULL AUTO_INCREMENT,
  `EmployeeLN` VARCHAR(25) NULL,
  `EmployeeFN` VARCHAR(25) NULL,
  `Address` VARCHAR(45) NULL,
  `City` VARCHAR(30) NULL,
  `Department` VARCHAR(10) NULL,
  `Position` VARCHAR(40) NULL,
  PRIMARY KEY (`EmployeeID`),
  UNIQUE INDEX `EmployeeID_UNIQUE` (`EmployeeID` ASC) VISIBLE);

CREATE TABLE `dbemployee`.`adress` (
  `city` VARCHAR(20) NOT NULL,
  `State` VARCHAR(2) NOT NULL,
  `Zip` INT(5) NULL,
  PRIMARY KEY (`city`));

CREATE TABLE `dbemployee`.`department` (
  `Department` VARCHAR(5) NOT NULL,
  `Manager` VARCHAR(45) NOT NULL,
  PRIMARY KEY (`Department`),
  UNIQUE INDEX `Department_UNIQUE` (`Department` ASC) VISIBLE);

CREATE TABLE `dbemployee`.`positions` (
  `idPositions` INT NOT NULL,
  `Positionname` VARCHAR(45) NOT NULL,
  `Salary` INT NOT NULL,
  PRIMARY KEY (`idPositions`),
  UNIQUE INDEX `idPositions_UNIQUE` (`idPositions` ASC) VISIBLE);
<br/>
  
<img src="https://i.imgur.com/JT0tdDP.jpg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Insert data into tables:<br />

INSERT INTO `dbemployee`.`employeeid` (`EmployeeID`, `EmployeeLN`, `EmployeeFN`, `Address`, `CityID`, `Departmentid`, `idPosition`) VALUES ('1000', 'Doe', 'Janet', '312 Maple Drive', '1', '1', '1');
INSERT INTO `dbemployee`.`employeeid` (`EmployeeID`, `EmployeeLN`, `EmployeeFN`, `Address`, `CityID`, `Departmentid`, `idPosition`) VALUES ('1010', 'Eyre', 'Jane', '1200 First Street', '1', '2', '2');
INSERT INTO `dbemployee`.`employeeid` (`EmployeeID`, `EmployeeLN`, `EmployeeFN`, `Address`, `CityID`, `Departmentid`, `idPosition`) VALUES ('1011', 'Bronte', 'Charlotte', '4989 Fleur de Lane', '2', '2', '2');
INSERT INTO `dbemployee`.`employeeid` (`EmployeeID`, `EmployeeLN`, `EmployeeFN`, `Address`, `CityID`, `Departmentid`, `idPosition`) VALUES ('2060', 'Poe', 'Edgar', '12Arcadia Avenue ', '1', '3', '3');
INSERT INTO `dbemployee`.`employeeid` (`EmployeeID`, `EmployeeLN`, `EmployeeFN`, `Address`, `CityID`, `Departmentid`, `idPosition`) VALUES ('2090', 'Dickens', 'Charles', '687 Gulf View Street', '2', '3', '4');
INSERT INTO `dbemployee`.`employeeid` (`EmployeeID`, `EmployeeLN`, `EmployeeFN`, `Address`, `CityID`, `Departmentid`, `idPosition`) VALUES ('2100', 'Doyle', 'AC', '1209 Pine Tree Lane', '4', '3', '4');
INSERT INTO `dbemployee`.`employeeid` (`EmployeeID`, `EmployeeLN`, `EmployeeFN`, `Address`, `CityID`, `Departmentid`, `idPosition`) VALUES ('3230', 'Uberville', 'Tess', '5435 Main Street ', '5', '4', '5');
INSERT INTO `dbemployee`.`employeeid` (`EmployeeID`, `EmployeeLN`, `EmployeeFN`, `Address`, `CityID`, `Departmentid`, `idPosition`) VALUES ('3330', 'Dumas', 'Alex', '3 Post Drive', '4', '4', '6');
<br />
<br />

INSERT INTO `dbemployee`.`adress` (`cityid`, `cityname`, `State`, `Zip`) VALUES ('1', 'Anytown I', 'FL', '32829');
INSERT INTO `dbemployee`.`adress` (`cityid`, `cityname`, `State`, `Zip`) VALUES ('2', 'Sometown I', 'FL', '32829');
INSERT INTO `dbemployee`.`adress` (`cityid`, `cityname`, `State`, `Zip`) VALUES ('3', 'Sometown II', 'FL', '32830');
INSERT INTO `dbemployee`.`adress` (`cityid`, `cityname`, `State`, `Zip`) VALUES ('4', 'Sometown III', 'FL', '32831');
INSERT INTO `dbemployee`.`adress` (`cityid`, `cityname`, `State`, `Zip`) VALUES ('5', 'Anytown II', 'FL', '32831');
<br />
<br />

INSERT INTO `dbemployee`.`department` (`Departmentid`, `Department`, `Manager`) VALUES ('1', 'EXEC', 'Janet Doe');
INSERT INTO `dbemployee`.`department` (`Departmentid`, `Department`, `Manager`) VALUES ('2', 'MGMT', 'Janey Doe');
INSERT INTO `dbemployee`.`department` (`Departmentid`, `Department`, `Manager`) VALUES ('3', 'IT', 'John Smith');
INSERT INTO `dbemployee`.`department` (`Departmentid`, `Department`, `Manager`) VALUES ('4', 'SALES', 'Jane Smith');
<br />
<br />

INSERT INTO `dbemployee`.`positions` (`idPositions`, `Positionname`, `Salary`) VALUES ('1', 'President', '100000');
INSERT INTO `dbemployee`.`positions` (`idPositions`, `Positionname`, `Salary`) VALUES ('2', 'Vice President', '75000');
INSERT INTO `dbemployee`.`positions` (`idPositions`, `Positionname`, `Salary`) VALUES ('3', 'Programmer II', '52000');
INSERT INTO `dbemployee`.`positions` (`idPositions`, `Positionname`, `Salary`) VALUES ('4', 'Programmer I', '45000');
INSERT INTO `dbemployee`.`positions` (`idPositions`, `Positionname`, `Salary`) VALUES ('5', 'Sales Rep. I', '32000');
INSERT INTO `dbemployee`.`positions` (`idPositions`, `Positionname`, `Salary`) VALUES ('6', 'Sales Rep. II', '35000');<br />
<img src="https://i.imgur.com/bLzEkG5.jpg" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<br />
<br />
Summary:  <br/>
The SQL code showcases the process of normalizing a database schema for employee information. It involves creating separate tables for cities, departments, and job positions, and then modifying the original employee table to reference these normalized tables. This approach eliminates redundancy and establishes relationships between entities, contributing to a more efficient and well-structured database design. The provided images visually represent the original and normalized schemas, offering a clear overview of the normalization process.
</p>

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
