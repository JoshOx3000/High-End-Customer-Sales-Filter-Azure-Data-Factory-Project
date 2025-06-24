# High-End-Customer-Sales-Filter-Azure-Data-Factory-Project
Azure Data Factory to build a simple yet effective Data Flow pipeline that identifies high-value customers from sales data stored in a CSV file

📌 Project Overview
The goal of this project is to move and filter data from a raw data container into a curated container containing high-end customers (customers whose total sales exceed $1000). The filtered output is then saved as a new CSV file for further marketing actions (e.g., exclusive discount offers, event invitations).

📂 Source
Container: raw-sales-data

File: fashion_sales.csv

Format: CSV

Sample Columns:

Column      Descriptions

OrderID	    Unique identifier for each order
CustomerID	Identifier of the customer
OrderDate	  Date when the order was placed (YYYY‑MM‑DD)
ProductID	  Identifier for the product sold
Quantity	  Number of units sold
UnitPrice	  Price per unit (in USD)
TotalAmount	Computed field: Quantity * UnitPrice

🔁 Data Flow Logic
ADF Mapping Data Flow steps:

Source: Reads the CSV file from raw-sales-data.

Derived Column (Optional): Ensure TotalAmount is in numeric format.

sql
Copy
Edit
toInteger(TotalAmount)
Filter: Identifies high-value orders.

sql
Copy
Edit
toInteger(TotalAmount) > 1000
Sink: Writes the filtered data to the high-end-customers container as high_value_customers.csv.

📥 Output
Container: high-end-customers

File: high_value_customers.csv

Contains only records where TotalAmount > 1000.

⚙️ Tech Stack
Azure Data Factory

Azure Blob Storage

CSV Format

Data Flow Expression Builder

📈 Use Case
This filtered data can be used by marketing or sales teams to:

Invite high-value customers to exclusive events

Offer VIP discounts

Analyze premium product performance

📌 How to Reuse
Upload your own sales CSV into your Azure Blob Storage container.

Update the dataset paths in ADF.

Modify filter logic if using a different currency or threshold.

Trigger the pipeline manually or set up a schedule.

📧 Contact
For questions or collaboration, feel free to reach out via GitHub or open an issue.
Linkedin: https://www.linkedin.com/in/joshua-oxner-615074107/
