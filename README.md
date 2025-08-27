# dbt Northwind Analytics

A comprehensive data analytics project utilizing **dbt**, **PostgreSQL**, and **Supabase** to transform and analyze the Northwind database. This project demonstrates modern data transformation practices and provides actionable business insights through structured data models.

## 🎯 Project Overview

This project transforms raw Northwind database data into clean, structured analytics models that provide insights into customer behavior, product performance, and regional sales analysis. The transformed data is pushed to **Supabase** for further analysis, reporting, and application integration.

## 🏗️ Architecture

- **Data Source**: Northwind database (classic sample database)
- **Transformation Engine**: dbt (data build tool)
- **Database**: PostgreSQL
- **Data Warehouse**: Supabase
- **Analytics Layer**: Structured marts and staging models

## 📊 Data Models

### Staging Layer (`models/staging/`)
- **schema.yml**: Configuration and documentation for staging models
- Raw data ingestion and initial cleaning

### Marts Layer (`models/marts/sales/`)

#### Customer Analytics
- **`customer_orders.sql`**: Analyzes customer orders to derive insights into customer purchasing behavior
  - Order counts per customer
  - Total order amounts
  - Product quantities per order

- **`customer_segmentation.sql`**: Segments customers based on order count and total spend for targeted marketing strategies
  - Customer value segmentation (High/Mid/Low Value)
  - Order frequency analysis
  - Total customer spend

#### Product Analytics
- **`product_sales.sql`**: Analyzes product sales to identify top-performing products and optimize inventory
  - Product order counts
  - Total sales revenue per product
  - Product performance metrics

#### Regional Analytics
- **`revenue_by_region.sql`**: Understanding revenue distribution across different shipping regions
  - Regional order counts
  - Total sales by region
  - Geographic performance analysis

## 🚀 Getting Started

### Prerequisites
- dbt CLI installed
- Access to Northwind database
- Supabase project configured

### Installation
```bash
# Clone the repository
git clone <repository-url>
cd dbt_northwind

# Install dependencies
dbt deps

# Configure your profile in ~/.dbt/profiles.yml
```

### Running the Project
```bash
# Run all models
dbt run

# Run specific models
dbt run --select marts.sales

# Run tests
dbt test

# Generate documentation
dbt docs generate
dbt docs serve
```

## 🔄 Data Flow

1. **Extract**: Raw data from Northwind database
2. **Transform**: dbt models clean, aggregate, and structure the data
3. **Load**: Transformed data is pushed to Supabase for analytics and application use
4. **Analyze**: Business intelligence and reporting from the transformed data

## 📈 Key Insights

The models provide insights into:
- Customer purchasing patterns and segmentation
- Product performance and sales trends
- Regional sales distribution
- Order volume and revenue analysis

## 🛠️ Technologies Used

- **dbt**: Data transformation and modeling
- **PostgreSQL**: Source database
- **Supabase**: Data warehouse and analytics platform
- **SQL**: Data transformation language

## 📝 Project Structure

```
dbt_northwind/
├── models/
│   ├── staging/          # Raw data ingestion
│   └── marts/
│       └── sales/        # Business-ready sales analytics
├── analyses/             # Ad-hoc analyses
├── macros/               # Reusable dbt macros
├── tests/                # Data quality tests
├── seeds/                # Static data files
└── snapshots/            # Type 2 SCD tracking
```

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests for new functionality
5. Submit a pull request

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

---

**Note**: This project demonstrates best practices for data transformation using dbt and provides a foundation for building comprehensive analytics solutions with Supabase.
