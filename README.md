# SPIS – Special Project Information System (Redesign)

A Django web application for managing, browsing, and tracking Special Project (SP) submissions by BS Computer Science, BS Biochemistry, and BS Applied Physics students at UP Manila.  
This is a redesigned and improved version of the original [DSpace archive](http://dspace.cas.upm.edu.ph/jspui/handle/123456789/5), with a modern interface and additional functionality.

---

## 🔧 Features

- Google SSO login for faculty and staff
- Role-based dashboards for Students, Faculty, and Staff
- Search and filter SPs by:
  - Title, Year, Adviser, Semester, Tags
- Online PDF viewer for uploaded SP documents
- Manual and CSV bulk upload support (for staff)
- Data scraping from DSpace
- Tag and metadata management
- Statistics Dashboard (SP trends, counts by year/category)

---

## 🛠 Tech Stack

- **Framework**: Django (Python)
- **Database**: PostgreSQL
- **Frontend**: HTML, CSS, Bootstrap
- **OAuth**: Google login (`django-allauth`)
- **Web scraping**: BeautifulSoup
- **Others**: Django ORM, crispy forms, modal popups

---

## 🖥️ Setup Instructions

###  1. Create PostgreSQL database

Open terminal and run:

```sql
psql -U postgres
CREATE DATABASE spis_db; 
```


### 2. Clone the repository
```
git clone https://github.com/smpuang/128SPIS-UPM
cd spis_project
```


### 3. Create & activate virtual environment
```
python -m venv venv
```
For Windows:
```
.\venv\Scripts\activate
```
For macOS/Linux:
```
source venv/bin/activate
```


### 4. Install dependencies
```
pip install -r requirements.txt
```


### 5. Migrate the database
```
python manage.py makemigrations
python manage.py migrate
```


### 6. Optional: Scrape DSpace data
```
python manage.py scrape_dspace
```


### 7. Run the server
```
python manage.py runserver
```


### 8. Create a superuser
```
python manage.py createsuperuser
```


### .env Format
Create a .env file at the root with:
```
SECRET_KEY=your-django-secret-key
DEBUG=True

DB_NAME=spis_db
DB_USER=postgres
DB_PASSWORD=yourpassword
DB_HOST=localhost
DB_PORT=5432

GOOGLE_CLIENT_ID=your-google-client-id
GOOGLE_CLIENT_SECRET=your-google-client-secret
```
