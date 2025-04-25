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
