# real-estate-analytics
RealEstateAnalytics

A practical real-estate analytics project combining Python, SQL, Excel and data analysis to support commercial real-estate research, underwriting, valuation and portfolio analysis.

The goal of this repository is to build a reusable toolkit for analysing real-estate data, with an initial focus on the Sofia commercial property market.

Project Objectives

This project is designed to develop tools for:

* Property valuation
* Investment underwriting
* Rent analysis
* Market analysis
* Lease-expiry analysis
* WAULT and lease metrics
* Comparable property analysis
* Portfolio analytics
* SQL-based property databases
* Excel model integration
* Interactive real-estate dashboards

The longer-term objective is to create a structured real-estate analytics environment where market data, property information, lease data and financial models can be analysed through a combination of Python, SQL, Excel and visualization tools.

⸻

Repository Structure

RealEstateAnalytics/
│
├── database/
│   └── sofia_real_estate.db
│
├── src/
│   ├── database.py
│   ├── rent_analysis.py
│   ├── valuation.py
│   └── market_analysis.py
│
├── sql/
│   ├── prime_offices.sql
│   ├── lease_expiries.sql
│   └── market_rents.sql
│
├── notebooks/
│
├── excel_models/
│
├── app.py
├── requirements.txt
└── README.md

database/

Contains the project database.

The initial database is:

sofia_real_estate.db

It is intended to store structured information such as:

* Properties
* Buildings
* Owners
* Tenants
* Leases
* Rental levels
* Vacancy
* Transactions
* Valuations
* Market data

The project initially uses a lightweight local database and may later migrate to PostgreSQL or another production database.

⸻

src/

Contains the main Python modules.

database.py

Handles database connections, table creation, data imports and queries.

Potential functionality includes:

* Connecting Python to the real-estate database
* Importing CSV and Excel datasets
* Creating database tables
* Updating property records
* Extracting datasets for analysis

rent_analysis.py

Contains tools for rental and lease analysis.

Planned calculations include:

* Average rent
* Median rent
* Rent per sqm
* Passing rent
* Estimated Rental Value (ERV)
* Rent by submarket
* Rent by building class
* Rent growth
* Tenant concentration
* Lease expiry profiles
* WAULT

valuation.py

Contains property valuation and investment-analysis functions.

Planned functionality includes:

* Income capitalization
* Property yield calculations
* DCF valuation
* Net Present Value
* Internal Rate of Return
* Exit value
* Equity multiple
* Sensitivity analysis
* Debt metrics
* LTV
* DSCR

Example valuation logic:

def property_value(noi, yield_rate):
    return noi / yield_rate

For example:

NOI:          €1,500,000
Yield:        7.50%
Property Value:
€1,500,000 / 7.50%
= €20,000,000

market_analysis.py

Contains market-level analytics.

Potential analysis includes:

* Office stock
* Vacancy
* Take-up
* New supply
* Development pipeline
* Asking rents
* Prime rents
* Investment yields
* Market segmentation
* Submarket comparisons
* Historical trends

⸻

sql/

Contains reusable SQL queries.

prime_offices.sql

Example purpose:

Identify prime office properties based on criteria such as:

* Location
* Building class
* Size
* Vacancy
* Asking rent
* Investment yield

Example:

SELECT *
FROM properties
WHERE city = 'Sofia'
AND property_type = 'Office'
AND building_class = 'A';

lease_expiries.sql

Used to analyse upcoming lease expiries and break options.

Potential outputs:

* Expiries by year
* Expiring rent
* Expiring area
* Largest tenant expiries
* Portfolio lease risk

market_rents.sql

Used to analyse rental levels by:

* Submarket
* Building class
* Property type
* Year
* Building
* Lease size

⸻

notebooks/

Contains Jupyter notebooks used for exploratory analysis.

Examples may include:

sofia_office_market_analysis.ipynb
rent_analysis.ipynb
transaction_analysis.ipynb
portfolio_analysis.ipynb

Jupyter notebooks are used to experiment with data, test calculations and create visualizations before moving reusable functionality into the main Python modules.

⸻

excel_models/

Contains Excel-based real-estate financial models.

Future models may include:

* Investment DCF
* Acquisition model
* Development feasibility model
* Rent-roll analysis
* Residual land valuation
* Debt model
* Comparable transaction analysis
* Sensitivity analysis

Python may later be used to automatically read assumptions from these models and write calculated outputs back into Excel.

⸻

Technology Stack

The project is expected to use:

Python

Main programming and analytics language.

Pandas

Used for:

* Excel files
* CSV files
* Data cleaning
* Filtering
* Aggregation
* Data transformation

SQL

Used for querying and organising structured real-estate information.

DuckDB / SQLite

Used initially as lightweight analytical databases.

NumPy

Used for numerical calculations.

NumPy Financial

Used for financial functions such as:

* IRR
* NPV

OpenPyXL

Used to read and write Excel workbooks.

Plotly

Used for interactive visualizations.

Streamlit

Used to build interactive real-estate analytics applications.

Power BI

May be used as an additional business-intelligence and dashboarding layer.

⸻

Example Workflow

A typical workflow may look like:

Excel / CSV / Public Data
           ↓
         Python
           ↓
      Data Cleaning
           ↓
       SQL Database
           ↓
   Python Analytics
           ↓
Financial Calculations
           ↓
 Excel / Streamlit / Power BI

For example:

Rent Roll.xlsx
      ↓
Python
      ↓
Clean lease data
      ↓
SQL database
      ↓
Calculate:
WAULT
Passing rent
ERV
Lease expiries
Tenant concentration
      ↓
Dashboard / Excel report

⸻

Example Use Case

Assume a property database contains:

300 office buildings
2,000 leases
150 investment transactions
10 years of market data

SQL could identify all:

Class A Sofia office buildings
> 5,000 sqm
< 10% vacancy

Python could then calculate:

* Average asking rent
* Average vacancy
* Estimated NOI
* Capital value
* Investment yield
* Lease-expiry risk

The results could subsequently be displayed in a Streamlit or Power BI dashboard.

⸻

Installation

Clone the repository:

git clone https://github.com/YOUR-USERNAME/RealEstateAnalytics.git

Open the folder:

cd RealEstateAnalytics

Create a Python virtual environment:

python -m venv .venv

Activate it on Windows:

.venv\Scripts\activate

Install the required packages:

pip install -r requirements.txt

⸻

Running the Application

When the Streamlit application is available:

streamlit run app.py

This will launch the analytics interface in a web browser.

⸻

Development Roadmap

Phase 1 — Foundations

* [ ]	Set up project structure
* [ ]	Create Python environment
* [ ]	Create real-estate database
* [ ]	Add sample property data
* [ ]	Add basic SQL queries
* [ ]	Connect Python to database

Phase 2 — Core Analytics

* [ ]	Rent analysis
* [ ]	Vacancy analysis
* [ ]	Lease-expiry analysis
* [ ]	WAULT calculation
* [ ]	Yield analysis
* [ ]	Property valuation
* [ ]	DCF analysis

Phase 3 — Market Analytics

* [ ]	Sofia office database
* [ ]	Submarket analysis
* [ ]	Historical rent analysis
* [ ]	Vacancy trends
* [ ]	Development pipeline
* [ ]	Comparable transactions

Phase 4 — Visualization

* [ ]	Plotly charts
* [ ]	Interactive maps
* [ ]	Streamlit dashboard
* [ ]	Power BI integration

Phase 5 — Advanced Analytics

Potential future functionality:

* Automated comparable-property selection
* GIS analysis
* Automated market reports
* Lease-document extraction
* AI-assisted property research
* Predictive rent analysis
* Automated valuation tools
* Portfolio scenario analysis

⸻

Data

This repository should not contain confidential client information, sensitive lease data, passwords, credentials or proprietary datasets.

Where necessary, sample or synthetic data should be used for demonstration purposes.

Large raw datasets should normally be excluded from GitHub and downloaded separately.

⸻

Disclaimer

This project is intended for educational, analytical and professional-development purposes.

Any valuation, investment or market outputs produced by the tools in this repository should not be considered formal investment, valuation, legal or financial advice without appropriate professional review.

⸻

Author

Lyubomir Mladenov

Commercial Real Estate | Investment & Market Analytics | Python | SQL | Excel | Power BI

I’d use this as the initial version and gradually shorten the Roadmap as you actually build each component. The README will then double as both project documentation and a strong portfolio piece for data/real-estate roles.