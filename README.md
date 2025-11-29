# Aqua Check - Water Quality Monitoring System

**Aqua Check** is a web-based application designed to monitor, record, and analyze river water quality across various regions. This application helps users compare water quality parameters (pH, Ammonia, BOD, TDS) against World Health Organization (WHO) standards and visualize the data effectively.

## Key Features

* Authentication: Secure Login and Registration system.
* Data Input: Forms to input water testing data (Region, District, River, and chemical parameters).
* Automated Analysis: Automatically compares input results with WHO standards to determine if the water is safe or not.
* Data Visualization: Generates real-time Bar Charts using Matplotlib and Seaborn to visualize test results against standard benchmarks.
* Responsive Design: Clean and user-friendly interface built with Bootstrap 5.

## Tech Stack

* Backend: Python (Flask Microframework)
* Database: MySQL (PyMySQL driver)
* Data Science & Plotting: Pandas, Matplotlib, Seaborn
* Frontend: HTML5, CSS3, Bootstrap 5

## Installation & Setup

Follow these steps to run the project on your local machine:

### 1. Clone the Repository (or download the zip)
```bash
git clone [https://github.com/your-username/Aqua-Check.git](https://github.com/your-username/Aqua-Check.git)
cd Aqua-Check
```

### 2. Set up Virtual Environment (Recommended)
```
python -m venv venv
# Windows
venv\Scripts\activate
# Mac/Linux
source venv/bin/activate
```

### 3. Install Dependencies

Install all required libraries listed in requirements.txt:
```
pip install -r requirements.txt
```
### 4. Database Configuration

This application uses MySQL. You need to create the database and tables before running the app.
1.  Open your MySQL client (phpMyAdmin or Workbench).
2. Create a database named aqua_web.
3. Run the following SQL query to create the necessary tables:
```
USE aqua_web;

-- Users Table
CREATE TABLE users (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100),
    email VARCHAR(100) UNIQUE,
    password VARCHAR(255)
);

-- Water Tests Table
CREATE TABLE water_tests (
    id INT AUTO_INCREMENT PRIMARY KEY,
    user_id INT,
    wilayah VARCHAR(100),
    kecamatan VARCHAR(100),
    sungai VARCHAR(100),
    ph FLOAT,
    Amonia FLOAT,
    `BOD(Biological_Oxygen_Demand)` FLOAT,
    `TDS(Total_Dissolved_Solids)` FLOAT,
    FOREIGN KEY (user_id) REFERENCES users(id)
);
```

### 5. Important: Update the database configuration in app.py if your MySQL username/password differs from the default:
```
db_connection = pymysql.connect(
    host="localhost",
    user="root",      # Update your user
    password="",      # Update your password
    database="aqua_web"
)
```

### 6. Run the Application
```
python app.py
```

## Screenshot
<img width="1911" height="805" alt="image" src="https://github.com/user-attachments/assets/77e98790-a14c-473f-b221-e836a0417b2b" />

