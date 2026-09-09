# User Roles

## 1\. Purpose

The purpose of this document is to identify the main user roles that directly interact with the Harvest Supermarket Management System and describe their business responsibilities.

A user role represents a responsibility performed when interacting with the system. A stakeholder does not necessarily have to be a direct system user.

Detailed technical privileges and Spring Security authorization rules will be defined during later requirements and security-design activities.

## 2\. User Role Identification

|ID|User Role|Description|Main Responsibilities|
|-|-|-|-|
|UR-01|Administrator|Performs system administration activities|Manage users, roles, privileges, and selected system configuration|
|UR-02|Store Manager|Supervises supermarket operations|Monitor operations, review information, perform or approve management activities|
|UR-03|Cashier|Performs customer sales activities|Process sales, payments, and permitted customer transaction activities|
|UR-04|Inventory Clerk|Performs inventory-related activities|Maintain item information, review stock, and perform permitted inventory activities|
|UR-05|Purchasing Officer|Performs supplier and purchasing activities|Maintain supplier information, prepare purchase orders, and manage goods-receiving activities|

## 3\. User Role Details

### UR-01 — Administrator

**Description:**  
The Administrator is responsible for administrative control of the application.

**Main Responsibilities:**

* Maintain user accounts
* Manage user roles
* Manage privileges
* Assign appropriate access to users
* Maintain selected system-level information

### UR-02 — Store Manager

**Description:**  
The Store Manager uses the system to supervise and control supermarket operations.

**Main Responsibilities:**

* Monitor supermarket operations
* Review inventory information
* Review sales and purchasing information
* Access management information and reports
* Perform or approve authorized management activities
* Investigate operational discrepancies when necessary

### UR-03 — Cashier

**Description:**  
The Cashier uses the system primarily to perform customer sales transactions.

**Main Responsibilities:**

* Search or identify items for sale
* Create customer sales transactions
* Record sold quantities
* Process permitted payments
* Produce transaction information such as receipts
* Perform permitted sales-related corrections or returns

### UR-04 — Inventory Clerk

**Description:**  
The Inventory Clerk is responsible for maintaining item and inventory-related information.

**Main Responsibilities:**

* Maintain item information
* View inventory levels
* Record permitted stock adjustments
* Assist with goods-receiving activities
* Monitor inventory-related information
* Identify inventory discrepancies

### UR-05 — Purchasing Officer

**Description:**  
The Purchasing Officer manages supplier and purchasing-related activities.

**Main Responsibilities:**

* Maintain supplier information
* Prepare and maintain purchase orders
* Review purchasing information
* Record or coordinate goods received from suppliers
* Compare ordered and received goods
* Maintain purchasing-related records

## 4\. Stakeholder and User Role Relationship

|Stakeholder|Related User Role|Direct System User|
|-|-|-|
|Supermarket Owner|Store Manager or management-level access where required|Optional|
|Store Manager|Store Manager|Yes|
|Cashiers|Cashier|Yes|
|Inventory Staff|Inventory Clerk|Yes|
|Purchasing Staff|Purchasing Officer|Yes|
|Administrative Staff|Administrator|Yes|
|Customers|None in the initial internal system|No|
|Suppliers|None in the initial internal system|No|
|Regulatory / Government Authorities|None|No|

## 5\. Role Design Principle

A physical employee and a system user role are not necessarily the same concept.

One employee may perform more than one role depending on the size and organization of the supermarket. For example, in a small supermarket, the Store Manager may also perform purchasing activities.

The detailed mapping between users, roles, and privileges will therefore be defined separately during security design.

\---

**Document Status:** Approved Sample Project Baseline

