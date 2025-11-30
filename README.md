
# 🚀 Getting Started with Django

A comprehensive guide to set up and run a Django web application with different database backends.

---

## 📋 Table of Contents
1. [Prerequisites](#prerequisites)
2. [Installation Steps](#installation-steps)
3. [Database Configuration](#database-configuration)
4. [Development Server](#development-server)
5. [Next Steps](#next-steps)

---

## 📦 Prerequisites

Before you begin, ensure you have the following installed:
- **Python** 3.8 or higher
- **pip** (Python package manager)

---

## 🔧 Installation Steps

### Step 1️⃣ Create a Virtual Environment
```bash
python -m venv "venv name"
```

### Step 2️⃣ Activate Virtual Environment

**For Windows:**
```bash
venv\Scripts\activate
```

**For macOS/Linux:**
```bash
source venv/bin/activate
```

### Step 3️⃣ Install Django
```bash
pip install django
```

### Step 4️⃣ Create a Django Project
```bash
django-admin startproject Getting_started_with_Django
cd Getting_started_with_Django
```

### Step 5️⃣ Create a Django App
```bash
python manage.py startapp myapp
```

### Step 6️⃣ Configure Your Database
Choose your preferred database below and update `settings.py` accordingly.

### Step 7️⃣ Run Migrations
```bash
python manage.py migrate
```

### Step 8️⃣ Create a Superuser Account
```bash
python manage.py createsuperuser
```

---

## 🗄️ Database Configuration

### 📊 Option 1: SQLite (Default)

**Best for:** Development and small projects

SQLite is configured by default and requires no additional setup. The database file `db.sqlite3` is automatically created.

```python
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.sqlite3',
        'NAME': BASE_DIR / 'db.sqlite3',
    }
}
```

---

### 🐘 Option 2: PostgreSQL

**Best for:** Production and large-scale applications

#### Step 1: Install PostgreSQL Driver
```bash
pip install psycopg2-binary
```

#### Step 2: Update `settings.py`
Replace the DATABASES configuration with:
```python
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql',
        'NAME': 'your_database_name',
        'USER': 'your_postgres_user',
        'PASSWORD': 'your_password',
        'HOST': 'localhost',
        'PORT': '5432',
    }
}
```

#### Step 3: Create Database
```bash
createdb your_database_name
```

#### Step 4: Run Migrations
```bash
python manage.py migrate
```

---

### 🐬 Option 3: MySQL

**Best for:** Shared hosting and flexible deployments

#### Step 1: Install MySQL Driver

**Option A: Using mysqlclient**
```bash
pip install mysqlclient
```

**Option B: Using PyMySQL**
```bash
pip install PyMySQL
```

#### Step 2: Update `settings.py`
Replace the DATABASES configuration with:
```python
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.mysql',
        'NAME': 'your_database_name',
        'USER': 'root',
        'PASSWORD': 'your_password',
        'HOST': 'localhost',
        'PORT': '3306',
    }
}
```

**If using PyMySQL**, add this to your project's `__init__.py`:
```python
import pymysql
pymysql.install_as_MySQLdb()
```

#### Step 3: Create Database
```bash
mysql -u root -p
CREATE DATABASE your_database_name;
EXIT;
```

#### Step 4: Run Migrations
```bash
python manage.py migrate
```

---

## 🚀 Development Server

### Step 1: Start the Development Server
```bash
python manage.py runserver
```

### Step 2: Open Your Browser
Visit `http://127.0.0.1:8000/` to see your Django application.

### Step 3: Access Django Admin
Visit `http://127.0.0.1:8000/admin/` and log in with your superuser credentials.

---

## 📝 Next Steps

After installation, enhance your Django application by:

- ✅ **Create Views** - Add business logic in `myapp/views.py`
- ✅ **Define URL Patterns** - Route URLs in `myapp/urls.py`
- ✅ **Create Templates** - Design HTML pages in `myapp/templates/`
- ✅ **Register Models** - Add models to admin in `myapp/admin.py`
- ✅ **Configure Database** - Set up your chosen database in `settings.py`

---

## 📚 Useful Commands

```bash
# Create database migrations
python manage.py makemigrations

# Apply migrations
python manage.py migrate

# Create superuser
python manage.py createsuperuser

# Start development server
python manage.py runserver

# Interactive shell
python manage.py shell

# Collect static files
python manage.py collectstatic
```

---

## 🆘 Troubleshooting

- **Import errors:** Ensure your virtual environment is activated
- **Database errors:** Verify database credentials in `settings.py`
- **Port 8000 in use:** Run `python manage.py runserver 8001` to use a different port

---

**Happy Coding! 🎉**
