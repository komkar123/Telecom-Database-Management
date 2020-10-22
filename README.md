# Telecommunication Services Management System

## Background
In the current world, usage and utilization of WIFI, phones and smart TVs has increased manifold. Though people are provided with variety of entertainment and informative content, it has also increased the complexity of managing these services all at once and keeping up with the customer interests and demands. 
We would be creating and maintaining a centralized database which would be used to store a huge amount of data across service providers and would store Customer data and the services they have subscribed to. The analysis of this data would help user with a consolidated view of bills for these services and would provide a better insight of the expenditure for these services for previous months. The service providers can also utilize the data to understand the usage of the services provided and enhance and come up with more user-oriented proposals with respect to services, enabling them to provide a better and effective customer service. 

## Purpose
•	To provide a consolidated view of billing of all the utilities the customer has subscribed.
•	Enabling the user to analyze the previous months spends for these subscribed services.
•	Enabling the service providers to analyze the subscriptions for the current plans.
•	To help determine the service provider the interests and current demands to enhance the current plans and propose more convenient plans for the customers.

## Abstract :
Creating and maintaining a centralized database which would be used to store a huge amount of data across service providers and would store Customer data and the services they have subscribed to. The analysis of this data would help user with a consolidated view of bills for these services and would provide a better insight of the expenditure for these services for previous months.

## Entity Relationship Diagram
![alt text](https://i.ibb.co/XC0LLw5/erd.png)

## Entities:
Our project deals with generating bills for all the telecommunication services used by the customer. We have identified the following entity types. An identifier is also suggested for each entity, together with selected important attributes: 

### CUSTOMER 
Customer is the general representation for all the telecommunication users. Customer_ID
Is the primary key for this entity and it contains CustomerName. It also contains additional information such as PhoneNumber, Email, Address , DateOfBirth.

### REGISTRATIONINFO
RegistrationInfo stores the relation between Customer and ServiceProvider . Registration_ID is the primary key for this entity and it contain foreign keys such as Customer_ID and SP_ID which are the primary keys in the Customer and ServiceProvider entities respectively. It also has other registration details such as Registration_Date.

### SERVICE_PROVIDER
Service_Provider is the general representation for all the provider providing different types of telecommunication services . SP_ID is the primary key and it also has other information about the ServiceProvider such as SP_Name and also the service type information such as Has_Wifi, Has_TV, Has_Mobile . ContactNo of the service provider is also included.

### PLAN
Plan gives details of various telecommunication plans provided by the ServiceProvider.
Plan_ID is the primary key of a plan. It also includes details of the plan which would be required to bill the customer as per his selected plan. The details included in plan are PlanType, PlanPrice, Cycle, PlanName, PlanDesc. Also plan includes the foreign key SP_ID to link the plan with its ServiceProvider.

### ASSET
Asset is supplied ServiceProvider. Asset contains primary key Asset_ID and also other details about the asset such as AssetName, AssetDesc, AssetModel, AssetSerial, AssetPrice. All the details are not null except AssetDesc as it can be null.

### ORDER
Order contains details about the Service provider and also asset such that which service provider is supplying a particular asset. Primary key of Order is UniqueID and it also contains ServiceProviderID and AssetID and Price.

### CUST_ORDER_MAPPING
Cust_Order_Mapping maps the customer with the order entity which provides the asset details ordered by a customer of the products assets provided by the ServiceProvider. OrderID is the primary key CustomerOrderMapping also contains other details such as OrderDesc and OrderDate and OrderAmount and also it contain foreign keys such as CustomerID from the customer entity and UniqueID from the Order entity.

### WIFI
Wifi contains the wifi plan details considering ExtraCharges as per speed, usage. WPlanID is the Primary key of wifi entity and it includes other Wifi plan related information such as Usage, Speed, ExtraCharges. 

### TV
TV contains the TV plan details . TPlanID is the primary key of the TV entity and other information in TV includes PlanName, TV_Services.

### MOBILE
Mobile includes the mobile plan details which would assist in billing the customers as per the telecommunication plan they are using. MPlanID is the primary key and other details included are DataSpeed, Calling and SMS.

### CUSTOMER_PLAN
Customer_Plan includes the details which would assist to generate the billing information for a particular customer depending on the plan the customer selects and also it provides the start and end date of the the customer plan. CustomerPlanID is the primary key and it also includes StartDate, EndDate, and Duration. It also includes Foreign keys such as CustomerID and PlanID.

### BILLING_INFO
Billing_Info has all the specific billing information for a customer as per the plan selected.
TransactionID is the primary key . Foreign key is CustomerPlanID and OrderID. BillingInfo also has details such as Duration, Month, TotalAmount, YearlyEstimate which would help in the bill generation for a particular customer as per his telecommunication plan.
 









