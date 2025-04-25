# CSVtoSQLCreate

**CSVtoSQLCreate** is a Python-based web tool that allows users to upload or paste CSV data and automatically generates SQL `CREATE TABLE` and `INSERT` statements using metadata embedded in the CSV file itself. The application is built using **Flask** and does not rely on JavaScript frameworks, ensuring simplicity, transparency, and ease of use.

---

## 🧩 Project Purpose

This tool is built to streamline the process of database initialization from spreadsheet formats used by business analysts, data engineers, and software developers. It interprets table schema and relationship metadata directly from CSV files using:

- **Row 1**: Column names
- **Row 2**: Key indicators
  - `1` = Primary Key
  - `2` = Foreign Key
- **Row 3+**: Data rows to generate `INSERT` statements

Foreign keys without known reference tables will be marked with `<Placeholder>`.

---

## 📁 Project Structure

```plaintext
CSVtoSQLCreate/
├── app/
│   ├── __init__.py              # Python package init
│   ├── main.py                  # Flask app entry point and routing
│   ├── parser.py                # Logic to parse CSV and generate SQL
│   ├── utils.py                 # Type inference, placeholder logic, etc.
├── templates/
│   └── index.html               # HTML form for upload and text paste
├── static/
│   └── style.css                # Optional: simple CSS styling
├── example/
│   └── sample.csv               # Example CSV for reference/testing
├── .gitignore                   # Ignoring .pyc, env, etc.
├── README.md                    # This documentation
└── requirements.txt             # Python package dependencies

---
##💡 Features
✅ CSV Interpretation
Header row becomes SQL column names.

Second row is metadata for primary (1) or foreign (2) keys.

Data from the third row onward will be transformed into SQL INSERT statements.

✅ SQL Generation
CREATE TABLE generation includes:

Primary key constraints

Placeholder for unknown foreign key constraints

Basic type inference (e.g., INT, VARCHAR)

INSERT INTO for all valid rows following the second.

✅ UI Features (HTML)
File upload or CSV text paste area

"Generate SQL" button

Output displayed in a read-only textbox

"Copy" button to copy the result for use in SQL IDEs

⚙️ Planned Enhancements
 Auto-detect datatype based on data rows

 Allow user-defined foreign key relationships

 Optional checkbox to auto-generate DROP TABLE IF EXISTS

 Light/dark UI theme

 Export SQL to file

📦 Requirements
Python 3.8+
Flask
Pandas



