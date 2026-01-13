# Transforming Data for Salesforce Imports

### Impact
This project replaces repetitive, manual Excel-based preprocessing with an automated Python workflow. It reduces human error, improves data consistency, supports scalable future imports, and saves over an hour of manual work per import cycle.

### Overview
This project automates the transformation and preparation of auction and trustee data from multiple source systems for import into Salesforce. The raw source data requires extensive cleaning, normalization, validation, and reconciliation before it can be successfully imported into the Salesforce Leads object and related lookup fields.

The pipeline ensures that all output files conform to Salesforce data type requirements, lookup dependencies, and business rules, enabling reliable and repeatable imports.

### Why This Matters
This project demonstrates the practical application of data engineering principles in a real-world Salesforce environment. It improves operational efficiency, reduces risk during imports, and provides a scalable foundation for future automation.

### Key Features
- Automated data cleaning and validation
- Entity matching and lookup reconciliation
- Conditional business rule enforcement
- Salesforce-compatible CSV outputs
- Audit and review support for unmatched records

### Data Structure
The repository is organized to clearly separate raw inputs, reference data, processed outputs, and transformation logic.
- **auction_data/**:
Raw, unmodified source files received from external auction systems.
- **sf_data/**:
Salesforce reference data used for validation, lookup matching, and reconciliation.
- **export_data/**:
Fully transformed, validated, Salesforce-compatible CSV files ready for import.
- **Notebooks (*.ipynb)**:
Contain the transformation logic, validation steps, and diagnostic outputs for each import workflow.

### Problems and Solutions

- Source Data is not Salesforce-Ready
    - Implemented a Python-based data transformation pipeline using pandas to standardize formats, enforce data types, handle null values, and prepare Salesforce-compatible output files automatically.
- Inconsistent naming conventions across systems
    - Created normalized representations of names to enable consistent comparisons. Applied multi-step matching logic to reconcile auction trustee records with existing Salesforce Contacts, significantly improving match rates.
- Lookup Field Dependencies and Missing References
    - Built validation checks and fallback matching logic to populate trustee lookup fields when possible and surface unmatched records for review, ensuring import readiness and data integrity.
- Conditional Business Rules Were Applied Manually
    - Automated conditional logic to enforce business rules programmatically, ensuring consistent application of status-based field updates across all records.
- Limited Visibility Into Data Quality Issues
    - Generated diagnostic outputs highlighting unmatched trustees and normalization results, enabling targeted review and continuous data quality improvement.

### Technologies Used
- Python
- pandas
- NumPy
- Salesforce Data Import Wizard
- VS Code/ Jupyter notebooks
