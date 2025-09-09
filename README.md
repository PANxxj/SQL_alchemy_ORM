# 🚀 FastAPI + SQLAlchemy + Alembic: Complete Professional Guide

[![FastAPI](https://img.shields.io/badge/FastAPI-005571?style=for-the-badge&logo=fastapi)](https://fastapi.tiangolo.com/)
[![SQLAlchemy](https://img.shields.io/badge/SQLAlchemy-FCA121?style=for-the-badge&logo=sqlalchemy&logoColor=white)](https://www.sqlalchemy.org/)
[![Alembic](https://img.shields.io/badge/Alembic-4B8BBE?style=for-the-badge&logo=alembic&logoColor=white)](https://alembic.sqlalchemy.org/)
[![PostgreSQL](https://img.shields.io/badge/PostgreSQL-316192?style=for-the-badge&logo=postgresql&logoColor=white)](https://www.postgresql.org/)
[![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)

> **Enterprise-Grade API Development**: Master FastAPI with SQLAlchemy ORM and Alembic migrations from absolute basics to production-ready applications. Everything explained in the simplest way possible with detailed JSON outputs.

## Overview

**Think of it like:** FastAPI is your restaurant's ordering system, SQLAlchemy is your kitchen that prepares the food (database operations), and Alembic is your recipe book that keeps track of how your menu (database structure) changes over time.

This comprehensive guide covers FastAPI + SQLAlchemy + Alembic from absolute beginner to advanced professional level, with detailed explanations, real-world examples, and complete JSON outputs for every operation.

### Target Audience
- **Absolute Beginners**: New to web APIs and databases
- **Intermediate Developers**: Know some Python, want to learn modern API development
- **Advanced Engineers**: Looking for production patterns and optimization techniques
- **Enterprise Teams**: Need scalable, maintainable API architecture

### Prerequisites
- Basic Python knowledge (variables, functions, classes)
- Basic understanding of databases (tables, rows, columns)
- Text editor or IDE (VS Code recommended)

## Architecture Overview

```mermaid
graph TB
    A[Client/Frontend] --> B[FastAPI Routes]
    B --> C[Pydantic Models]
    C --> D[Business Logic]
    D --> E[SQLAlchemy ORM]
    E --> F[Database]
    G[Alembic Migrations] --> F
    
    subgraph "FastAPI Application"
        B
        C
        D
    end
    
    subgraph "Data Layer"
        E
        F
        G
    end
```

**Simple Explanation:**
1. **Client** sends HTTP requests (like ordering food)
2. **FastAPI Routes** receive requests (like a waiter taking your order)
3. **Pydantic Models** validate data (like checking if your order is valid)
4. **Business Logic** processes the request (like the chef preparing your meal)
5. **SQLAlchemy ORM** talks to database (like the kitchen storage system)
6. **Database** stores your data (like the actual food storage)
7. **Alembic** manages database changes (like updating recipes and menu items)

## 🚀 **Quick Start Guide**

**⏱️ Just want to get started? Choose your path:**

| 👤 **I'm New to FastAPI/SQLAlchemy** | 🔧 **I need specific help** | 🎯 **I'm building production apps** |
|------|------|------|
| → [30-Minute Starter](#30-minute-starter) | → [Quick Reference Cards](#quick-reference) | → [Production Checklist](#production-ready) |
| → [Basic Tutorial Path](#basic-tutorial) | → [Common Problems](#troubleshooting) | → [Advanced Patterns](#expert-patterns) |

---

## 📚 **Learning Paths** 

### 🌱 **Path 1: Complete Beginner** (2-3 hours)
```
Start Here → Setup → Basic Models → Simple CRUD → First API
     ↓
 [30-min Starter] → [Basic Models] → [CRUD Ops] → [Your First API]
```

### 🔧 **Path 2: I Know FastAPI, New to SQLAlchemy** (1-2 hours)  
```
Database → Models → Relationships → Queries → Migrations
    ↓
[SQLAlchemy Setup] → [Model Design] → [Advanced Queries] → [Alembic]
```

### 🎯 **Path 3: I Know Both, Show Me Best Practices** (30 min)
```
Patterns → Performance → Production → Advanced Topics
    ↓  
[Design Patterns] → [Optimization] → [Deployment] → [Expert Tips]
```

---

## 📖 **Table of Contents**

> **💡 Tip**: Use the learning paths above, or jump directly to any section you need.

<details>
<summary><strong>📋 Full Table of Contents</strong> (Click to expand)</summary>

### 🚀 **QUICK START** (Get Running Fast)
- [⚡ 30-Minute Starter](#30-minute-starter) - Get a working API in 30 minutes
- [🎯 Quick Reference Cards](#quick-reference-cards) - Cheat sheets for common tasks  
- [🆘 Common Issues & Solutions](#common-issues-solutions) - Fix problems fast

### 🏗️ **FOUNDATION** (Core Architecture) 
- [📦 Project Setup](#project-setup-and-environment) - Environment & dependencies
- [🏛️ FastAPI Structure](#fastapi-application-structure) - App architecture
- [🗄️ SQLAlchemy Config](#sqlalchemy-configuration) - Database setup  
- [🔄 Alembic Migrations](#complete-alembic-migration-guide) - Version control for DB

### ⚙️ **DEVELOPMENT** (Building Your App)
- [📋 Model Design](#model-design-patterns) - Create database tables
- [🔗 Relationships](#database-relationships) - Connect your data
- [📝 Pydantic Schemas](#pydantic-schemas) - Data validation
- [🔌 Database Connections](#database-connection-management) - Session management

### 🔍 **QUERYING** (Working with Data)
- [📊 Basic Queries](#basic-queries-beginner-level) - SELECT, WHERE, ORDER BY
- [🔗 JOIN Operations](#advanced-queries-joins-most-important) - Connect tables
- [📈 Aggregations](#advanced-aggregation-and-analytics) - COUNT, SUM, GROUP BY
- [🎯 Complex Patterns](#subqueries-and-complex-query-patterns) - Subqueries & advanced

### 🚀 **PRODUCTION** (Scale & Deploy)
- [⚡ Performance](#performance-optimization) - Speed up your queries
- [🧪 Testing](#testing-patterns) - Ensure quality
- [🔒 Security](#security-implementation) - Keep data safe
- [🌐 Deployment](#production-deployment) - Go live safely

### 🎓 **ADVANCED** (Expert Level)
- [🏗️ Architecture Patterns](#advanced-patterns) - Enterprise designs
- [📊 Monitoring](#monitoring-observability) - Track performance  
- [🔧 Troubleshooting](#migration-best-practices-and-troubleshooting) - Debug issues
- [💡 Best Practices](#best-practices-summary) - Expert tips

</details>

---

## ⚡ **30-Minute Starter**

**🎯 Goal**: Get a working FastAPI + SQLAlchemy API running in 30 minutes.

### **📋 What You'll Build**
A simple product API that can:
- ✅ Create products
- ✅ List products  
- ✅ Update products
- ✅ Delete products

### **⏱️ Time Breakdown**
- **10 min**: Setup & installation
- **10 min**: Create models & database
- **10 min**: Build API endpoints & test

### **🚀 Let's Go!**

#### Step 1: Install Dependencies (2 minutes)
```bash
pip install fastapi sqlalchemy alembic uvicorn[standard] psycopg2-binary
```

#### Step 2: Create Project Structure (1 minute)
```
my_api/
├── main.py          # FastAPI app
├── models.py        # Database models  
├── database.py      # DB connection
└── schemas.py       # Pydantic models
```

#### Step 3: Database Connection (2 minutes)
```python
# database.py
from sqlalchemy import create_engine
from sqlalchemy.ext.declarative import declarative_base
from sqlalchemy.orm import sessionmaker

DATABASE_URL = "sqlite:///./test.db"  # Simple SQLite for starter

engine = create_engine(DATABASE_URL, connect_args={"check_same_thread": False})
SessionLocal = sessionmaker(autocommit=False, autoflush=False, bind=engine)
Base = declarative_base()

def get_db():
    db = SessionLocal()
    try:
        yield db
    finally:
        db.close()
```

#### Step 4: Create Your First Model (3 minutes)
```python
# models.py
from sqlalchemy import Column, Integer, String, Float, Boolean, DateTime
from sqlalchemy.sql import func
from database import Base

class Product(Base):
    __tablename__ = "products"
    
    id = Column(Integer, primary_key=True, index=True)
    name = Column(String, index=True)
    price = Column(Float)
    is_active = Column(Boolean, default=True)
    created_at = Column(DateTime, server_default=func.now())
```

#### Step 5: Pydantic Schemas (2 minutes)
```python
# schemas.py
from pydantic import BaseModel
from datetime import datetime
from typing import Optional

class ProductBase(BaseModel):
    name: str
    price: float
    is_active: bool = True

class ProductCreate(ProductBase):
    pass

class Product(ProductBase):
    id: int
    created_at: datetime
    
    class Config:
        from_attributes = True
```

#### Step 6: FastAPI App with CRUD (10 minutes)
```python
# main.py
from fastapi import FastAPI, Depends, HTTPException
from sqlalchemy.orm import Session
from typing import List

import models, schemas
from database import engine, get_db

# Create tables
models.Base.metadata.create_all(bind=engine)

app = FastAPI(title="My Product API", version="1.0.0")

# Create product
@app.post("/products/", response_model=schemas.Product)
def create_product(product: schemas.ProductCreate, db: Session = Depends(get_db)):
    db_product = models.Product(**product.dict())
    db.add(db_product)
    db.commit()
    db.refresh(db_product)
    return db_product

# Get all products
@app.get("/products/", response_model=List[schemas.Product])
def read_products(skip: int = 0, limit: int = 10, db: Session = Depends(get_db)):
    products = db.query(models.Product).offset(skip).limit(limit).all()
    return products

# Get single product
@app.get("/products/{product_id}", response_model=schemas.Product)  
def read_product(product_id: int, db: Session = Depends(get_db)):
    product = db.query(models.Product).filter(models.Product.id == product_id).first()
    if not product:
        raise HTTPException(status_code=404, detail="Product not found")
    return product

# Update product
@app.put("/products/{product_id}", response_model=schemas.Product)
def update_product(product_id: int, product: schemas.ProductCreate, db: Session = Depends(get_db)):
    db_product = db.query(models.Product).filter(models.Product.id == product_id).first()
    if not db_product:
        raise HTTPException(status_code=404, detail="Product not found")
    
    for key, value in product.dict().items():
        setattr(db_product, key, value)
    
    db.commit()
    db.refresh(db_product)
    return db_product

# Delete product  
@app.delete("/products/{product_id}")
def delete_product(product_id: int, db: Session = Depends(get_db)):
    db_product = db.query(models.Product).filter(models.Product.id == product_id).first()
    if not db_product:
        raise HTTPException(status_code=404, detail="Product not found")
    
    db.delete(db_product)
    db.commit()
    return {"message": "Product deleted successfully"}
```

#### Step 7: Run Your API (1 minute)
```bash
uvicorn main:app --reload
```

#### Step 8: Test It! (2 minutes)
Open http://localhost:8000/docs and try:
- ✅ POST `/products/` - Create a product
- ✅ GET `/products/` - List products
- ✅ GET `/products/1` - Get specific product
- ✅ PUT `/products/1` - Update product
- ✅ DELETE `/products/1` - Delete product

### **🎉 Congratulations!** 
You built a working API in 30 minutes! 

**🔄 What's Next?**
- [Add more fields to your model](#model-design-patterns)
- [Set up proper database](#sqlalchemy-configuration)  
- [Add relationships](#database-relationships)
- [Learn advanced queries](#advanced-queries-joins-most-important)

---

## 🎯 **Quick Reference Cards**

### **📊 Most Common Queries**

<details>
<summary><strong>🔍 Basic Queries Cheat Sheet</strong></summary>

```python
# Get all records
products = db.query(Product).all()

# Get by ID  
product = db.query(Product).filter(Product.id == 1).first()
# or
product = db.get(Product, 1)

# Filter records
active_products = db.query(Product).filter(Product.is_active == True).all()
expensive = db.query(Product).filter(Product.price > 100).all()

# Order and limit
latest = db.query(Product).order_by(Product.created_at.desc()).limit(10).all()

# Count
total = db.query(Product).count()
active_count = db.query(Product).filter(Product.is_active == True).count()
```

</details>

<details>
<summary><strong>🔗 JOIN Queries Cheat Sheet</strong></summary>

```python
# Inner join
products_with_categories = (
    db.query(Product)
    .join(Category)
    .all()
)

# Left join (get all products, even without categories)
all_products_with_optional_categories = (
    db.query(Product)
    .outerjoin(Category)
    .all()
)

# Join with additional columns
results = (
    db.query(Product, Category.name.label('category_name'))
    .join(Category)
    .all()
)
```

</details>

<details>
<summary><strong>🔄 Migration Commands Cheat Sheet</strong></summary>

```bash
# Create migration from model changes
alembic revision --autogenerate -m "Add products table"

# Apply all pending migrations
alembic upgrade head

# Rollback one migration
alembic downgrade -1

# Check current migration status
alembic current

# See migration history
alembic history
```

</details>

### **🆘 Common Issues & Quick Fixes**

<details>
<summary><strong>❌ "Table doesn't exist" Error</strong></summary>

**Problem**: `Table 'products' doesn't exist`

**Quick Fix**:
```python
# Add this to create tables
from database import engine
import models
models.Base.metadata.create_all(bind=engine)
```

**Better Solution**: Use Alembic migrations
```bash
alembic init alembic
alembic revision --autogenerate -m "Initial migration"  
alembic upgrade head
```

</details>

<details>
<summary><strong>❌ "No module named" Import Error</strong></summary>

**Problem**: Import errors between files

**Quick Fix**: Check your project structure and imports
```python
# If files are in same directory
from models import Product
from database import get_db

# If using packages, add __init__.py files
```

</details>

---

## 📖 **Detailed Documentation**

> **💡 Ready to dive deeper?** The sections below contain comprehensive guides for each topic.

### 🏗️ **FOUNDATION** (Core Architecture)
1. [Project Setup and Environment](#project-setup-and-environment)
2. [FastAPI Application Structure](#fastapi-application-structure)
3. [SQLAlchemy Configuration](#sqlalchemy-configuration)
4. [Alembic Migration Setup](#alembic-migration-setup)

### ⚙️ **DEVELOPMENT PATTERNS** (Implementation)
5. [Model Design Patterns](#model-design-patterns)
6. [Pydantic Schemas](#pydantic-schemas)
7. [Database Connection Management](#database-connection-management)
8. [Dependency Injection](#dependency-injection)

### 🔍 **QUERYING MASTERY** (Data Operations)
9. [Basic CRUD Operations](#basic-crud-operations)
10. [Database Relationships](#database-relationships)
11. [Advanced Querying Techniques](#advanced-querying-techniques)
12. [Aggregation and Analytics](#aggregation-and-analytics)

### 🚀 **PERFORMANCE & SCALE** (Production Ready)
13. [Performance Optimization](#performance-optimization)
14. [Async Database Operations](#async-database-operations)
15. [Caching Strategies](#caching-strategies)
16. [Background Tasks](#background-tasks)

### 🧪 **TESTING & QUALITY** (Best Practices)
17. [Testing Patterns](#testing-patterns)
18. [API Documentation](#api-documentation)
19. [Error Handling](#error-handling)
20. [Production Deployment](#production-deployment)

---

## 🏗️ FOUNDATION

### Project Setup and Environment

**Think of it like:** Setting up your kitchen before you start cooking - you need all the right tools and ingredients ready.

#### 1. Create Project Structure

```bash
# Create project directory
mkdir fastapi-ecommerce
cd fastapi-ecommerce

# Create virtual environment
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Create project structure
mkdir -p {app/{api,core,models,schemas,crud,db},alembic/versions,tests}
touch app/__init__.py app/main.py app/api/__init__.py app/core/__init__.py
touch app/models/__init__.py app/schemas/__init__.py app/crud/__init__.py app/db/__init__.py
```

**Project Structure:**
```
fastapi-ecommerce/
├── app/
│   ├── __init__.py
│   ├── main.py              # FastAPI application entry point
│   ├── api/                 # API routes
│   │   ├── __init__.py
│   │   ├── deps.py          # Dependencies
│   │   └── endpoints/       # Route endpoints
│   ├── core/                # Core functionality
│   │   ├── __init__.py
│   │   ├── config.py        # Configuration settings
│   │   └── security.py      # Authentication/authorization
│   ├── crud/                # CRUD operations
│   │   ├── __init__.py
│   │   └── base.py          # Base CRUD operations
│   ├── db/                  # Database related
│   │   ├── __init__.py
│   │   ├── base.py          # Base model class
│   │   ├── session.py       # Database session
│   │   └── init_db.py       # Database initialization
│   ├── models/              # SQLAlchemy models
│   │   ├── __init__.py
│   │   └── user.py          # Model definitions
│   └── schemas/             # Pydantic schemas
│       ├── __init__.py
│       └── user.py          # Schema definitions
├── alembic/                 # Database migrations
│   ├── versions/
│   ├── env.py
│   ├── script.py.mako
│   └── alembic.ini
├── tests/                   # Test files
├── requirements.txt         # Dependencies
└── .env                     # Environment variables
```

#### 2. Install Dependencies

```bash
# Install core dependencies
pip install fastapi[all] sqlalchemy psycopg2-binary alembic python-dotenv

# Install development dependencies
pip install pytest pytest-asyncio httpx black isort mypy

# Create requirements.txt
pip freeze > requirements.txt
```

**Requirements.txt Output:**
```txt
fastapi[all]==0.104.1
sqlalchemy==2.0.23
psycopg2-binary==2.9.7
alembic==1.12.1
python-dotenv==1.0.0
uvicorn[standard]==0.24.0
pydantic==2.4.2
pytest==7.4.3
pytest-asyncio==0.21.1
httpx==0.25.1
black==23.10.0
isort==5.12.0
mypy==1.6.1
```

#### 3. Environment Configuration

```python
# .env
DATABASE_URL=postgresql://username:password@localhost:5432/ecommerce_db
SECRET_KEY=your-super-secret-key-here
ALGORITHM=HS256
ACCESS_TOKEN_EXPIRE_MINUTES=30

# Database settings
DB_HOST=localhost
DB_PORT=5432
DB_USER=username
DB_PASSWORD=password
DB_NAME=ecommerce_db

# API settings
API_V1_STR=/api/v1
PROJECT_NAME=E-commerce API
```

```python
# app/core/config.py
from typing import Optional
from pydantic_settings import BaseSettings
from pydantic import PostgresDsn, validator

class Settings(BaseSettings):
    """
    Think of this like: Your application's main control panel
    where you set all the important settings and configurations.
    """
    
    # API Settings
    API_V1_STR: str = "/api/v1"
    PROJECT_NAME: str = "E-commerce API"
    
    # Database Settings
    DATABASE_URL: Optional[PostgresDsn] = None
    DB_HOST: str = "localhost"
    DB_PORT: int = 5432
    DB_USER: str = "username"
    DB_PASSWORD: str = "password"
    DB_NAME: str = "ecommerce_db"
    
    @validator("DATABASE_URL", pre=True)
    def assemble_db_connection(cls, v: Optional[str], values: dict) -> str:
        """Build database URL from individual components if not provided"""
        if isinstance(v, str):
            return v
        return f"postgresql://{values.get('DB_USER')}:{values.get('DB_PASSWORD')}@{values.get('DB_HOST')}:{values.get('DB_PORT')}/{values.get('DB_NAME')}"
    
    # Security Settings
    SECRET_KEY: str = "your-super-secret-key"
    ALGORITHM: str = "HS256"
    ACCESS_TOKEN_EXPIRE_MINUTES: int = 30
    
    class Config:
        env_file = ".env"

# Create global settings instance
settings = Settings()
```

**Configuration Output:**
```json
{
  "configuration": {
    "api_settings": {
      "api_v1_str": "/api/v1",
      "project_name": "E-commerce API"
    },
    "database_settings": {
      "database_url": "postgresql://username:password@localhost:5432/ecommerce_db",
      "host": "localhost",
      "port": 5432,
      "database": "ecommerce_db"
    },
    "security_settings": {
      "algorithm": "HS256",
      "token_expire_minutes": 30
    }
  }
}
```

### SQLAlchemy Configuration

**Think of it like:** Setting up your kitchen's connection to the pantry (database) - you need to know how to get ingredients and where to store them.

#### Database Session Setup

```python
# app/db/session.py
from sqlalchemy import create_engine
from sqlalchemy.ext.declarative import declarative_base
from sqlalchemy.orm import sessionmaker
from app.core.config import settings

# Create database engine
# Think of engine like: The main connection highway to your database
engine = create_engine(
    settings.DATABASE_URL,
    pool_pre_ping=True,  # Verify connections before use
    pool_recycle=3600,   # Recycle connections after 1 hour
    echo=True            # Log all SQL statements (disable in production)
)

# Create session factory
# Think of SessionLocal like: A factory that creates database conversations
SessionLocal = sessionmaker(
    autocommit=False,    # Don't auto-commit transactions
    autoflush=False,     # Don't auto-flush before queries
    bind=engine          # Bind to our database engine
)

# Create base class for models
# Think of Base like: The foundation blueprint for all your data models
Base = declarative_base()

# Dependency to get database session
def get_db():
    """
    Think of this like: A waiter that brings you a fresh database 
    connection when you need it and cleans up when you're done.
    """
    db = SessionLocal()
    try:
        yield db
    finally:
        db.close()
```

#### Base Model with Timestamps

```python
# app/db/base.py
from typing import Any
from sqlalchemy import Column, Integer, DateTime, func
from sqlalchemy.ext.declarative import declared_attr
from app.db.session import Base

class TimestampMixin:
    """
    Think of this like: Adding a timestamp to every document you create,
    so you always know when something was created or last updated.
    """
    
    @declared_attr
    def created_at(cls):
        return Column(DateTime(timezone=True), server_default=func.now(), nullable=False)
    
    @declared_attr
    def updated_at(cls):
        return Column(
            DateTime(timezone=True), 
            server_default=func.now(), 
            onupdate=func.now(), 
            nullable=False
        )

class BaseModel(Base, TimestampMixin):
    """
    Think of this like: The basic template that all your data models 
    will inherit from, giving them common functionality.
    """
    __abstract__ = True
    
    id = Column(Integer, primary_key=True, index=True)
    
    def dict(self) -> dict:
        """Convert model to dictionary"""
        return {c.name: getattr(self, c.name) for c in self.__table__.columns}
    
    def __repr__(self) -> str:
        """String representation of the model"""
        return f"<{self.__class__.__name__}(id={self.id})>"
```

### Alembic Migration Setup

**Think of it like:** Alembic is your database's version control system - like Git for your database structure. It keeps track of all changes you make to your database schema.

#### 1. Initialize Alembic

```bash
# Initialize Alembic in your project
alembic init alembic

# This creates:
# - alembic/ directory with migration files
# - alembic.ini configuration file
```

#### 2. Configure Alembic

```python
# alembic/env.py
from logging.config import fileConfig
from sqlalchemy import engine_from_config, pool
from alembic import context
import os
import sys

# Add your app directory to Python path
sys.path.append(os.path.dirname(os.path.dirname(__file__)))

# Import your models and config
from app.core.config import settings
from app.db.base import Base
from app.models import *  # Import all models

# this is the Alembic Config object
config = context.config

# Set database URL in alembic config
config.set_main_option("sqlalchemy.url", str(settings.DATABASE_URL))

# Interpret the config file for Python logging
if config.config_file_name is not None:
    fileConfig(config.config_file_name)

# Set target metadata for autogenerate support
target_metadata = Base.metadata

def run_migrations_offline() -> None:
    """
    Run migrations in 'offline' mode - generates SQL scripts
    Think of this like: Writing down recipe changes without actually cooking
    """
    url = config.get_main_option("sqlalchemy.url")
    context.configure(
        url=url,
        target_metadata=target_metadata,
        literal_binds=True,
        dialect_opts={"paramstyle": "named"},
    )

    with context.begin_transaction():
        context.run_migrations()

def run_migrations_online() -> None:
    """
    Run migrations in 'online' mode - directly against database
    Think of this like: Actually cooking the recipe changes in your kitchen
    """
    connectable = engine_from_config(
        config.get_section(config.config_ini_section),
        prefix="sqlalchemy.",
        poolclass=pool.NullPool,
    )

    with connectable.connect() as connection:
        context.configure(connection=connection, target_metadata=target_metadata)

        with context.begin_transaction():
            context.run_migrations()

if context.is_offline_mode():
    run_migrations_offline()
else:
    run_migrations_online()
```

```ini
# alembic.ini
[alembic]
script_location = alembic
prepend_sys_path = .
version_path_separator = os
sqlalchemy.url = 

[post_write_hooks]
hooks = black
black.type = console_scripts
black.entrypoint = black
black.options = --line-length 88

[loggers]
keys = root,sqlalchemy,alembic

[handlers]
keys = console

[formatters]
keys = generic

[logger_root]
level = WARN
handlers = console
qualname =

[logger_sqlalchemy]
level = WARN
handlers =
qualname = sqlalchemy.engine

[logger_alembic]
level = INFO
handlers =
qualname = alembic

[handler_console]
class = StreamHandler
args = (sys.stderr,)
level = NOTSET
formatter = generic

[formatter_generic]
format = %(levelname)-5.5s [%(name)s] %(message)s
datefmt = %H:%M:%S
```

---

# 🔄 Complete Alembic Migration Guide

**Think of it like:** Alembic is your database's time machine and version control system. Just like Git tracks code changes, Alembic tracks database schema changes, letting you move forward and backward through database history safely.

## 📋 Migration Lifecycle Overview

```mermaid
graph TB
    A[Model Changes] --> B[Generate Migration]
    B --> C[Review Migration Script]
    C --> D{Migration Looks Good?}
    D -->|No| E[Edit Migration Script]
    E --> C
    D -->|Yes| F[Apply Migration]
    F --> G[Test in Development]
    G --> H{Tests Pass?}
    H -->|No| I[Rollback Migration]
    I --> J[Fix Issues]
    J --> A
    H -->|Yes| K[Deploy to Production]
    K --> L[Monitor Production]
    L --> M{Issues Found?}
    M -->|Yes| N[Rollback in Production]
    M -->|No| O[Migration Complete]
```

## 🎯 Migration States and Visualization

### Database Version States

```
Database Evolution Timeline:

Initial State (No Migrations)
│
├── Migration 001: Create users table
│   ├── [APPLIED] ✅ HEAD -> 001_create_users
│   └── Schema: users table exists
│
├── Migration 002: Add products table
│   ├── [APPLIED] ✅ HEAD -> 002_add_products  
│   └── Schema: users + products tables
│
├── Migration 003: Add foreign keys
│   ├── [PENDING] ⏳ 003_add_foreign_keys
│   └── Schema: Not yet applied
│
└── Future migrations...
    └── [NOT CREATED] 📝
```

---

## 📚 Complete Alembic Command Reference

### 🆕 Creating Migrations

#### 1. Auto-generate Migration from Model Changes

```bash
# Generate migration automatically based on model changes
alembic revision --autogenerate -m "Add user authentication tables"

# What this does:
# ✅ Compares current models with database schema
# ✅ Generates migration script with detected changes
# ✅ Creates timestamped migration file
```

**Generated Migration File Structure:**
```python
"""Add user authentication tables

Revision ID: 1a2b3c4d5e6f
Revises: 
Create Date: 2023-11-20 10:30:45.123456

"""
from typing import Sequence, Union
from alembic import op
import sqlalchemy as sa

# revision identifiers
revision: str = '1a2b3c4d5e6f'
down_revision: Union[str, None] = None
branch_labels: Union[str, Sequence[str], None] = None
depends_on: Union[str, Sequence[str], None] = None

def upgrade() -> None:
    """
    Apply the migration (forward migration)
    Think of this like: Installing new features in your database
    """
    # ### commands auto generated by Alembic - please adjust! ###
    op.create_table('users',
        sa.Column('id', sa.Integer(), nullable=False),
        sa.Column('email', sa.String(length=255), nullable=False),
        sa.Column('hashed_password', sa.String(length=255), nullable=False),
        sa.Column('is_active', sa.Boolean(), nullable=True),
        sa.Column('is_superuser', sa.Boolean(), nullable=True),
        sa.Column('created_at', sa.DateTime(), nullable=True),
        sa.Column('updated_at', sa.DateTime(), nullable=True),
        sa.PrimaryKeyConstraint('id')
    )
    op.create_index(op.f('ix_users_email'), 'users', ['email'], unique=True)
    op.create_index(op.f('ix_users_id'), 'users', ['id'], unique=False)
    # ### end Alembic commands ###

def downgrade() -> None:
    """
    Reverse the migration (rollback)
    Think of this like: Uninstalling features to go back to previous state
    """
    # ### commands auto generated by Alembic - please adjust! ###
    op.drop_index(op.f('ix_users_id'), table_name='users')
    op.drop_index(op.f('ix_users_email'), table_name='users')
    op.drop_table('users')
    # ### end Alembic commands ###
```

#### 2. Create Empty Migration (For Custom Logic)

```bash
# Create empty migration for manual changes
alembic revision -m "Custom data migration for user roles"
```

**Custom Migration Example:**
```python
"""Custom data migration for user roles

Revision ID: 2b3c4d5e6f7g
Revises: 1a2b3c4d5e6f
Create Date: 2023-11-20 11:15:30.789012

"""
from typing import Sequence, Union
from alembic import op
import sqlalchemy as sa
from sqlalchemy.sql import table, column

# revision identifiers
revision: str = '2b3c4d5e6f7g'
down_revision: Union[str, None] = '1a2b3c4d5e6f'
branch_labels: Union[str, Sequence[str], None] = None
depends_on: Union[str, Sequence[str], None] = None

def upgrade() -> None:
    """Complex migration with data transformation"""
    
    # 1. Add new column
    op.add_column('users', sa.Column('role', sa.String(50), nullable=True))
    
    # 2. Data migration - set default roles
    users_table = table('users',
        column('id', sa.Integer),
        column('is_superuser', sa.Boolean),
        column('role', sa.String)
    )
    
    # Update existing users with roles based on is_superuser
    connection = op.get_bind()
    connection.execute(
        users_table.update()
        .where(users_table.c.is_superuser == True)
        .values(role='admin')
    )
    connection.execute(
        users_table.update()
        .where(users_table.c.is_superuser == False)
        .values(role='user')
    )
    
    # 3. Make column non-nullable after data migration
    op.alter_column('users', 'role', nullable=False)

def downgrade() -> None:
    """Reverse the migration"""
    op.drop_column('users', 'role')
```

---

## 🚀 Applying Migrations

### Forward Migrations (Upgrade)

```bash
# Apply all pending migrations
alembic upgrade head

# Apply specific migration
alembic upgrade 1a2b3c4d5e6f

# Apply next migration only
alembic upgrade +1

# Apply migrations up to a specific point
alembic upgrade 2b3c4d5e6f7g
```

**Migration Application Visualization:**
```json
{
  "migration_application": {
    "command": "alembic upgrade head",
    "description": "Apply all pending migrations to bring database to latest state",
    "execution_flow": [
      {
        "step": 1,
        "action": "Check current database version",
        "current_revision": "001_create_users",
        "status": "Found in alembic_version table"
      },
      {
        "step": 2,
        "action": "Identify pending migrations",
        "pending_migrations": [
          "002_add_products",
          "003_add_foreign_keys", 
          "004_add_indexes"
        ],
        "total_pending": 3
      },
      {
        "step": 3,
        "action": "Apply migrations sequentially",
        "migrations_applied": [
          {
            "revision": "002_add_products",
            "description": "Add products table",
            "execution_time_ms": 45,
            "sql_executed": [
              "CREATE TABLE products (...)",
              "CREATE INDEX ix_products_name ON products (name)"
            ],
            "status": "SUCCESS"
          },
          {
            "revision": "003_add_foreign_keys",
            "description": "Add foreign key relationships",
            "execution_time_ms": 23,
            "sql_executed": [
              "ALTER TABLE products ADD CONSTRAINT fk_products_category FOREIGN KEY ..."
            ],
            "status": "SUCCESS"
          },
          {
            "revision": "004_add_indexes",
            "description": "Add performance indexes",
            "execution_time_ms": 67,
            "sql_executed": [
              "CREATE INDEX ix_products_price ON products (price)",
              "CREATE INDEX ix_products_created_at ON products (created_at)"
            ],
            "status": "SUCCESS"
          }
        ]
      },
      {
        "step": 4,
        "action": "Update version tracking",
        "new_head_revision": "004_add_indexes",
        "alembic_version_table_updated": true
      }
    ],
    "final_state": {
      "database_version": "004_add_indexes",
      "total_migrations_applied": 3,
      "total_execution_time_ms": 135,
      "status": "SUCCESS"
    }
  }
}
```

---

## ⏪ Rollback and Reverse Migrations

### Understanding Rollback Strategies

```bash
# Rollback to previous migration
alembic downgrade -1

# Rollback to specific revision
alembic downgrade 1a2b3c4d5e6f

# Rollback all migrations (nuclear option)
alembic downgrade base

# Rollback multiple steps
alembic downgrade -2
```

**Rollback Visualization:**
```mermaid
graph LR
    A[Current: 004_add_indexes] -->|downgrade -1| B[003_add_foreign_keys]
    B -->|downgrade -1| C[002_add_products]  
    C -->|downgrade -1| D[001_create_users]
    D -->|downgrade base| E[Empty Database]
    
    A -->|downgrade 002| C
    A -->|downgrade base| E
```

**Rollback Execution Example:**
```json
{
  "rollback_operation": {
    "command": "alembic downgrade -1",
    "description": "Rollback one migration step",
    "before_state": {
      "current_revision": "004_add_indexes",
      "database_tables": ["users", "products", "categories"],
      "indexes": ["ix_products_price", "ix_products_created_at", "ix_products_name"],
      "foreign_keys": ["fk_products_category"]
    },
    "rollback_execution": {
      "target_revision": "003_add_foreign_keys",
      "migration_to_reverse": "004_add_indexes",
      "downgrade_operations": [
        {
          "operation": "DROP INDEX",
          "sql": "DROP INDEX ix_products_price",
          "execution_time_ms": 12,
          "status": "SUCCESS"
        },
        {
          "operation": "DROP INDEX", 
          "sql": "DROP INDEX ix_products_created_at",
          "execution_time_ms": 8,
          "status": "SUCCESS"
        }
      ],
      "total_operations": 2,
      "total_execution_time_ms": 20
    },
    "after_state": {
      "current_revision": "003_add_foreign_keys",
      "database_tables": ["users", "products", "categories"],
      "indexes": ["ix_products_name"],
      "foreign_keys": ["fk_products_category"],
      "rollback_successful": true
    },
    "recovery_instructions": {
      "to_reapply": "alembic upgrade +1",
      "to_continue_rollback": "alembic downgrade -1",
      "emergency_stop": "Current state is stable"
    }
  }
}
```

---

## 🔍 Migration Information and History

### Viewing Migration Status

```bash
# Show current migration status
alembic current

# Show migration history
alembic history

# Show verbose history with details
alembic history --verbose

# Show pending migrations
alembic show head

# Show specific migration details
alembic show 1a2b3c4d5e6f
```

**Migration History Output:**
```json
{
  "migration_history": {
    "command": "alembic history --verbose",
    "current_head": "004_add_indexes",
    "total_migrations": 4,
    "migration_chain": [
      {
        "revision": "004_add_indexes",
        "parent": "003_add_foreign_keys",
        "branch_labels": null,
        "depends_on": null,
        "description": "Add performance indexes for products",
        "created_date": "2023-11-20 14:30:00",
        "applied_date": "2023-11-20 15:45:12",
        "status": "APPLIED",
        "is_head": true,
        "operations": [
          "CREATE INDEX ix_products_price",
          "CREATE INDEX ix_products_created_at"
        ]
      },
      {
        "revision": "003_add_foreign_keys",
        "parent": "002_add_products", 
        "branch_labels": null,
        "depends_on": null,
        "description": "Add foreign key relationships",
        "created_date": "2023-11-20 13:15:00",
        "applied_date": "2023-11-20 15:44:58",
        "status": "APPLIED",
        "is_head": false,
        "operations": [
          "ADD FOREIGN KEY fk_products_category"
        ]
      },
      {
        "revision": "002_add_products",
        "parent": "001_create_users",
        "branch_labels": null,
        "depends_on": null,
        "description": "Add products table with basic structure",
        "created_date": "2023-11-20 12:00:00",
        "applied_date": "2023-11-20 15:44:32",
        "status": "APPLIED",
        "is_head": false,
        "operations": [
          "CREATE TABLE products",
          "CREATE INDEX ix_products_name"
        ]
      },
      {
        "revision": "001_create_users",
        "parent": null,
        "branch_labels": null,
        "depends_on": null,
        "description": "Initial user authentication system",
        "created_date": "2023-11-20 10:30:00", 
        "applied_date": "2023-11-20 10:35:45",
        "status": "APPLIED",
        "is_head": false,
        "is_base": true,
        "operations": [
          "CREATE TABLE users",
          "CREATE INDEX ix_users_email"
        ]
      }
    ]
  }
}
```

---

## 🏭 Complex Migration Scenarios

### 1. Data Migrations with Transformations

```python
"""Complex data migration: Normalize user data and split name fields

Revision ID: 5c6d7e8f9g0h
Revises: 4b5c6d7e8f9g
Create Date: 2023-11-20 16:20:15.456789

"""
from typing import Sequence, Union
from alembic import op
import sqlalchemy as sa
from sqlalchemy.sql import table, column
from sqlalchemy import String, Integer, DateTime

# revision identifiers
revision: str = '5c6d7e8f9g0h'
down_revision: Union[str, None] = '4b5c6d7e8f9g'
branch_labels: Union[str, Sequence[str], None] = None
depends_on: Union[str, Sequence[str], None] = None

def upgrade() -> None:
    """
    Complex migration: Split full_name into first_name and last_name
    """
    
    # Step 1: Add new columns
    op.add_column('users', sa.Column('first_name', sa.String(100), nullable=True))
    op.add_column('users', sa.Column('last_name', sa.String(100), nullable=True))
    
    # Step 2: Data transformation
    # Create table representation for data manipulation
    users_table = table('users',
        column('id', Integer),
        column('full_name', String),
        column('first_name', String),
        column('last_name', String)
    )
    
    # Get database connection
    connection = op.get_bind()
    
    # Step 3: Migrate existing data
    result = connection.execute(
        sa.select(users_table.c.id, users_table.c.full_name)
        .where(users_table.c.full_name.isnot(None))
    )
    
    for user_id, full_name in result:
        if full_name:
            # Split name (handle edge cases)
            name_parts = full_name.strip().split(' ', 1)
            first_name = name_parts[0] if name_parts else ''
            last_name = name_parts[1] if len(name_parts) > 1 else ''
            
            # Update the record
            connection.execute(
                users_table.update()
                .where(users_table.c.id == user_id)
                .values(
                    first_name=first_name[:100],  # Ensure length limit
                    last_name=last_name[:100]
                )
            )
    
    # Step 4: Handle users without full_name
    connection.execute(
        users_table.update()
        .where(users_table.c.full_name.is_(None))
        .values(first_name='', last_name='')
    )
    
    # Step 5: Make new columns non-nullable
    op.alter_column('users', 'first_name', nullable=False)
    op.alter_column('users', 'last_name', nullable=False)
    
    # Step 6: Add indexes for performance
    op.create_index('ix_users_first_name', 'users', ['first_name'])
    op.create_index('ix_users_last_name', 'users', ['last_name'])
    
    # Step 7: Remove old column (optional - can be done in next migration)
    # op.drop_column('users', 'full_name')

def downgrade() -> None:
    """
    Reverse the migration - reconstruct full_name from parts
    """
    
    # Step 1: Re-add full_name column if it was dropped
    # op.add_column('users', sa.Column('full_name', sa.String(200), nullable=True))
    
    # Step 2: Reconstruct full names
    users_table = table('users',
        column('id', Integer),
        column('first_name', String),
        column('last_name', String),
        column('full_name', String)
    )
    
    connection = op.get_bind()
    
    # Reconstruct full names from parts
    connection.execute(
        users_table.update().values(
            full_name=sa.func.concat(
                users_table.c.first_name,
                sa.text("' '"),
                users_table.c.last_name
            ).op("TRIM")()
        )
    )
    
    # Step 3: Remove new columns and indexes
    op.drop_index('ix_users_last_name', 'users')
    op.drop_index('ix_users_first_name', 'users')
    op.drop_column('users', 'last_name')
    op.drop_column('users', 'first_name')
```

### 2. Schema Migrations with Dependency Management

```python
"""Add product variants with complex relationships

Revision ID: 6d7e8f9g0h1i
Revises: 5c6d7e8f9g0h
Create Date: 2023-11-20 17:45:22.789012

"""
from typing import Sequence, Union
from alembic import op
import sqlalchemy as sa

# revision identifiers
revision: str = '6d7e8f9g0h1i'
down_revision: Union[str, None] = '5c6d7e8f9g0h'
branch_labels: Union[str, Sequence[str], None] = None
depends_on: Union[str, Sequence[str], None] = None

def upgrade() -> None:
    """
    Create product variants system with proper relationships
    """
    
    # Create product_variants table
    op.create_table('product_variants',
        sa.Column('id', sa.Integer(), nullable=False),
        sa.Column('product_id', sa.Integer(), nullable=False),
        sa.Column('sku', sa.String(length=100), nullable=False),
        sa.Column('name', sa.String(length=200), nullable=False),
        sa.Column('price_modifier', sa.Decimal(precision=10, scale=2), nullable=True),
        sa.Column('stock_quantity', sa.Integer(), nullable=False, default=0),
        sa.Column('is_active', sa.Boolean(), nullable=False, default=True),
        sa.Column('created_at', sa.DateTime(), nullable=False, server_default=sa.func.now()),
        sa.Column('updated_at', sa.DateTime(), nullable=False, server_default=sa.func.now(), onupdate=sa.func.now()),
        sa.PrimaryKeyConstraint('id')
    )
    
    # Create variant_attributes table for flexible attributes (color, size, etc.)
    op.create_table('variant_attributes',
        sa.Column('id', sa.Integer(), nullable=False),
        sa.Column('variant_id', sa.Integer(), nullable=False),
        sa.Column('attribute_name', sa.String(length=50), nullable=False),
        sa.Column('attribute_value', sa.String(length=200), nullable=False),
        sa.Column('created_at', sa.DateTime(), nullable=False, server_default=sa.func.now()),
        sa.PrimaryKeyConstraint('id')
    )
    
    # Add foreign key constraints
    op.create_foreign_key(
        'fk_product_variants_product_id',
        'product_variants', 'products',
        ['product_id'], ['id'],
        ondelete='CASCADE'
    )
    
    op.create_foreign_key(
        'fk_variant_attributes_variant_id',
        'variant_attributes', 'product_variants',
        ['variant_id'], ['id'],
        ondelete='CASCADE'
    )
    
    # Add indexes for performance
    op.create_index('ix_product_variants_product_id', 'product_variants', ['product_id'])
    op.create_index('ix_product_variants_sku', 'product_variants', ['sku'], unique=True)
    op.create_index('ix_product_variants_is_active', 'product_variants', ['is_active'])
    op.create_index('ix_variant_attributes_variant_id', 'variant_attributes', ['variant_id'])
    op.create_index('ix_variant_attributes_name_value', 'variant_attributes', ['attribute_name', 'attribute_value'])
    
    # Add check constraints for data integrity
    op.create_check_constraint(
        'ck_product_variants_stock_non_negative',
        'product_variants',
        sa.text('stock_quantity >= 0')
    )

def downgrade() -> None:
    """
    Remove product variants system
    """
    # Drop tables in reverse order (respect foreign keys)
    op.drop_table('variant_attributes')
    op.drop_table('product_variants')
```

---

## 🛠️ Migration Best Practices and Troubleshooting

### Migration Safety Checklist

```json
{
  "migration_safety_checklist": {
    "before_creating_migration": [
      "✅ All model changes are finalized and tested",
      "✅ Migration purpose is clearly documented", 
      "✅ Breaking changes are identified and communicated",
      "✅ Data migration strategy is planned for large datasets"
    ],
    "review_generated_migration": [
      "✅ Auto-generated migration script is reviewed line by line",
      "✅ Data loss potential is assessed and mitigated",
      "✅ Performance impact on large tables is considered",
      "✅ Rollback strategy is tested and verified"
    ],
    "before_applying_to_production": [
      "✅ Migration tested thoroughly in staging environment",
      "✅ Database backup is created and verified",
      "✅ Maintenance window is scheduled if needed",
      "✅ Rollback plan is documented and tested"
    ],
    "monitoring_after_deployment": [
      "✅ Application performance metrics are monitored",
      "✅ Database performance is tracked",
      "✅ Error logs are monitored for issues",
      "✅ Rollback readiness is maintained for 24-48 hours"
    ]
  }
}
```

### Common Migration Problems and Solutions

```json
{
  "migration_troubleshooting": {
    "problem_1": {
      "issue": "Migration fails with 'column already exists' error",
      "cause": "Database state doesn't match migration expectations",
      "solutions": [
        {
          "approach": "Check current database state",
          "command": "alembic current",
          "next_steps": "Compare with migration script"
        },
        {
          "approach": "Manually resolve conflicts",
          "command": "alembic stamp head",
          "warning": "Only if you're certain about database state"
        },
        {
          "approach": "Create corrective migration",
          "command": "alembic revision -m 'Fix column conflict'",
          "description": "Add conditional logic to handle existing columns"
        }
      ]
    },
    "problem_2": {
      "issue": "Large table migration takes too long and locks database",
      "cause": "Migration blocks other operations on production",
      "solutions": [
        {
          "approach": "Use pt-online-schema-change (MySQL)",
          "description": "Online schema change tool for zero-downtime migrations"
        },
        {
          "approach": "Implement chunked data migration",
          "example": "Process records in batches of 1000-10000"
        },
        {
          "approach": "Schedule maintenance window",
          "description": "Plan for brief downtime during low-traffic periods"
        }
      ]
    },
    "problem_3": {
      "issue": "Migration applied but application crashes",
      "cause": "Application code not compatible with new schema",
      "immediate_action": {
        "step_1": "Rollback migration immediately",
        "command": "alembic downgrade -1",
        "step_2": "Investigate application compatibility",
        "step_3": "Fix application code before reapplying"
      }
    }
  }
}
```

### Advanced Migration Patterns

```python
# Pattern 1: Chunked Data Migration for Large Tables
def upgrade() -> None:
    """Migrate large amounts of data in chunks"""
    
    connection = op.get_bind()
    batch_size = 10000
    
    # Get total count
    result = connection.execute(sa.text("SELECT COUNT(*) FROM large_table"))
    total_rows = result.scalar()
    
    print(f"Migrating {total_rows} rows in batches of {batch_size}")
    
    for offset in range(0, total_rows, batch_size):
        print(f"Processing batch: {offset} to {offset + batch_size}")
        
        connection.execute(sa.text(f"""
            UPDATE large_table 
            SET new_column = CASE 
                WHEN old_column = 'A' THEN 'Alpha'
                WHEN old_column = 'B' THEN 'Beta'
                ELSE 'Unknown'
            END
            WHERE id >= {offset} AND id < {offset + batch_size}
        """))
        
        # Commit each batch
        connection.execute(sa.text("COMMIT"))

# Pattern 2: Conditional Migration Based on Database State  
def upgrade() -> None:
    """Apply migration only if needed"""
    
    connection = op.get_bind()
    
    # Check if column already exists
    inspector = sa.inspect(connection)
    columns = [col['name'] for col in inspector.get_columns('users')]
    
    if 'new_column' not in columns:
        op.add_column('users', sa.Column('new_column', sa.String(50)))
        print("Added new_column to users table")
    else:
        print("Column new_column already exists, skipping")

# Pattern 3: Migration with External System Integration
def upgrade() -> None:
    """Migration that coordinates with external systems"""
    
    # 1. Update database schema
    op.add_column('products', sa.Column('external_id', sa.String(100)))
    
    # 2. Integrate with external system
    import requests
    
    connection = op.get_bind()
    products = connection.execute(sa.text("SELECT id, name FROM products"))
    
    for product_id, name in products:
        # Call external API to get external_id
        try:
            response = requests.post('https://external-api.com/register', 
                                   json={'name': name}, timeout=30)
            external_id = response.json().get('id')
            
            connection.execute(sa.text(
                "UPDATE products SET external_id = :ext_id WHERE id = :prod_id"
            ), {'ext_id': external_id, 'prod_id': product_id})
            
        except Exception as e:
            print(f"Failed to register product {product_id}: {e}")
            # Handle failure appropriately
```

---

## 🎯 Migration Workflow for Different Environments

### Development Environment
```bash
# Daily development workflow
alembic revision --autogenerate -m "Add user preferences"
alembic upgrade head
# Test changes thoroughly

# Reset database to clean state (development only!)
alembic downgrade base
alembic upgrade head
```

### Staging Environment  
```bash
# Before deploying to staging
alembic history
alembic current
alembic upgrade head

# Test full application functionality
# Run automated test suite
# Performance testing with production-like data
```

### Production Environment
```bash
# Production deployment checklist

# 1. Create backup
pg_dump production_db > backup_$(date +%Y%m%d_%H%M%S).sql

# 2. Check migration status
alembic current
alembic history --verbose

# 3. Apply migrations (in maintenance window if needed)
alembic upgrade head

# 4. Verify deployment
alembic current
# Run health checks
# Monitor application metrics

# 5. Rollback procedure (if issues found)
alembic downgrade <previous_revision>
# Restore from backup if necessary
```

## 🟢 **BEGINNER LEVEL: Basic Models and Operations**

### Model Design Patterns

**Think of it like:** Creating the blueprint for your data - like designing forms that people will fill out, but these forms become database tables.

#### Creating Your First Models

```python
# app/models/category.py
from sqlalchemy import Column, Integer, String, Text, Boolean
from sqlalchemy.orm import relationship
from app.db.base import BaseModel

class Category(BaseModel):
    """
    Think of this like: A filing cabinet drawer label
    Each category groups similar products together
    """
    __tablename__ = "categories"
    
    name = Column(String(100), nullable=False, unique=True, index=True)
    description = Column(Text, nullable=True)
    is_active = Column(Boolean, default=True, nullable=False)
    
    # Relationship to products (one category has many products)
    products = relationship("Product", back_populates="category")
    
    def __str__(self):
        return f"Category: {self.name}"
```

```python
# app/models/product.py
from sqlalchemy import Column, Integer, String, Text, Numeric, Boolean, ForeignKey
from sqlalchemy.orm import relationship
from app.db.base import BaseModel

class Product(BaseModel):
    """
    Think of this like: An item in your store inventory
    Each product has details like name, price, and which category it belongs to
    """
    __tablename__ = "products"
    
    # Basic product information
    name = Column(String(200), nullable=False, index=True)
    description = Column(Text, nullable=True)
    price = Column(Numeric(10, 2), nullable=False)  # 10 digits total, 2 decimal places
    stock_quantity = Column(Integer, default=0, nullable=False)
    is_active = Column(Boolean, default=True, nullable=False)
    
    # Foreign key to category (many products belong to one category)
    category_id = Column(Integer, ForeignKey("categories.id"), nullable=False)
    
    # Relationships
    category = relationship("Category", back_populates="products")
    order_items = relationship("OrderItem", back_populates="product")
    
    def __str__(self):
        return f"Product: {self.name} (${self.price})"
    
    @property
    def is_in_stock(self) -> bool:
        """Check if product is available in stock"""
        return self.stock_quantity > 0
```

```python
# app/models/user.py
from sqlalchemy import Column, Integer, String, Boolean, Date
from sqlalchemy.orm import relationship
from app.db.base import BaseModel

class User(BaseModel):
    """
    Think of this like: A customer's profile card
    Contains all the information about a person who uses your system
    """
    __tablename__ = "users"
    
    # User identification
    username = Column(String(50), unique=True, nullable=False, index=True)
    email = Column(String(100), unique=True, nullable=False, index=True)
    full_name = Column(String(100), nullable=False)
    
    # Authentication
    hashed_password = Column(String(100), nullable=False)
    is_active = Column(Boolean, default=True, nullable=False)
    is_superuser = Column(Boolean, default=False, nullable=False)
    
    # Profile information
    phone = Column(String(20), nullable=True)
    date_of_birth = Column(Date, nullable=True)
    
    # Relationships
    orders = relationship("Order", back_populates="user")
    
    def __str__(self):
        return f"User: {self.username} ({self.email})"
```

```python
# app/models/order.py
from sqlalchemy import Column, Integer, String, Numeric, DateTime, ForeignKey, Enum
from sqlalchemy.orm import relationship
import enum
from app.db.base import BaseModel

class OrderStatus(str, enum.Enum):
    """
    Think of this like: The different stages of an order
    Like tracking a package from 'ordered' to 'delivered'
    """
    PENDING = "pending"
    PROCESSING = "processing"
    SHIPPED = "shipped"
    DELIVERED = "delivered"
    CANCELLED = "cancelled"

class Order(BaseModel):
    """
    Think of this like: A shopping receipt
    Contains information about what someone bought and when
    """
    __tablename__ = "orders"
    
    # Order information
    order_number = Column(String(50), unique=True, nullable=False, index=True)
    total_amount = Column(Numeric(10, 2), nullable=False)
    status = Column(Enum(OrderStatus), default=OrderStatus.PENDING, nullable=False)
    
    # Customer information
    user_id = Column(Integer, ForeignKey("users.id"), nullable=False)
    
    # Relationships
    user = relationship("User", back_populates="orders")
    items = relationship("OrderItem", back_populates="order")
    
    def __str__(self):
        return f"Order: {self.order_number} (${self.total_amount})"

class OrderItem(BaseModel):
    """
    Think of this like: Individual items on a shopping receipt
    Each line item shows what product, how many, and the price
    """
    __tablename__ = "order_items"
    
    quantity = Column(Integer, nullable=False, default=1)
    unit_price = Column(Numeric(10, 2), nullable=False)
    
    # Foreign keys
    order_id = Column(Integer, ForeignKey("orders.id"), nullable=False)
    product_id = Column(Integer, ForeignKey("products.id"), nullable=False)
    
    # Relationships
    order = relationship("Order", back_populates="items")
    product = relationship("Product", back_populates="order_items")
    
    @property
    def line_total(self) -> float:
        """Calculate total price for this line item"""
        return float(self.quantity * self.unit_price)
    
    def __str__(self):
        return f"OrderItem: {self.quantity}x {self.product.name} @ ${self.unit_price}"
```

#### Model Registration

```python
# app/models/__init__.py
"""
Think of this like: The index of your recipe book
Lists all the data models so the system knows about them
"""

from app.db.base import BaseModel
from app.models.category import Category
from app.models.product import Product
from app.models.user import User
from app.models.order import Order, OrderItem, OrderStatus

# Export all models
__all__ = [
    "BaseModel",
    "Category", 
    "Product",
    "User",
    "Order",
    "OrderItem", 
    "OrderStatus"
]
```

### Creating Your First Migration

**Think of it like:** Writing down the recipe for your database structure so it can be recreated anywhere.

```bash
# Generate migration for your models
alembic revision --autogenerate -m "Create initial tables"

# This creates a migration file like: 001_create_initial_tables.py
```

**Migration File Output:**
```python
# alembic/versions/001_create_initial_tables.py
"""Create initial tables

Revision ID: 001
Revises: 
Create Date: 2024-01-01 10:00:00.000000

"""
from alembic import op
import sqlalchemy as sa
from sqlalchemy.dialects import postgresql

# revision identifiers
revision = '001'
down_revision = None
branch_labels = None
depends_on = None

def upgrade() -> None:
    """
    Think of this like: The recipe to build your database
    Creates all the tables and relationships
    """
    # Create categories table
    op.create_table('categories',
        sa.Column('id', sa.Integer(), nullable=False),
        sa.Column('name', sa.String(length=100), nullable=False),
        sa.Column('description', sa.Text(), nullable=True),
        sa.Column('is_active', sa.Boolean(), nullable=False),
        sa.Column('created_at', sa.DateTime(timezone=True), server_default=sa.text('now()'), nullable=False),
        sa.Column('updated_at', sa.DateTime(timezone=True), server_default=sa.text('now()'), nullable=False),
        sa.PrimaryKeyConstraint('id')
    )
    op.create_index(op.f('ix_categories_id'), 'categories', ['id'], unique=False)
    op.create_index(op.f('ix_categories_name'), 'categories', ['name'], unique=True)

    # Create products table
    op.create_table('products',
        sa.Column('id', sa.Integer(), nullable=False),
        sa.Column('name', sa.String(length=200), nullable=False),
        sa.Column('description', sa.Text(), nullable=True),
        sa.Column('price', sa.Numeric(precision=10, scale=2), nullable=False),
        sa.Column('stock_quantity', sa.Integer(), nullable=False),
        sa.Column('is_active', sa.Boolean(), nullable=False),
        sa.Column('category_id', sa.Integer(), nullable=False),
        sa.Column('created_at', sa.DateTime(timezone=True), server_default=sa.text('now()'), nullable=False),
        sa.Column('updated_at', sa.DateTime(timezone=True), server_default=sa.text('now()'), nullable=False),
        sa.ForeignKeyConstraint(['category_id'], ['categories.id'], ),
        sa.PrimaryKeyConstraint('id')
    )
    op.create_index(op.f('ix_products_id'), 'products', ['id'], unique=False)
    op.create_index(op.f('ix_products_name'), 'products', ['name'], unique=False)

    # Create users table
    op.create_table('users',
        sa.Column('id', sa.Integer(), nullable=False),
        sa.Column('username', sa.String(length=50), nullable=False),
        sa.Column('email', sa.String(length=100), nullable=False),
        sa.Column('full_name', sa.String(length=100), nullable=False),
        sa.Column('hashed_password', sa.String(length=100), nullable=False),
        sa.Column('is_active', sa.Boolean(), nullable=False),
        sa.Column('is_superuser', sa.Boolean(), nullable=False),
        sa.Column('phone', sa.String(length=20), nullable=True),
        sa.Column('date_of_birth', sa.Date(), nullable=True),
        sa.Column('created_at', sa.DateTime(timezone=True), server_default=sa.text('now()'), nullable=False),
        sa.Column('updated_at', sa.DateTime(timezone=True), server_default=sa.text('now()'), nullable=False),
        sa.PrimaryKeyConstraint('id')
    )
    op.create_index(op.f('ix_users_email'), 'users', ['email'], unique=True)
    op.create_index(op.f('ix_users_id'), 'users', ['id'], unique=False)
    op.create_index(op.f('ix_users_username'), 'users', ['username'], unique=True)

def downgrade() -> None:
    """
    Think of this like: The recipe to undo changes if something goes wrong
    Removes all the tables in reverse order
    """
    op.drop_index(op.f('ix_users_username'), table_name='users')
    op.drop_index(op.f('ix_users_id'), table_name='users')
    op.drop_index(op.f('ix_users_email'), table_name='users')
    op.drop_table('users')
    
    op.drop_index(op.f('ix_products_name'), table_name='products')
    op.drop_index(op.f('ix_products_id'), table_name='products')
    op.drop_table('products')
    
    op.drop_index(op.f('ix_categories_name'), table_name='categories')
    op.drop_index(op.f('ix_categories_id'), table_name='categories')
    op.drop_table('categories')
```

```bash
# Apply the migration to create tables
alembic upgrade head

# Output:
INFO  [alembic.runtime.migration] Context impl PostgresqlImpl.
INFO  [alembic.runtime.migration] Will assume transactional DDL.
INFO  [alembic.runtime.migration] Running upgrade -> 001, Create initial tables
```

**Database Structure Created:**
```json
{
  "database_structure": {
    "tables_created": 6,
    "tables": [
      {
        "name": "categories",
        "columns": ["id", "name", "description", "is_active", "created_at", "updated_at"],
        "indexes": ["ix_categories_id", "ix_categories_name"],
        "primary_key": "id"
      },
      {
        "name": "products", 
        "columns": ["id", "name", "description", "price", "stock_quantity", "is_active", "category_id", "created_at", "updated_at"],
        "indexes": ["ix_products_id", "ix_products_name"],
        "foreign_keys": ["category_id -> categories.id"],
        "primary_key": "id"
      },
      {
        "name": "users",
        "columns": ["id", "username", "email", "full_name", "hashed_password", "is_active", "is_superuser", "phone", "date_of_birth", "created_at", "updated_at"],
        "indexes": ["ix_users_id", "ix_users_username", "ix_users_email"],
        "unique_constraints": ["username", "email"],
        "primary_key": "id"
      }
    ],
    "migration_status": "SUCCESS",
    "current_revision": "001"
  }
}
```

### Pydantic Schemas

**Think of it like:** Pydantic schemas are like forms with validation rules. They ensure data coming in and going out of your API is clean and follows the right format.

#### Input/Output Schemas

```python
# app/schemas/category.py
from typing import Optional, List
from pydantic import BaseModel, Field
from datetime import datetime

class CategoryBase(BaseModel):
    """
    Think of this like: The basic information every category needs
    This is the foundation that other schemas build on
    """
    name: str = Field(..., min_length=1, max_length=100, description="Category name")
    description: Optional[str] = Field(None, max_length=500, description="Category description")
    is_active: bool = Field(True, description="Whether category is active")

class CategoryCreate(CategoryBase):
    """
    Think of this like: A form for creating a new category
    Contains only the fields needed when creating
    """
    pass

class CategoryUpdate(BaseModel):
    """
    Think of this like: A form for updating an existing category
    All fields are optional since you might only want to update some
    """
    name: Optional[str] = Field(None, min_length=1, max_length=100)
    description: Optional[str] = Field(None, max_length=500)
    is_active: Optional[bool] = None

class CategoryInDB(CategoryBase):
    """
    Think of this like: The complete category record as stored in database
    Includes all fields including auto-generated ones
    """
    id: int
    created_at: datetime
    updated_at: datetime
    
    class Config:
        from_attributes = True  # Allows creation from SQLAlchemy models

class Category(CategoryInDB):
    """
    Think of this like: The category data sent back to API users
    Same as CategoryInDB but can be extended with computed fields
    """
    pass
```

## Basic CRUD Operations

**Think of it like:** CRUD stands for Create, Read, Update, Delete - the four basic things you can do with data, like adding items to your shopping cart, viewing them, changing quantities, and removing items.

### CRUD Base Class

```python
# app/crud/base.py
from typing import Any, Dict, Generic, List, Optional, Type, TypeVar, Union
from fastapi.encoders import jsonable_encoder
from pydantic import BaseModel
from sqlalchemy.orm import Session
from app.db.base import BaseModel as DBBaseModel

ModelType = TypeVar("ModelType", bound=DBBaseModel)
CreateSchemaType = TypeVar("CreateSchemaType", bound=BaseModel)
UpdateSchemaType = TypeVar("UpdateSchemaType", bound=BaseModel)

class CRUDBase(Generic[ModelType, CreateSchemaType, UpdateSchemaType]):
    """
    Think of this like: A universal remote control for database operations
    Works with any model and provides standard Create, Read, Update, Delete functions
    """
    
    def __init__(self, model: Type[ModelType]):
        self.model = model
    
    def get(self, db: Session, id: Any) -> Optional[ModelType]:
        """Get a single record by ID"""
        return db.query(self.model).filter(self.model.id == id).first()
    
    def get_multi(self, db: Session, *, skip: int = 0, limit: int = 100) -> List[ModelType]:
        """Get multiple records with pagination"""
        return db.query(self.model).offset(skip).limit(limit).all()
    
    def create(self, db: Session, *, obj_in: CreateSchemaType) -> ModelType:
        """Create a new record"""
        obj_in_data = jsonable_encoder(obj_in)
        db_obj = self.model(**obj_in_data)
        db.add(db_obj)
        db.commit()
        db.refresh(db_obj)
        return db_obj
    
    def update(self, db: Session, *, db_obj: ModelType, obj_in: Union[UpdateSchemaType, Dict[str, Any]]) -> ModelType:
        """Update an existing record"""
        obj_data = jsonable_encoder(db_obj)
        if isinstance(obj_in, dict):
            update_data = obj_in
        else:
            update_data = obj_in.dict(exclude_unset=True)
            
        for field in obj_data:
            if field in update_data:
                setattr(db_obj, field, update_data[field])
                
        db.add(db_obj)
        db.commit()
        db.refresh(db_obj)
        return db_obj
    
    def remove(self, db: Session, *, id: int) -> ModelType:
        """Delete a record by ID"""
        obj = db.query(self.model).get(id)
        db.delete(obj)
        db.commit()
        return obj
```

### FastAPI Application Setup

```python
# app/main.py
from fastapi import FastAPI
from fastapi.middleware.cors import CORSMiddleware
from app.core.config import settings
from app.api.api_v1.api import api_router

def create_application() -> FastAPI:
    """
    Think of this like: Setting up your restaurant
    Configuring the dining room, menu, and service rules
    """
    
    app = FastAPI(
        title=settings.PROJECT_NAME,
        description="A comprehensive e-commerce API built with FastAPI and SQLAlchemy",
        version="1.0.0",
        openapi_url=f"{settings.API_V1_STR}/openapi.json",
        docs_url="/docs",        # Swagger UI
        redoc_url="/redoc",      # ReDoc documentation
    )

    # Set up CORS middleware
    app.add_middleware(
        CORSMiddleware,
        allow_origins=["http://localhost:3000"],  # React app URL
        allow_credentials=True,
        allow_methods=["*"],
        allow_headers=["*"],
    )

    # Include API routes
    app.include_router(api_router, prefix=settings.API_V1_STR)

    @app.get("/")
    def root():
        """Health check endpoint"""
        return {
            "message": "E-commerce API is running!",
            "version": "1.0.0",
            "docs": "/docs",
            "redoc": "/redoc"
        }

    @app.get("/health")
    def health_check():
        """Detailed health check"""
        return {
            "status": "healthy",
            "database": "connected",
            "timestamp": "2024-01-01T10:00:00Z"
        }

    return app

# Create the application
app = create_application()

if __name__ == "__main__":
    import uvicorn
    uvicorn.run("main:app", host="0.0.0.0", port=8000, reload=True)
```

**API Documentation Output:**
```json
{
  "api_documentation": {
    "swagger_ui": "http://localhost:8000/docs",
    "redoc": "http://localhost:8000/redoc",
    "openapi_schema": "http://localhost:8000/api/v1/openapi.json",
    "health_endpoints": [
      "GET / - Root health check",
      "GET /health - Detailed health status"
    ],
    "api_features": {
      "automatic_validation": true,
      "interactive_docs": true,
      "type_hints": true,
      "async_support": true,
      "dependency_injection": true
    }
  }
}
```

### Sample Data and Testing

**Sample API Requests and Responses:**

**1. Create Category:**
```bash
curl -X POST "http://localhost:8000/api/v1/categories/" \
     -H "Content-Type: application/json" \
     -d '{
       "name": "Electronics",
       "description": "Electronic devices and accessories"
     }'
```

**Response:**
```json
{
  "id": 1,
  "name": "Electronics", 
  "description": "Electronic devices and accessories",
  "is_active": true,
  "created_at": "2024-01-01T10:00:00.123456Z",
  "updated_at": "2024-01-01T10:00:00.123456Z"
}
```

**2. Create Product:**
```bash
curl -X POST "http://localhost:8000/api/v1/products/" \
     -H "Content-Type: application/json" \
     -d '{
       "name": "iPhone 15 Pro",
       "description": "Latest iPhone with Pro features",
       "price": 1199.99,
       "stock_quantity": 50,
       "category_id": 1
     }'
```

**Response:**
```json
{
  "id": 1,
  "name": "iPhone 15 Pro",
  "description": "Latest iPhone with Pro features", 
  "price": "1199.99",
  "stock_quantity": 50,
  "is_active": true,
  "category_id": 1,
  "created_at": "2024-01-01T10:05:00.123456Z",
  "updated_at": "2024-01-01T10:05:00.123456Z"
}
```

**3. Get All Products:**
```bash
curl -X GET "http://localhost:8000/api/v1/products/?skip=0&limit=10"
```

**Response:**
```json
{
  "items": [
    {
      "id": 1,
      "name": "iPhone 15 Pro",
      "description": "Latest iPhone with Pro features",
      "price": "1199.99",
      "stock_quantity": 50,
      "is_active": true,
      "category_id": 1,
      "created_at": "2024-01-01T10:05:00.123456Z",
      "updated_at": "2024-01-01T10:05:00.123456Z"
    },
    {
      "id": 2,
      "name": "MacBook Pro",
      "description": "Professional laptop for developers",
      "price": "2499.99",
      "stock_quantity": 25,
      "is_active": true,
      "category_id": 1,
      "created_at": "2024-01-01T10:10:00.123456Z",
      "updated_at": "2024-01-01T10:10:00.123456Z"
    }
  ],
  "total": 2,
  "skip": 0,
  "limit": 10
}
```

**4. Update Product:**
```bash
curl -X PUT "http://localhost:8000/api/v1/products/1" \
     -H "Content-Type: application/json" \
     -d '{
       "price": 1099.99,
       "stock_quantity": 45
     }'
```

**Response:**
```json
{
  "id": 1,
  "name": "iPhone 15 Pro", 
  "description": "Latest iPhone with Pro features",
  "price": "1099.99",
  "stock_quantity": 45,
  "is_active": true,
  "category_id": 1,
  "created_at": "2024-01-01T10:05:00.123456Z",
  "updated_at": "2024-01-01T10:15:00.789012Z"
}
```

## 🔗 Database Relationships

**Think of it like:** Database relationships are like connections between different filing cabinets in your office. Some files reference other files, creating a web of connected information.

### One-to-Many Relationships

**Think of it like:** One category can contain many products, but each product belongs to only one category - like books in a library where each section (category) contains many books (products).

```python
# app/models/relationships.py
from sqlalchemy import Column, Integer, String, ForeignKey, Numeric, Text
from sqlalchemy.orm import relationship
from app.db.base import BaseModel

class Category(BaseModel):
    """One category can have many products"""
    __tablename__ = "categories"
    
    name = Column(String(100), nullable=False)
    description = Column(Text)
    
    # One-to-Many: One category has many products
    products = relationship("Product", back_populates="category")

class Product(BaseModel):
    """Many products belong to one category"""
    __tablename__ = "products"
    
    name = Column(String(200), nullable=False)
    price = Column(Numeric(10, 2), nullable=False)
    
    # Foreign Key: Links to the category this product belongs to
    category_id = Column(Integer, ForeignKey("categories.id"), nullable=False)
    
    # Many-to-One: Many products belong to one category
    category = relationship("Category", back_populates="products")
    
    # One-to-Many: One product can have many order items
    order_items = relationship("OrderItem", back_populates="product")
```

**Working with One-to-Many Relationships:**

```python
# app/crud/relationship_examples.py
from sqlalchemy.orm import Session, joinedload, selectinload
from app.models import Category, Product

def create_category_with_products(db: Session):
    """
    Think of this like: Setting up a new store section with initial products
    """
    
    # Create category
    electronics = Category(
        name="Electronics",
        description="Electronic devices and gadgets"
    )
    db.add(electronics)
    db.flush()  # Get the ID without committing
    
    # Create products for this category
    products_data = [
        {"name": "iPhone 15 Pro", "price": 1199.99, "category_id": electronics.id},
        {"name": "MacBook Pro", "price": 2499.99, "category_id": electronics.id},
        {"name": "iPad Air", "price": 599.99, "category_id": electronics.id}
    ]
    
    products = [Product(**data) for data in products_data]
    db.add_all(products)
    db.commit()
    
    return electronics

def get_category_with_products(db: Session, category_id: int):
    """
    Think of this like: Getting a store section and seeing all products in it
    """
    
    # Method 1: Using joinedload (single query with JOIN)
    category = (
        db.query(Category)
        .options(joinedload(Category.products))
        .filter(Category.id == category_id)
        .first()
    )
    
    return category

def get_products_with_category(db: Session):
    """
    Think of this like: Getting all products and knowing which section they belong to
    """
    
    # Using selectinload for efficient loading
    products = (
        db.query(Product)
        .options(selectinload(Product.category))
        .all()
    )
    
    return products
```

**Query Results:**
```json
{
  "one_to_many_examples": {
    "category_with_products": {
      "id": 1,
      "name": "Electronics", 
      "description": "Electronic devices and gadgets",
      "products": [
        {
          "id": 1,
          "name": "iPhone 15 Pro",
          "price": "1199.99",
          "category_id": 1
        },
        {
          "id": 2, 
          "name": "MacBook Pro",
          "price": "2499.99",
          "category_id": 1
        },
        {
          "id": 3,
          "name": "iPad Air", 
          "price": "599.99",
          "category_id": 1
        }
      ],
      "total_products": 3,
      "category_value": "4299.97"
    },
    "products_with_category": [
      {
        "id": 1,
        "name": "iPhone 15 Pro",
        "price": "1199.99",
        "category": {
          "id": 1,
          "name": "Electronics"
        }
      },
      {
        "id": 2,
        "name": "MacBook Pro", 
        "price": "2499.99",
        "category": {
          "id": 1,
          "name": "Electronics"
        }
      }
    ]
  }
}
```

### Many-to-Many Relationships

**Think of it like:** A product can have multiple tags (like "bestseller", "new", "popular"), and each tag can be applied to multiple products. This creates a many-to-many relationship.

```python
# app/models/many_to_many.py
from sqlalchemy import Table, Column, Integer, ForeignKey
from sqlalchemy.orm import relationship
from app.db.base import Base, BaseModel

# Association table for many-to-many relationship
product_tags = Table(
    'product_tags',
    Base.metadata,
    Column('product_id', Integer, ForeignKey('products.id'), primary_key=True),
    Column('tag_id', Integer, ForeignKey('tags.id'), primary_key=True)
)

class Tag(BaseModel):
    """Tags that can be applied to multiple products"""
    __tablename__ = "tags"
    
    name = Column(String(50), nullable=False, unique=True)
    color = Column(String(7), default="#007bff")  # Hex color code
    
    # Many-to-Many: Many tags can be applied to many products
    products = relationship(
        "Product", 
        secondary=product_tags, 
        back_populates="tags"
    )

# Updated Product model with tags
class Product(BaseModel):
    """Products with many-to-many tag relationships"""
    __tablename__ = "products"
    
    name = Column(String(200), nullable=False)
    price = Column(Numeric(10, 2), nullable=False)
    category_id = Column(Integer, ForeignKey("categories.id"))
    
    # Relationships
    category = relationship("Category", back_populates="products")
    
    # Many-to-Many: Many products can have many tags  
    tags = relationship(
        "Tag",
        secondary=product_tags,
        back_populates="products"
    )
```

**Working with Many-to-Many Relationships:**

```python
def create_products_with_tags(db: Session):
    """
    Think of this like: Creating products and applying multiple labels to them
    """
    
    # Create tags
    tags_data = [
        {"name": "bestseller", "color": "#28a745"},
        {"name": "new", "color": "#007bff"},  
        {"name": "premium", "color": "#6f42c1"},
        {"name": "popular", "color": "#fd7e14"}
    ]
    
    tags = []
    for tag_data in tags_data:
        tag = Tag(**tag_data)
        tags.append(tag)
    
    db.add_all(tags)
    db.flush()
    
    # Create products
    iphone = Product(name="iPhone 15 Pro", price=1199.99, category_id=1)
    macbook = Product(name="MacBook Pro", price=2499.99, category_id=1)
    
    # Add tags to products (many-to-many)
    iphone.tags.extend([tags[0], tags[1], tags[3]])  # bestseller, new, popular
    macbook.tags.extend([tags[0], tags[2]])          # bestseller, premium
    
    db.add_all([iphone, macbook])
    db.commit()
    
    return [iphone, macbook]

def get_products_with_tags(db: Session):
    """
    Think of this like: Getting all products and seeing what labels are attached
    """
    
    products = (
        db.query(Product)
        .options(selectinload(Product.tags))
        .all()
    )
    
    return products

def get_products_by_tag(db: Session, tag_name: str):
    """
    Think of this like: Finding all products that have a specific label
    """
    
    products = (
        db.query(Product)
        .join(Product.tags)
        .filter(Tag.name == tag_name)
        .all()
    )
    
    return products
```

**Query Results:**
```json
{
  "many_to_many_examples": {
    "products_with_tags": [
      {
        "id": 1,
        "name": "iPhone 15 Pro",
        "price": "1199.99",
        "tags": [
          {
            "id": 1,
            "name": "bestseller",
            "color": "#28a745"
          },
          {
            "id": 2, 
            "name": "new",
            "color": "#007bff"
          },
          {
            "id": 4,
            "name": "popular", 
            "color": "#fd7e14"
          }
        ],
        "tag_count": 3
      },
      {
        "id": 2,
        "name": "MacBook Pro",
        "price": "2499.99", 
        "tags": [
          {
            "id": 1,
            "name": "bestseller",
            "color": "#28a745"
          },
          {
            "id": 3,
            "name": "premium",
            "color": "#6f42c1"
          }
        ],
        "tag_count": 2
      }
    ],
    "products_by_tag": {
      "tag": "bestseller",
      "products": [
        {
          "id": 1,
          "name": "iPhone 15 Pro",
          "price": "1199.99"
        },
        {
          "id": 2,
          "name": "MacBook Pro", 
          "price": "2499.99"
        }
      ],
      "total_bestsellers": 2
    }
  }
}
```

### Complex Migrations with Relationships

**Think of it like:** As your business grows, you need to add new tables and relationships. Alembic helps you do this systematically.

```bash
# Add tags and product_tags tables
alembic revision --autogenerate -m "Add tags and product_tags relationship"
```

**Generated Migration:**
```python
# alembic/versions/002_add_tags_relationship.py
"""Add tags and product_tags relationship

Revision ID: 002
Revises: 001
Create Date: 2024-01-01 11:00:00.000000
"""

from alembic import op
import sqlalchemy as sa

revision = '002'
down_revision = '001'
branch_labels = None
depends_on = None

def upgrade() -> None:
    """
    Think of this like: Adding a new labeling system to your store
    """
    
    # Create tags table
    op.create_table(
        'tags',
        sa.Column('id', sa.Integer(), nullable=False),
        sa.Column('name', sa.String(length=50), nullable=False),
        sa.Column('color', sa.String(length=7), nullable=True),
        sa.Column('created_at', sa.DateTime(timezone=True), server_default=sa.text('now()'), nullable=False),
        sa.Column('updated_at', sa.DateTime(timezone=True), server_default=sa.text('now()'), nullable=False),
        sa.PrimaryKeyConstraint('id'),
        sa.UniqueConstraint('name')
    )
    op.create_index(op.f('ix_tags_id'), 'tags', ['id'], unique=False)
    
    # Create product_tags association table
    op.create_table(
        'product_tags',
        sa.Column('product_id', sa.Integer(), nullable=False),
        sa.Column('tag_id', sa.Integer(), nullable=False),
        sa.ForeignKeyConstraint(['product_id'], ['products.id'], ),
        sa.ForeignKeyConstraint(['tag_id'], ['tags.id'], ),
        sa.PrimaryKeyConstraint('product_id', 'tag_id')
    )

def downgrade() -> None:
    """
    Think of this like: Removing the labeling system if something goes wrong
    """
    op.drop_table('product_tags')
    op.drop_index(op.f('ix_tags_id'), table_name='tags')
    op.drop_table('tags')
```

```bash
# Apply the migration
alembic upgrade head

# Output:
INFO  [alembic.runtime.migration] Running upgrade 001 -> 002, Add tags and product_tags relationship
```

**Migration Result:**
```json
{
  "migration_result": {
    "revision": "002",
    "description": "Add tags and product_tags relationship",
    "changes": [
      {
        "action": "CREATE_TABLE",
        "table": "tags",
        "columns": ["id", "name", "color", "created_at", "updated_at"],
        "constraints": ["PRIMARY KEY (id)", "UNIQUE (name)"]
      },
      {
        "action": "CREATE_TABLE", 
        "table": "product_tags",
        "columns": ["product_id", "tag_id"],
        "constraints": [
          "PRIMARY KEY (product_id, tag_id)",
          "FOREIGN KEY (product_id) REFERENCES products(id)",
          "FOREIGN KEY (tag_id) REFERENCES tags(id)"
        ]
      }
    ],
    "status": "SUCCESS",
    "execution_time": "0.045s"
  }
}
```

## 🔍 SQLAlchemy ORM: Basic to Advanced Queries

**Think of it like:** Learning SQLAlchemy queries is like learning to speak with your database - starting with simple sentences and building up to complex conversations.

### Sample Dataset for Examples

First, let's create a comprehensive dataset to work with:

```python
# Sample data creation
def create_sample_data(db: Session):
    """Create comprehensive sample dataset for examples"""
    
    # Create Categories
    categories = [
        Category(name="Electronics", description="Electronic devices"),
        Category(name="Books", description="Books and literature"),
        Category(name="Clothing", description="Apparel and accessories"),
        Category(name="Home & Garden", description="Home improvement items"),
        Category(name="Sports", description="Sports and fitness equipment")
    ]
    db.add_all(categories)
    db.flush()
    
    # Create Suppliers
    suppliers = [
        Supplier(name="TechCorp", email="tech@corp.com", rating=4.5),
        Supplier(name="BookWorld", email="info@bookworld.com", rating=4.8),
        Supplier(name="FashionHub", email="sales@fashion.com", rating=4.2),
        Supplier(name="HomeSupply", email="home@supply.com", rating=4.0),
        Supplier(name="SportsTech", email="sports@tech.com", rating=4.6)
    ]
    db.add_all(suppliers)
    db.flush()
    
    # Create Products with relationships
    products = [
        # Electronics
        Product(name="iPhone 15 Pro", price=1199.99, stock_quantity=50, category_id=1, supplier_id=1),
        Product(name="MacBook Pro", price=2499.99, stock_quantity=25, category_id=1, supplier_id=1),
        Product(name="Samsung Galaxy S24", price=899.99, stock_quantity=30, category_id=1, supplier_id=1),
        Product(name="iPad Air", price=599.99, stock_quantity=40, category_id=1, supplier_id=1),
        
        # Books
        Product(name="Python Programming", price=49.99, stock_quantity=100, category_id=2, supplier_id=2),
        Product(name="Data Science Handbook", price=59.99, stock_quantity=75, category_id=2, supplier_id=2),
        Product(name="Web Development Guide", price=39.99, stock_quantity=80, category_id=2, supplier_id=2),
        
        # Clothing
        Product(name="Nike T-Shirt", price=29.99, stock_quantity=200, category_id=3, supplier_id=3),
        Product(name="Levi's Jeans", price=89.99, stock_quantity=120, category_id=3, supplier_id=3),
        Product(name="Adidas Sneakers", price=129.99, stock_quantity=80, category_id=3, supplier_id=3),
        
        # Home & Garden
        Product(name="Garden Tools Set", price=79.99, stock_quantity=60, category_id=4, supplier_id=4),
        Product(name="Indoor Plant Pot", price=24.99, stock_quantity=150, category_id=4, supplier_id=4),
        
        # Sports
        Product(name="Yoga Mat", price=34.99, stock_quantity=90, category_id=5, supplier_id=5),
        Product(name="Dumbbells Set", price=149.99, stock_quantity=30, category_id=5, supplier_id=5),
        Product(name="Running Shoes", price=119.99, stock_quantity=60, category_id=5, supplier_id=5)
    ]
    db.add_all(products)
    db.commit()

# Execute this to create sample data
create_sample_data(db)
```

**Sample Dataset Overview:**
```json
{
  "sample_dataset": {
    "categories": 5,
    "suppliers": 5, 
    "products": 15,
    "breakdown": {
      "electronics": 4,
      "books": 3,
      "clothing": 3,
      "home_garden": 2,
      "sports": 3
    },
    "price_range": {
      "min": "$24.99",
      "max": "$2499.99",
      "average": "$283.32"
    },
    "total_inventory": 1205
  }
}
```

## 🔰 Basic Queries (Beginner Level)

**Think of it like:** Basic queries are like asking simple questions - "Show me all products" or "Find product with ID 1"

### 1. Simple SELECT Queries

#### Get All Records
```python
from sqlalchemy.orm import Session
from sqlalchemy import select

# Method 1: Using Query API (Classic)
def get_all_products_classic(db: Session):
    """Think of this like: Show me everything in the store"""
    products = db.query(Product).all()
    return products

# Method 2: Using SQLAlchemy 2.0 syntax (Modern)
async def get_all_products_modern(db: AsyncSession):
    """Modern async approach"""
    stmt = select(Product)
    result = await db.execute(stmt)
    products = result.scalars().all()
    return products

# SQL equivalent: SELECT * FROM products;
```

**JSON Output:**
```json
{
  "query_type": "SELECT_ALL",
  "operation": "Get all products from database",
  "sql_equivalent": "SELECT * FROM products;",
  "execution_time_ms": 45,
  "total_records": 15,
  "data": [
    {
      "id": 1,
      "name": "iPhone 15 Pro",
      "price": 1199.99,
      "stock_quantity": 50,
      "category_id": 1,
      "supplier_id": 1,
      "is_active": true,
      "created_at": "2023-11-01T10:30:00Z",
      "updated_at": "2023-11-15T14:20:00Z"
    },
    {
      "id": 2,
      "name": "MacBook Pro M3", 
      "price": 2499.99,
      "stock_quantity": 25,
      "category_id": 1,
      "supplier_id": 1,
      "is_active": true,
      "created_at": "2023-11-02T09:15:00Z",
      "updated_at": "2023-11-16T11:45:00Z"
    },
    {
      "id": 3,
      "name": "Samsung Galaxy S24",
      "price": 899.99,
      "stock_quantity": 75,
      "category_id": 1,
      "supplier_id": 2,
      "is_active": true,
      "created_at": "2023-11-03T15:20:00Z",
      "updated_at": "2023-11-17T08:30:00Z"
    }
  ],
  "metadata": {
    "query_complexity": "BASIC",
    "performance_impact": "LOW",
    "indexing_required": false,
    "best_practices": [
      "Use pagination for large datasets",
      "Consider adding LIMIT clause",
      "Use async for better performance"
    ]
  }
}
```

#### Get Single Record by ID
```python
# Method 1: Using get() - Most efficient for primary keys
def get_product_by_id(db: Session, product_id: int):
    """Think of it like: Find me the product with this exact ID"""
    product = db.query(Product).get(product_id)
    return product

# Method 2: Using filter() - More flexible
def get_product_by_id_filter(db: Session, product_id: int):
    """Alternative approach using filter"""
    product = db.query(Product).filter(Product.id == product_id).first()
    return product

# Method 3: SQLAlchemy 2.0 async
async def get_product_by_id_async(db: AsyncSession, product_id: int):
    """Modern async approach"""
    result = await db.get(Product, product_id)
    return result

# SQL equivalent: SELECT * FROM products WHERE id = ?;
```

**JSON Output:**
```json
{
  "query_type": "SELECT_BY_ID",
  "operation": "Get single product by primary key",
  "sql_equivalent": "SELECT * FROM products WHERE id = 1;",
  "execution_time_ms": 2,
  "parameters": {
    "product_id": 1
  },
  "result": {
    "found": true,
    "data": {
      "id": 1,
      "name": "iPhone 15 Pro",
      "price": 1199.99,
      "description": "Latest iPhone with titanium design and A17 Pro chip",
      "stock_quantity": 50,
      "category_id": 1,
      "supplier_id": 1,
      "is_active": true,
      "sku": "IPH15-PRO-256GB",
      "weight": 0.221,
      "dimensions": "159.9 x 76.7 x 8.25 mm",
      "created_at": "2023-11-01T10:30:00Z",
      "updated_at": "2023-11-15T14:20:00Z"
    }
  },
  "metadata": {
    "query_complexity": "BASIC",
    "performance_impact": "MINIMAL",
    "uses_primary_key": true,
    "indexing_required": false,
    "cache_recommended": true
  }
}
```

### 2. WHERE Clause Filtering

#### Basic Filtering
```python
# Single condition filtering
def get_active_products(db: Session):
    """Think of it like: Show me only the products that are available"""
    products = db.query(Product).filter(Product.is_active == True).all()
    return products

# Multiple conditions with AND
def get_expensive_electronics(db: Session):
    """Think of it like: Show me expensive electronics"""
    products = (
        db.query(Product)
        .filter(Product.price > 1000)
        .filter(Product.category_id == 1)  # Electronics category
        .all()
    )
    return products

# SQL equivalent: SELECT * FROM products WHERE price > 1000 AND category_id = 1;
```

**JSON Output:**
```json
{
  "query_type": "WHERE_FILTERING",
  "operations": {
    "active_products": {
      "description": "Filter products by active status",
      "sql_equivalent": "SELECT * FROM products WHERE is_active = true;",
      "execution_time_ms": 12,
      "total_records": 13,
      "sample_data": [
        {
          "id": 1,
          "name": "iPhone 15 Pro",
          "price": 1199.99,
          "is_active": true,
          "category": "Electronics"
        },
        {
          "id": 3,
          "name": "Samsung Galaxy S24",
          "price": 899.99,
          "is_active": true,
          "category": "Electronics"
        },
        {
          "id": 5,
          "name": "Python Programming Book",
          "price": 49.99,
          "is_active": true,
          "category": "Books"
        }
      ]
    },
    "expensive_electronics": {
      "description": "Filter by price and category",
      "sql_equivalent": "SELECT * FROM products WHERE price > 1000 AND category_id = 1;",
      "execution_time_ms": 8,
      "total_records": 2,
      "data": [
        {
          "id": 1,
          "name": "iPhone 15 Pro",
          "price": 1199.99,
          "category_name": "Electronics",
          "meets_criteria": "Price: $1199.99 > $1000"
        },
        {
          "id": 2,
          "name": "MacBook Pro M3",
          "price": 2499.99,
          "category_name": "Electronics", 
          "meets_criteria": "Price: $2499.99 > $1000"
        }
      ]
    }
  },
  "performance_metrics": {
    "filtered_vs_total": "13/15 active products",
    "selectivity": 0.87,
    "index_usage": {
      "is_active_index": "used",
      "price_index": "used",
      "category_id_index": "used"
    }
  }
}
```

#### Range and Comparison Operators
```python
from sqlalchemy import and_, or_, not_

def get_products_by_price_range(db: Session, min_price: float, max_price: float):
    """Think of it like: Show me products within my budget"""
    products = (
        db.query(Product)
        .filter(Product.price >= min_price)
        .filter(Product.price <= max_price)
        .all()
    )
    return products

def get_products_complex_filter(db: Session):
    """Think of it like: Show me cheap books OR expensive electronics"""
    products = (
        db.query(Product)
        .filter(
            or_(
                and_(Product.category_id == 2, Product.price < 50),  # Cheap books
                and_(Product.category_id == 1, Product.price > 1000)  # Expensive electronics
            )
        )
        .all()
    )
    return products

# SQL equivalent: SELECT * FROM products 
# WHERE (category_id = 2 AND price < 50) OR (category_id = 1 AND price > 1000);
```

**JSON Output:**
```json
{
  "query_type": "RANGE_AND_COMPLEX_FILTERING",
  "operations": {
    "price_range_filter": {
      "description": "Filter products within price range",
      "parameters": {
        "min_price": 100.00,
        "max_price": 500.00
      },
      "sql_equivalent": "SELECT * FROM products WHERE price >= 100 AND price <= 500;",
      "execution_time_ms": 15,
      "total_records": 6,
      "data": [
        {
          "id": 4,
          "name": "Wireless Earbuds",
          "price": 199.99,
          "category": "Electronics",
          "in_range": true
        },
        {
          "id": 6,
          "name": "Coffee Maker",
          "price": 299.99,
          "category": "Home & Kitchen",
          "in_range": true
        },
        {
          "id": 8,
          "name": "Running Shoes",
          "price": 129.99,
          "category": "Sports",
          "in_range": true
        }
      ],
      "price_statistics": {
        "lowest_in_range": 129.99,
        "highest_in_range": 299.99,
        "average_in_range": 209.99
      }
    },
    "complex_or_filter": {
      "description": "Complex OR logic with AND conditions",
      "sql_equivalent": "SELECT * FROM products WHERE (category_id = 2 AND price < 50) OR (category_id = 1 AND price > 1000);",
      "execution_time_ms": 10,
      "logic_explanation": "Show either cheap books OR expensive electronics",
      "total_records": 4,
      "data": [
        {
          "id": 7,
          "name": "Web Development Guide",
          "price": 39.99,
          "category": "Books",
          "match_reason": "Cheap book (price < $50)"
        },
        {
          "id": 9,
          "name": "Python Cookbook",
          "price": 45.99,
          "category": "Books",
          "match_reason": "Cheap book (price < $50)"
        },
        {
          "id": 1,
          "name": "iPhone 15 Pro",
          "price": 1199.99,
          "category": "Electronics",
          "match_reason": "Expensive electronics (price > $1000)"
        },
        {
          "id": 2,
          "name": "MacBook Pro M3",
          "price": 2499.99,
          "category": "Electronics",
          "match_reason": "Expensive electronics (price > $1000)"
        }
      ]
    }
  },
  "performance_analysis": {
    "complex_query_cost": "MEDIUM",
    "recommended_indexes": [
      "INDEX on (category_id, price)",
      "INDEX on (price) for range queries"
    ],
    "query_optimization_tips": [
      "Consider splitting complex OR queries",
      "Use UNION for better performance with large datasets",
      "Add covering indexes for frequently accessed columns"
    ]
  }
}
```

### 3. Ordering and Limiting Results

#### Basic Ordering
```python
from sqlalchemy import desc, asc

def get_products_ordered_by_price(db: Session, ascending: bool = True):
    """Think of it like: Sort products by price (cheapest/most expensive first)"""
    query = db.query(Product)
    
    if ascending:
        products = query.order_by(Product.price.asc()).all()
    else:
        products = query.order_by(Product.price.desc()).all()
    
    return products

def get_products_multi_column_sort(db: Session):
    """Think of it like: Sort by category first, then by price within each category"""
    products = (
        db.query(Product)
        .order_by(Product.category_id.asc(), Product.price.desc())
        .all()
    )
    return products

# SQL equivalent: SELECT * FROM products ORDER BY category_id ASC, price DESC;
```

**JSON Output:**
```json
{
  "query_type": "ORDERING_AND_SORTING",
  "operations": {
    "price_ascending": {
      "description": "Products sorted by price (lowest to highest)",
      "sql_equivalent": "SELECT * FROM products ORDER BY price ASC;",
      "execution_time_ms": 18,
      "total_records": 15,
      "data": [
        {
          "id": 12,
          "name": "Indoor Plant Pot",
          "price": 24.99,
          "category": "Home & Garden",
          "rank": 1
        },
        {
          "id": 8,
          "name": "Nike T-Shirt",
          "price": 29.99,
          "category": "Clothing",
          "rank": 2
        },
        {
          "id": 7,
          "name": "Web Development Guide",
          "price": 39.99,
          "category": "Books",
          "rank": 3
        },
        {
          "id": 9,
          "name": "Python Cookbook",
          "price": 45.99,
          "category": "Books",
          "rank": 4
        },
        {
          "id": 5,
          "name": "Python Programming Book",
          "price": 49.99,
          "category": "Books",
          "rank": 5
        }
      ],
      "price_range": {
        "cheapest": 24.99,
        "most_expensive": 2499.99
      }
    },
    "multi_column_sort": {
      "description": "Sort by category, then by price within category",
      "sql_equivalent": "SELECT * FROM products ORDER BY category_id ASC, price DESC;",
      "execution_time_ms": 22,
      "sorting_logic": "Category ascending, then price descending",
      "data_by_category": {
        "Electronics": [
          {
            "id": 2,
            "name": "MacBook Pro M3",
            "price": 2499.99,
            "category_rank": 1
          },
          {
            "id": 1,
            "name": "iPhone 15 Pro", 
            "price": 1199.99,
            "category_rank": 2
          },
          {
            "id": 3,
            "name": "Samsung Galaxy S24",
            "price": 899.99,
            "category_rank": 3
          }
        ],
        "Books": [
          {
            "id": 5,
            "name": "Python Programming Book",
            "price": 49.99,
            "category_rank": 1
          },
          {
            "id": 9,
            "name": "Python Cookbook",
            "price": 45.99,
            "category_rank": 2
          }
        ]
      }
    }
  }
}
```

#### Pagination and Limiting
```python
def get_products_paginated(db: Session, page: int = 1, per_page: int = 5):
    """Think of it like: Show me page 2 with 5 products per page"""
    offset = (page - 1) * per_page
    
    products = (
        db.query(Product)
        .offset(offset)
        .limit(per_page)
        .all()
    )
    
    total = db.query(Product).count()
    
    return {
        "products": products,
        "pagination": {
            "page": page,
            "per_page": per_page,
            "total": total,
            "pages": (total + per_page - 1) // per_page
        }
    }

def get_top_expensive_products(db: Session, limit: int = 3):
    """Think of it like: Show me the 3 most expensive products"""
    products = (
        db.query(Product)
        .order_by(Product.price.desc())
        .limit(limit)
        .all()
    )
    return products

# SQL equivalent: SELECT * FROM products ORDER BY price DESC LIMIT 3;
```

**JSON Output:**
```json
{
  "query_type": "PAGINATION_AND_LIMITING",
  "operations": {
    "paginated_results": {
      "description": "Paginated product listing",
      "sql_equivalent": "SELECT * FROM products LIMIT 5 OFFSET 5;",
      "execution_time_ms": 25,
      "current_page": 2,
      "per_page": 5,
      "data": [
        {
          "id": 6,
          "name": "Coffee Maker",
          "price": 299.99,
          "category": "Home & Kitchen"
        },
        {
          "id": 7,
          "name": "Web Development Guide", 
          "price": 39.99,
          "category": "Books"
        },
        {
          "id": 8,
          "name": "Nike T-Shirt",
          "price": 29.99,
          "category": "Clothing"
        },
        {
          "id": 9,
          "name": "Python Cookbook",
          "price": 45.99,
          "category": "Books"
        },
        {
          "id": 10,
          "name": "Yoga Mat",
          "price": 79.99,
          "category": "Sports"
        }
      ],
      "pagination": {
        "current_page": 2,
        "per_page": 5,
        "total_records": 15,
        "total_pages": 3,
        "has_previous": true,
        "has_next": true,
        "previous_page": 1,
        "next_page": 3
      }
    },
    "top_expensive": {
      "description": "Most expensive products (top 3)",
      "sql_equivalent": "SELECT * FROM products ORDER BY price DESC LIMIT 3;",
      "execution_time_ms": 12,
      "limit": 3,
      "data": [
        {
          "id": 2,
          "name": "MacBook Pro M3",
          "price": 2499.99,
          "category": "Electronics",
          "rank": 1,
          "price_difference_from_cheapest": 2475.00
        },
        {
          "id": 1,
          "name": "iPhone 15 Pro",
          "price": 1199.99,
          "category": "Electronics", 
          "rank": 2,
          "price_difference_from_cheapest": 1175.00
        },
        {
          "id": 3,
          "name": "Samsung Galaxy S24",
          "price": 899.99,
          "category": "Electronics",
          "rank": 3,
          "price_difference_from_cheapest": 875.00
        }
      ],
      "summary": {
        "total_value_top_3": 4599.97,
        "average_price_top_3": 1533.32,
        "category_distribution": {
          "Electronics": 3,
          "Others": 0
        }
      }
    }
  },
  "pagination_best_practices": {
    "performance_tips": [
      "Use cursor-based pagination for large datasets",
      "Always include ORDER BY with pagination",
      "Consider using database-specific pagination features"
    ],
    "ux_recommendations": [
      "Show total count when possible",
      "Implement jump-to-page functionality",
      "Cache page counts for better performance"
    ]
  }
}
```

### 2. Filter Queries with WHERE

```python
# Filter by single condition
def get_products_by_category(db: Session, category_id: int):
    """Think of this like: Show me only electronics"""
    products = db.query(Product).filter(Product.category_id == category_id).all()
    return products

# SQL equivalent: SELECT * FROM products WHERE category_id = 1;

# Filter with multiple conditions
def get_expensive_electronics(db: Session):
    """Think of this like: Show me expensive electronics"""
    products = db.query(Product).filter(
        Product.category_id == 1,  # Electronics
        Product.price > 500        # Expensive
    ).all()
    return products

# SQL equivalent: SELECT * FROM products WHERE category_id = 1 AND price > 500;
```

**Output:**
```json
{
  "electronics_products": [
    {
      "id": 1,
      "name": "iPhone 15 Pro",
      "price": "1199.99",
      "category_id": 1
    },
    {
      "id": 2,
      "name": "MacBook Pro",
      "price": "2499.99", 
      "category_id": 1
    },
    {
      "id": 3,
      "name": "Samsung Galaxy S24",
      "price": "899.99",
      "category_id": 1
    },
    {
      "id": 4,
      "name": "iPad Air",
      "price": "599.99",
      "category_id": 1
    }
  ],
  "expensive_electronics": [
    {
      "id": 1,
      "name": "iPhone 15 Pro",
      "price": "1199.99"
    },
    {
      "id": 2,
      "name": "MacBook Pro",
      "price": "2499.99"
    },
    {
      "id": 3,
      "name": "Samsung Galaxy S24", 
      "price": "899.99"
    },
    {
      "id": 4,
      "name": "iPad Air",
      "price": "599.99"
    }
  ]
}
```

### 3. Ordering and Limiting

```python
# Order by price (ascending)
def get_cheapest_products(db: Session, limit: int = 5):
    """Think of this like: Show me the 5 cheapest items"""
    products = db.query(Product).order_by(Product.price).limit(limit).all()
    return products

# Order by price (descending) 
def get_most_expensive_products(db: Session, limit: int = 5):
    """Think of this like: Show me the 5 most expensive items"""
    products = db.query(Product).order_by(Product.price.desc()).limit(limit).all()
    return products

# Order by multiple fields
def get_products_by_category_and_price(db: Session):
    """Think of this like: Group by category, then by price within each category"""
    products = db.query(Product).order_by(Product.category_id, Product.price.desc()).all()
    return products
```

**Output:**
```json
{
  "cheapest_products": [
    {
      "rank": 1,
      "name": "Indoor Plant Pot",
      "price": "24.99"
    },
    {
      "rank": 2,
      "name": "Nike T-Shirt", 
      "price": "29.99"
    },
    {
      "rank": 3,
      "name": "Yoga Mat",
      "price": "34.99"
    },
    {
      "rank": 4,
      "name": "Web Development Guide",
      "price": "39.99"
    },
    {
      "rank": 5,
      "name": "Python Programming",
      "price": "49.99"
    }
  ],
  "most_expensive_products": [
    {
      "rank": 1,
      "name": "MacBook Pro",
      "price": "2499.99"
    },
    {
      "rank": 2,
      "name": "iPhone 15 Pro",
      "price": "1199.99"
    },
    {
      "rank": 3,
      "name": "Samsung Galaxy S24",
      "price": "899.99"
    },
    {
      "rank": 4,
      "name": "iPad Air",
      "price": "599.99"
    },
    {
      "rank": 5,
      "name": "Dumbbells Set",
      "price": "149.99"
    }
  ]
}
```

## 🟡 Intermediate Queries (Growing Skills)

**Think of it like:** Now we're learning to ask more specific questions with conditions, ranges, and patterns.

### 4. Advanced Filtering with Operators

```python
# LIKE operator for text search
def search_products_by_name(db: Session, search_term: str):
    """Think of this like: Find products with 'Pro' in the name"""
    products = db.query(Product).filter(Product.name.like(f"%{search_term}%")).all()
    return products

# Case-insensitive search
def search_products_ilike(db: Session, search_term: str):
    """Think of this like: Find products regardless of case"""
    products = db.query(Product).filter(Product.name.ilike(f"%{search_term}%")).all()
    return products

# IN operator for multiple values
def get_products_by_multiple_categories(db: Session, category_ids: list):
    """Think of this like: Show me products from categories 1, 2, and 3"""
    products = db.query(Product).filter(Product.category_id.in_(category_ids)).all()
    return products

# BETWEEN operator for ranges
def get_products_in_price_range(db: Session, min_price: float, max_price: float):
    """Think of this like: Show me products between $50 and $200"""
    products = db.query(Product).filter(Product.price.between(min_price, max_price)).all()
    return products

# NOT NULL check
def get_products_with_description(db: Session):
    """Think of this like: Show me products that have descriptions"""
    products = db.query(Product).filter(Product.description.isnot(None)).all()
    return products
```

**Output Examples:**
```json
{
  "search_examples": {
    "products_with_pro": [
      {
        "id": 1,
        "name": "iPhone 15 Pro",
        "price": "1199.99"
      },
      {
        "id": 2,
        "name": "MacBook Pro",
        "price": "2499.99"
      }
    ],
    "case_insensitive_search": [
      {
        "search_term": "BOOK",
        "results": [
          {"name": "Python Programming"},
          {"name": "Data Science Handbook"}, 
          {"name": "Web Development Guide"}
        ]
      }
    ],
    "multiple_categories": {
      "category_ids": [1, 2],
      "results_count": 7,
      "categories": ["Electronics", "Books"]
    },
    "price_range_50_200": [
      {
        "name": "Data Science Handbook",
        "price": "59.99"
      },
      {
        "name": "Levi's Jeans", 
        "price": "89.99"
      },
      {
        "name": "Adidas Sneakers",
        "price": "129.99"
      },
      {
        "name": "Dumbbells Set",
        "price": "149.99"
      },
      {
        "name": "Running Shoes",
        "price": "119.99"
      }
    ]
  }
}
```

### 5. Logical Operators (AND, OR, NOT)

```python
from sqlalchemy import and_, or_, not_

# AND operator
def get_expensive_electronics_in_stock(db: Session):
    """Think of this like: Show me expensive electronics that are available"""
    products = db.query(Product).filter(
        and_(
            Product.category_id == 1,    # Electronics
            Product.price > 500,         # Expensive
            Product.stock_quantity > 0   # In stock
        )
    ).all()
    return products

# OR operator
def get_cheap_or_books(db: Session):
    """Think of this like: Show me either cheap items OR books"""
    products = db.query(Product).filter(
        or_(
            Product.price < 50,          # Cheap items
            Product.category_id == 2     # Books
        )
    ).all()
    return products

# NOT operator
def get_non_electronics(db: Session):
    """Think of this like: Show me everything except electronics"""
    products = db.query(Product).filter(
        not_(Product.category_id == 1)
    ).all()
    return products

# Complex combinations
def get_complex_filter(db: Session):
    """Think of this like: (Cheap books) OR (expensive electronics in stock)"""
    products = db.query(Product).filter(
        or_(
            and_(Product.category_id == 2, Product.price < 50),  # Cheap books
            and_(                                                # OR
                Product.category_id == 1,                       # Expensive electronics
                Product.price > 500,                            # that are
                Product.stock_quantity > 10                     # well-stocked
            )
        )
    ).all()
    return products
```

**Output:**
```json
{
  "logical_operators": {
    "expensive_electronics_in_stock": [
      {
        "id": 1,
        "name": "iPhone 15 Pro",
        "price": "1199.99",
        "stock_quantity": 50,
        "category": "Electronics"
      },
      {
        "id": 2,
        "name": "MacBook Pro",
        "price": "2499.99",
        "stock_quantity": 25,
        "category": "Electronics"
      },
      {
        "id": 3,
        "name": "Samsung Galaxy S24",
        "price": "899.99",
        "stock_quantity": 30,
        "category": "Electronics"
      },
      {
        "id": 4,
        "name": "iPad Air",
        "price": "599.99",
        "stock_quantity": 40,
        "category": "Electronics"
      }
    ],
    "cheap_or_books": [
      {
        "id": 5,
        "name": "Python Programming",
        "price": "49.99",
        "category": "Books",
        "reason": "Book category"
      },
      {
        "id": 8,
        "name": "Nike T-Shirt", 
        "price": "29.99",
        "category": "Clothing",
        "reason": "Price < $50"
      },
      {
        "id": 12,
        "name": "Indoor Plant Pot",
        "price": "24.99",
        "category": "Home & Garden",
        "reason": "Price < $50"
      }
    ],
    "complex_filter": [
      {
        "id": 7,
        "name": "Web Development Guide",
        "price": "39.99",
        "category": "Books",
        "matched_condition": "Cheap books"
      },
      {
        "id": 1,
        "name": "iPhone 15 Pro", 
        "price": "1199.99",
        "stock_quantity": 50,
        "matched_condition": "Expensive electronics in stock"
      }
    ]
  }
}
```

## 🔗 Advanced Queries: JOINS (Most Important!)

**Think of it like:** JOINs are like connecting different filing cabinets to get complete information - like getting a product's name AND its category name AND supplier details all in one query.

### 4. INNER JOIN - Getting Related Data

**Think of it like:** INNER JOIN is like finding people who BOTH have a library card AND have checked out books - you only get results where both conditions exist.

#### Single Table INNER JOIN
```python
from sqlalchemy.orm import Session, selectinload, joinedload
from sqlalchemy import select

# Method 1: Classic ORM approach
def get_products_with_categories_classic(db: Session):
    """Show me products WITH their category names (only products that have categories)"""
    results = (
        db.query(Product)
        .join(Category)  # INNER JOIN by default
        .add_columns(
            Category.name.label('category_name'),
            Category.description.label('category_description')
        )
        .all()
    )
    return results

# Method 2: SQLAlchemy 2.0 approach
async def get_products_with_categories_modern(db: AsyncSession):
    """Modern async approach with explicit INNER JOIN"""
    stmt = (
        select(Product, Category.name.label('category_name'))
        .join(Category)
        .where(Product.is_active == True)
    )
    result = await db.execute(stmt)
    return result.all()

# Method 3: Using relationships with eager loading
def get_products_with_categories_eager(db: Session):
    """Using SQLAlchemy relationships with eager loading"""
    products = (
        db.query(Product)
        .options(joinedload(Product.category))
        .filter(Product.is_active == True)
        .all()
    )
    return products

# SQL equivalent: 
# SELECT p.*, c.name as category_name, c.description as category_description 
# FROM products p INNER JOIN categories c ON p.category_id = c.id 
# WHERE p.is_active = true;
```

**JSON Output:**
```json
{
  "query_type": "INNER_JOIN_SINGLE_TABLE",
  "description": "Join products with their categories (only products with valid categories)",
  "sql_equivalent": "SELECT p.*, c.name, c.description FROM products p INNER JOIN categories c ON p.category_id = c.id;",
  "execution_time_ms": 25,
  "join_type": "INNER",
  "tables_joined": ["products", "categories"],
  "total_records": 13,
  "filtered_out": 2,
  "data": [
    {
      "product_id": 1,
      "product_name": "iPhone 15 Pro",
      "price": 1199.99,
      "stock_quantity": 50,
      "category_id": 1,
      "category_name": "Electronics",
      "category_description": "Electronic devices and gadgets",
      "joined_successfully": true
    },
    {
      "product_id": 2,
      "product_name": "MacBook Pro M3",
      "price": 2499.99,
      "stock_quantity": 25,
      "category_id": 1,
      "category_name": "Electronics",
      "category_description": "Electronic devices and gadgets",
      "joined_successfully": true
    },
    {
      "product_id": 5,
      "product_name": "Python Programming Book",
      "price": 49.99,
      "stock_quantity": 100,
      "category_id": 2,
      "category_name": "Books",
      "category_description": "Educational and reference books",
      "joined_successfully": true
    },
    {
      "product_id": 7,
      "product_name": "Web Development Guide",
      "price": 39.99,
      "stock_quantity": 80,
      "category_id": 2,
      "category_name": "Books",
      "category_description": "Educational and reference books",
      "joined_successfully": true
    }
  ],
  "category_distribution": {
    "Electronics": 4,
    "Books": 3,
    "Home & Kitchen": 2,
    "Sports": 2,
    "Clothing": 1,
    "Home & Garden": 1
  },
  "performance_metrics": {
    "join_efficiency": "HIGH",
    "index_usage": {
      "products.category_id": "used",
      "categories.id": "used (primary key)"
    },
    "memory_usage": "LOW"
  }
}
```

#### Multiple Table INNER JOIN
```python
def get_products_complete_details(db: Session):
    """Get product with category AND supplier information (triple join)"""
    results = (
        db.query(Product)
        .join(Category)
        .join(Supplier)
        .add_columns(
            Category.name.label('category_name'),
            Category.description.label('category_description'),
            Supplier.name.label('supplier_name'),
            Supplier.contact_email.label('supplier_email'),
            Supplier.rating.label('supplier_rating')
        )
        .filter(Product.is_active == True)
        .order_by(Product.price.desc())
        .all()
    )
    return results

def get_products_with_order_history(db: Session):
    """Complex join: Products with their categories, suppliers, and order counts"""
    from sqlalchemy import func
    
    results = (
        db.query(Product)
        .join(Category)
        .join(Supplier)
        .outerjoin(OrderItem)  # LEFT JOIN for order items
        .add_columns(
            Category.name.label('category_name'),
            Supplier.name.label('supplier_name'),
            func.count(OrderItem.id).label('total_orders'),
            func.coalesce(func.sum(OrderItem.quantity), 0).label('total_sold')
        )
        .group_by(Product.id, Category.name, Supplier.name)
        .having(func.count(OrderItem.id) > 0)  # Only products with orders
        .order_by(func.sum(OrderItem.quantity).desc())
        .all()
    )
    return results

# SQL equivalent:
# SELECT p.*, c.name, s.name, COUNT(oi.id), COALESCE(SUM(oi.quantity), 0)
# FROM products p 
# INNER JOIN categories c ON p.category_id = c.id
# INNER JOIN suppliers s ON p.supplier_id = s.id
# LEFT JOIN order_items oi ON p.id = oi.product_id
# GROUP BY p.id, c.name, s.name
# HAVING COUNT(oi.id) > 0
# ORDER BY SUM(oi.quantity) DESC;
```

**JSON Output:**
```json
{
  "query_type": "MULTIPLE_INNER_JOINS",
  "description": "Complex joins with products, categories, suppliers, and order history",
  "sql_equivalent": "SELECT p.*, c.name, s.name FROM products p INNER JOIN categories c ON p.category_id = c.id INNER JOIN suppliers s ON p.supplier_id = s.id;",
  "execution_time_ms": 45,
  "joins_performed": [
    {
      "type": "INNER JOIN",
      "tables": ["products", "categories"],
      "condition": "products.category_id = categories.id"
    },
    {
      "type": "INNER JOIN", 
      "tables": ["products", "suppliers"],
      "condition": "products.supplier_id = suppliers.id"
    },
    {
      "type": "LEFT JOIN",
      "tables": ["products", "order_items"],
      "condition": "products.id = order_items.product_id"
    }
  ],
  "total_records": 8,
  "complete_details": [
    {
      "product_id": 1,
      "product_name": "iPhone 15 Pro",
      "price": 1199.99,
      "category_name": "Electronics",
      "category_description": "Electronic devices and gadgets",
      "supplier_name": "TechCorp",
      "supplier_email": "orders@techcorp.com",
      "supplier_rating": 4.8,
      "supplier_country": "USA",
      "total_orders": 25,
      "total_sold": 125,
      "revenue_generated": 149999.75
    },
    {
      "product_id": 2,
      "product_name": "MacBook Pro M3",
      "price": 2499.99,
      "category_name": "Electronics",
      "category_description": "Electronic devices and gadgets", 
      "supplier_name": "TechCorp",
      "supplier_email": "orders@techcorp.com",
      "supplier_rating": 4.8,
      "supplier_country": "USA",
      "total_orders": 15,
      "total_sold": 45,
      "revenue_generated": 112499.55
    },
    {
      "product_id": 5,
      "product_name": "Python Programming Book",
      "price": 49.99,
      "category_name": "Books",
      "category_description": "Educational and reference books",
      "supplier_name": "BookWorld",
      "supplier_email": "supply@bookworld.com",
      "supplier_rating": 4.2,
      "supplier_country": "UK",
      "total_orders": 45,
      "total_sold": 180,
      "revenue_generated": 8998.20
    }
  ],
  "business_insights": {
    "top_selling_category": "Electronics",
    "most_reliable_supplier": "TechCorp",
    "highest_revenue_product": "iPhone 15 Pro",
    "supplier_performance": {
      "TechCorp": {
        "products": 4,
        "avg_rating": 4.8,
        "total_revenue": 262499.30
      },
      "BookWorld": {
        "products": 3,
        "avg_rating": 4.2,
        "total_revenue": 8998.20
      }
    }
  }
}
```

### 5. LEFT JOIN (LEFT OUTER JOIN) - Include All Records

**Think of it like:** LEFT JOIN is like getting a list of all students (left table) and their grades (right table) - you get ALL students, even those who haven't taken any tests yet.

```python
def get_all_products_with_optional_categories(db: Session):
    """Get ALL products, even those without assigned categories"""
    results = (
        db.query(Product)
        .outerjoin(Category)  # LEFT JOIN
        .add_columns(
            Category.name.label('category_name')
        )
        .all()
    )
    return results

def get_categories_with_product_counts(db: Session):
    """Get ALL categories with their product counts (including categories with 0 products)"""
    from sqlalchemy import func
    
    results = (
        db.query(Category)
        .outerjoin(Product)
        .add_columns(
            func.count(Product.id).label('product_count'),
            func.coalesce(func.avg(Product.price), 0).label('avg_price'),
            func.coalesce(func.sum(Product.stock_quantity), 0).label('total_stock')
        )
        .group_by(Category.id)
        .order_by(func.count(Product.id).desc())
        .all()
    )
    return results

def get_suppliers_with_product_performance(db: Session):
    """Comprehensive supplier analysis including inactive suppliers"""
    results = (
        db.query(Supplier)
        .outerjoin(Product)
        .outerjoin(OrderItem)
        .add_columns(
            func.count(Product.id.distinct()).label('total_products'),
            func.count(OrderItem.id).label('total_orders'),
            func.coalesce(func.sum(OrderItem.quantity * OrderItem.unit_price), 0).label('total_revenue'),
            func.coalesce(func.avg(Product.price), 0).label('avg_product_price')
        )
        .group_by(Supplier.id)
        .all()
    )
    return results

# SQL equivalent:
# SELECT s.*, COUNT(DISTINCT p.id), COUNT(oi.id), COALESCE(SUM(oi.quantity * oi.unit_price), 0)
# FROM suppliers s
# LEFT JOIN products p ON s.id = p.supplier_id  
# LEFT JOIN order_items oi ON p.id = oi.product_id
# GROUP BY s.id;
```

**JSON Output:**
```json
{
  "query_type": "LEFT_OUTER_JOIN",
  "description": "Get all records from left table, matching records from right table",
  "sql_equivalent": "SELECT p.*, c.name FROM products p LEFT JOIN categories c ON p.category_id = c.id;",
  "execution_time_ms": 35,
  "total_records": 15,
  "operations": {
    "all_products_with_categories": {
      "description": "All products including those without categories",
      "records_with_match": 13,
      "records_without_match": 2,
      "data": [
        {
          "product_id": 1,
          "product_name": "iPhone 15 Pro",
          "price": 1199.99,
          "category_name": "Electronics",
          "has_category": true
        },
        {
          "product_id": 14,
          "product_name": "Mystery Item",
          "price": 99.99,
          "category_name": null,
          "has_category": false,
          "reason": "Category not assigned yet"
        },
        {
          "product_id": 15,
          "product_name": "Discontinued Product",
          "price": 0.00,
          "category_name": null,
          "has_category": false,
          "reason": "Category removed from system"
        }
      ]
    },
    "categories_with_product_counts": {
      "description": "All categories including empty ones",
      "data": [
        {
          "category_id": 1,
          "category_name": "Electronics",
          "product_count": 4,
          "avg_price": 1024.99,
          "total_stock": 145,
          "category_status": "Active"
        },
        {
          "category_id": 2,
          "category_name": "Books",
          "product_count": 3,
          "avg_price": 45.32,
          "total_stock": 225,
          "category_status": "Active"
        },
        {
          "category_id": 7,
          "category_name": "Automotive",
          "product_count": 0,
          "avg_price": 0.00,
          "total_stock": 0,
          "category_status": "Empty - No products assigned"
        },
        {
          "category_id": 8,
          "category_name": "Jewelry",
          "product_count": 0,
          "avg_price": 0.00,
          "total_stock": 0,
          "category_status": "Empty - Recently created"
        }
      ]
    },
    "supplier_performance_analysis": {
      "description": "All suppliers including those with no products",
      "data": [
        {
          "supplier_id": 1,
          "supplier_name": "TechCorp",
          "total_products": 4,
          "total_orders": 89,
          "total_revenue": 445678.99,
          "avg_product_price": 1312.49,
          "performance_status": "Top Performer"
        },
        {
          "supplier_id": 3,
          "supplier_name": "NewSupplier Inc",
          "total_products": 0,
          "total_orders": 0,
          "total_revenue": 0.00,
          "avg_product_price": 0.00,
          "performance_status": "No Activity - Recently Added"
        },
        {
          "supplier_id": 4,
          "supplier_name": "InactiveSupplier",
          "total_products": 2,
          "total_orders": 0,
          "total_revenue": 0.00,
          "avg_product_price": 149.99,
          "performance_status": "Products Available But No Sales"
        }
      ]
    }
  },
  "left_join_benefits": [
    "Shows complete picture including missing relationships",
    "Useful for finding orphaned records",
    "Essential for reporting with optional data",
    "Helps identify data quality issues"
  ]
}
```

### 6. RIGHT JOIN - Include All Right Table Records

**Think of it like:** RIGHT JOIN is like LEFT JOIN but flipped - you get ALL records from the right table and matching ones from the left.

```python
def get_all_categories_with_products_right_join(db: Session):
    """Get ALL categories (right table) with their products (left table)"""
    # Note: SQLAlchemy doesn't have explicit RIGHT JOIN, but we can simulate it
    # by switching the order and using LEFT JOIN
    
    results = (
        db.query(Category)
        .outerjoin(Product)  # This becomes RIGHT JOIN if we think of Product as left
        .add_columns(
            func.count(Product.id).label('product_count'),
            func.group_concat(Product.name).label('product_names')
        )
        .group_by(Category.id)
        .all()
    )
    return results

# Alternative: Use explicit SQL for true RIGHT JOIN
def get_right_join_with_raw_sql(db: Session):
    """Using raw SQL for explicit RIGHT JOIN"""
    sql = """
    SELECT c.*, p.name as product_name, p.price
    FROM products p 
    RIGHT JOIN categories c ON p.category_id = c.id
    ORDER BY c.name, p.price DESC
    """
    result = db.execute(text(sql))
    return result.fetchall()

# SQL equivalent:
# SELECT c.*, p.name, p.price 
# FROM products p 
# RIGHT JOIN categories c ON p.category_id = c.id;
```

**JSON Output:**
```json
{
  "query_type": "RIGHT_OUTER_JOIN",
  "description": "All categories (right table) with matching products (left table)",
  "sql_equivalent": "SELECT c.*, p.name FROM products p RIGHT JOIN categories c ON p.category_id = c.id;",
  "execution_time_ms": 28,
  "note": "SQLAlchemy uses LEFT JOIN syntax but achieves RIGHT JOIN by table order",
  "data": [
    {
      "category_id": 1,
      "category_name": "Electronics",
      "category_description": "Electronic devices and gadgets",
      "product_count": 4,
      "sample_products": [
        {"name": "MacBook Pro M3", "price": 2499.99},
        {"name": "iPhone 15 Pro", "price": 1199.99},
        {"name": "Samsung Galaxy S24", "price": 899.99},
        {"name": "Wireless Earbuds", "price": 199.99}
      ],
      "category_revenue": 4699.96
    },
    {
      "category_id": 2,
      "category_name": "Books",
      "category_description": "Educational and reference books",
      "product_count": 3,
      "sample_products": [
        {"name": "Python Programming Book", "price": 49.99},
        {"name": "Python Cookbook", "price": 45.99},
        {"name": "Web Development Guide", "price": 39.99}
      ],
      "category_revenue": 135.97
    },
    {
      "category_id": 7,
      "category_name": "Automotive",
      "category_description": "Car parts and accessories",
      "product_count": 0,
      "sample_products": [],
      "category_revenue": 0.00,
      "status": "No products in this category"
    },
    {
      "category_id": 8,
      "category_name": "Jewelry",
      "category_description": "Fashion jewelry and accessories",
      "product_count": 0,
      "sample_products": [],
      "category_revenue": 0.00,
      "status": "Newly created category"
    }
  ],
  "right_join_insights": {
    "total_categories": 8,
    "categories_with_products": 5,
    "empty_categories": 3,
    "most_populated_category": "Electronics",
    "categories_needing_products": ["Automotive", "Jewelry", "Pet Supplies"]
  }
}
```

### 7. FULL OUTER JOIN - Include All Records from Both Tables

**Think of it like:** FULL OUTER JOIN is like combining two incomplete lists - you want EVERYTHING from both lists, even if some items don't match.

```python
from sqlalchemy import union_all

def get_full_outer_join_products_categories(db: Session):
    """
    SQLAlchemy doesn't have direct FULL OUTER JOIN, but we can simulate it
    using UNION of LEFT JOIN and RIGHT JOIN
    """
    
    # Left join: All products with their categories
    left_join = (
        db.query(
            Product.id.label('product_id'),
            Product.name.label('product_name'),
            Category.id.label('category_id'),
            Category.name.label('category_name')
        )
        .outerjoin(Category)
    )
    
    # Right join simulation: All categories with their products
    right_join = (
        db.query(
            Product.id.label('product_id'),
            Product.name.label('product_name'),
            Category.id.label('category_id'),
            Category.name.label('category_name')
        )
        .outerjoin(Product, Category.id == Product.category_id)
        .filter(Product.id.is_(None))  # Only categories without products
    )
    
    # Combine both using UNION
    full_outer = left_join.union(right_join).all()
    return full_outer

# Alternative: Using raw SQL for true FULL OUTER JOIN
def get_full_outer_join_raw_sql(db: Session):
    """Using raw SQL for explicit FULL OUTER JOIN"""
    sql = """
    SELECT 
        COALESCE(p.id, -1) as product_id,
        COALESCE(p.name, 'No Product') as product_name,
        COALESCE(c.id, -1) as category_id,
        COALESCE(c.name, 'No Category') as category_name,
        CASE 
            WHEN p.id IS NULL THEN 'Category without products'
            WHEN c.id IS NULL THEN 'Product without category'
            ELSE 'Matched'
        END as join_status
    FROM products p 
    FULL OUTER JOIN categories c ON p.category_id = c.id
    ORDER BY join_status, c.name, p.name
    """
    result = db.execute(text(sql))
    return result.fetchall()

# SQL equivalent:
# SELECT p.*, c.* 
# FROM products p 
# FULL OUTER JOIN categories c ON p.category_id = c.id;
```

**JSON Output:**
```json
{
  "query_type": "FULL_OUTER_JOIN",
  "description": "All records from both tables, whether they match or not",
  "sql_equivalent": "SELECT p.*, c.* FROM products p FULL OUTER JOIN categories c ON p.category_id = c.id;",
  "execution_time_ms": 42,
  "implementation_note": "Using UNION of LEFT and RIGHT JOINs in SQLAlchemy",
  "total_records": 18,
  "data_categories": {
    "matched_records": {
      "count": 13,
      "description": "Products with valid categories",
      "sample_data": [
        {
          "product_id": 1,
          "product_name": "iPhone 15 Pro",
          "category_id": 1,
          "category_name": "Electronics",
          "join_status": "Matched"
        },
        {
          "product_id": 2,
          "product_name": "MacBook Pro M3",
          "category_id": 1,
          "category_name": "Electronics",
          "join_status": "Matched"
        }
      ]
    },
    "products_without_categories": {
      "count": 2,
      "description": "Products that need category assignment",
      "data": [
        {
          "product_id": 14,
          "product_name": "Mystery Item",
          "category_id": null,
          "category_name": null,
          "join_status": "Product without category",
          "action_needed": "Assign category"
        },
        {
          "product_id": 15,
          "product_name": "Discontinued Product",
          "category_id": null,
          "category_name": null,
          "join_status": "Product without category",
          "action_needed": "Update or remove product"
        }
      ]
    },
    "categories_without_products": {
      "count": 3,
      "description": "Empty categories that need products",
      "data": [
        {
          "product_id": null,
          "product_name": null,
          "category_id": 7,
          "category_name": "Automotive",
          "join_status": "Category without products",
          "action_needed": "Add products or consider removal"
        },
        {
          "product_id": null,
          "product_name": null,
          "category_id": 8,
          "category_name": "Jewelry",
          "join_status": "Category without products",
          "action_needed": "Add products to new category"
        },
        {
          "product_id": null,
          "product_name": null,
          "category_id": 9,
          "category_name": "Pet Supplies",
          "join_status": "Category without products",
          "action_needed": "Stock this popular category"
        }
      ]
    }
  },
  "data_quality_insights": {
    "completeness_score": 0.72,
    "orphaned_products": 2,
    "empty_categories": 3,
    "well_matched_records": 13,
    "recommendations": [
      "Assign categories to orphaned products",
      "Add products to empty categories or remove unused categories",
      "Implement data validation to prevent orphaned records"
    ]
  },
  "business_impact": {
    "inventory_issues": "2 products without proper categorization",
    "catalog_gaps": "3 categories ready for expansion",
    "data_integrity": "72% of records properly matched"
  }
}
```

---

## 🧮 Advanced Aggregation and Analytics

**Think of it like:** Aggregation is like having a smart calculator that can analyze your entire inventory and give you business insights - like "What's my total revenue?" or "Which category makes the most money?"

### 8. Basic Aggregation Functions

```python
from sqlalchemy import func, case, cast, Integer, Float
from datetime import datetime, timedelta

def get_comprehensive_product_statistics(db: Session):
    """Get complete statistical analysis of products"""
    stats = db.query(
        func.count(Product.id).label('total_products'),
        func.count(Product.id.distinct()).label('unique_products'),
        func.avg(Product.price).label('avg_price'),
        func.min(Product.price).label('min_price'),
        func.max(Product.price).label('max_price'),
        func.sum(Product.stock_quantity).label('total_inventory'),
        func.stddev(Product.price).label('price_std_dev'),
        func.percentile_cont(0.5).within_group(Product.price).label('median_price')
    ).first()
    return stats

def get_category_performance_analysis(db: Session):
    """Advanced category analysis with business metrics"""
    results = (
        db.query(
            Category.name.label('category_name'),
            func.count(Product.id).label('product_count'),
            func.avg(Product.price).label('avg_price'),
            func.min(Product.price).label('min_price'),
            func.max(Product.price).label('max_price'),
            func.sum(Product.stock_quantity).label('total_stock'),
            func.sum(Product.price * Product.stock_quantity).label('inventory_value'),
            # Price ranges analysis
            func.count(
                case((Product.price < 50, 1))
            ).label('budget_items'),
            func.count(
                case((Product.price.between(50, 200), 1))
            ).label('mid_range_items'),
            func.count(
                case((Product.price > 200, 1))
            ).label('premium_items')
        )
        .join(Product)
        .group_by(Category.id, Category.name)
        .having(func.count(Product.id) > 0)
        .order_by(func.sum(Product.price * Product.stock_quantity).desc())
        .all()
    )
    return results

def get_supplier_performance_metrics(db: Session):
    """Comprehensive supplier analysis with profitability metrics"""
    results = (
        db.query(
            Supplier.name.label('supplier_name'),
            Supplier.rating.label('supplier_rating'),
            func.count(Product.id).label('products_supplied'),
            func.avg(Product.price).label('avg_product_price'),
            func.sum(Product.stock_quantity).label('total_stock_supplied'),
            func.sum(Product.price * Product.stock_quantity).label('total_inventory_value'),
            # Performance indicators
            func.count(
                case((Product.stock_quantity > 0, 1))
            ).label('products_in_stock'),
            func.count(
                case((Product.is_active == True, 1))
            ).label('active_products'),
            # Revenue potential calculation
            func.coalesce(
                func.sum(OrderItem.quantity * OrderItem.unit_price), 0
            ).label('total_revenue_generated')
        )
        .outerjoin(Product)
        .outerjoin(OrderItem)
        .group_by(Supplier.id, Supplier.name, Supplier.rating)
        .order_by(func.coalesce(func.sum(OrderItem.quantity * OrderItem.unit_price), 0).desc())
        .all()
    )
    return results

# SQL equivalents:
# SELECT COUNT(*), AVG(price), MIN(price), MAX(price), SUM(stock_quantity) FROM products;
# SELECT c.name, COUNT(p.id), AVG(p.price), SUM(p.stock_quantity) FROM categories c JOIN products p ON c.id = p.category_id GROUP BY c.id;
```

**JSON Output:**
```json
{
  "query_type": "ADVANCED_AGGREGATION",
  "description": "Comprehensive statistical analysis of products, categories, and suppliers",
  "execution_time_ms": 85,
  "overall_statistics": {
    "description": "Complete product database statistics",
    "data": {
      "total_products": 15,
      "unique_products": 15,
      "avg_price": 283.32,
      "min_price": 24.99,
      "max_price": 2499.99,
      "median_price": 129.99,
      "price_std_dev": 645.23,
      "total_inventory": 1205,
      "total_inventory_value": 341401.95,
      "price_distribution": {
        "budget_under_50": 5,
        "mid_range_50_200": 4,
        "premium_over_200": 6
      }
    }
  },
  "category_performance": {
    "description": "Category-wise performance analysis with business insights",
    "total_categories_analyzed": 5,
    "data": [
      {
        "category_name": "Electronics",
        "product_count": 4,
        "avg_price": 1024.99,
        "min_price": 199.99,
        "max_price": 2499.99,
        "total_stock": 145,
        "inventory_value": 148623.55,
        "budget_items": 0,
        "mid_range_items": 1,
        "premium_items": 3,
        "performance_tier": "Premium Category",
        "market_position": "High-value electronics dominating inventory value"
      },
      {
        "category_name": "Books",
        "product_count": 3,
        "avg_price": 45.32,
        "min_price": 39.99,
        "max_price": 49.99,
        "total_stock": 225,
        "inventory_value": 10197.00,
        "budget_items": 3,
        "mid_range_items": 0,
        "premium_items": 0,
        "performance_tier": "Budget Category",
        "market_position": "High-volume, low-margin educational products"
      },
      {
        "category_name": "Home & Kitchen",
        "product_count": 2,
        "avg_price": 189.99,
        "min_price": 79.99,
        "max_price": 299.99,
        "total_stock": 65,
        "inventory_value": 12349.35,
        "budget_items": 0,
        "mid_range_items": 2,
        "premium_items": 0,
        "performance_tier": "Mid-Range Category",
        "market_position": "Moderate-value household essentials"
      }
    ]
  },
  "supplier_performance": {
    "description": "Supplier analysis with profitability and reliability metrics",
    "total_suppliers_analyzed": 4,
    "data": [
      {
        "supplier_name": "TechCorp",
        "supplier_rating": 4.8,
        "products_supplied": 4,
        "avg_product_price": 1312.49,
        "total_stock_supplied": 145,
        "total_inventory_value": 190211.05,
        "products_in_stock": 4,
        "active_products": 4,
        "total_revenue_generated": 445678.99,
        "performance_metrics": {
          "roi_ratio": 2.34,
          "stock_efficiency": "100%",
          "reliability_score": 9.6
        },
        "supplier_tier": "Premium Partner"
      },
      {
        "supplier_name": "BookWorld",
        "supplier_rating": 4.2,
        "products_supplied": 3,
        "avg_product_price": 45.32,
        "total_stock_supplied": 225,
        "total_inventory_value": 10197.00,
        "products_in_stock": 3,
        "active_products": 3,
        "total_revenue_generated": 15678.45,
        "performance_metrics": {
          "roi_ratio": 1.54,
          "stock_efficiency": "100%",
          "reliability_score": 8.4
        },
        "supplier_tier": "Reliable Volume Partner"
      }
    ]
  },
  "business_insights": {
    "top_performing_category": "Electronics",
    "most_reliable_supplier": "TechCorp",
    "inventory_distribution": {
      "high_value_low_volume": "Electronics",
      "low_value_high_volume": "Books",
      "balanced": "Home & Kitchen"
    },
    "recommendations": [
      "Focus marketing efforts on Electronics for highest ROI",
      "Expand Books category for volume sales",
      "Consider premium pricing for Home & Kitchen items"
    ]
  }
}
```

### 9. Advanced GROUP BY with HAVING

```python
def get_advanced_category_insights(db: Session):
    """Advanced grouping with complex conditions"""
    results = (
        db.query(
            Category.name.label('category_name'),
            func.count(Product.id).label('product_count'),
            func.avg(Product.price).label('avg_price'),
            func.sum(Product.stock_quantity).label('total_stock'),
            # Complex calculations
            func.round(
                func.avg(Product.price) * func.sum(Product.stock_quantity), 2
            ).label('potential_revenue'),
            # Conditional aggregation
            func.sum(
                case((Product.stock_quantity > 50, Product.stock_quantity), else_=0)
            ).label('high_stock_quantity'),
            func.count(
                case((Product.price > func.avg(Product.price), 1))
            ).label('above_avg_price_count')
        )
        .join(Product)
        .group_by(Category.id, Category.name)
        .having(
            func.and_(
                func.count(Product.id) >= 2,  # At least 2 products
                func.avg(Product.price) > 40   # Average price > $40
            )
        )
        .order_by(func.avg(Product.price).desc())
        .all()
    )
    return results

def get_monthly_sales_trends(db: Session):
    """Time-based aggregation for sales analysis"""
    results = (
        db.query(
            func.date_trunc('month', OrderItem.created_at).label('month'),
            func.count(OrderItem.id.distinct()).label('total_orders'),
            func.sum(OrderItem.quantity).label('items_sold'),
            func.sum(OrderItem.quantity * OrderItem.unit_price).label('monthly_revenue'),
            func.avg(OrderItem.quantity * OrderItem.unit_price).label('avg_order_value'),
            # Window functions for trends
            func.lag(func.sum(OrderItem.quantity * OrderItem.unit_price))
            .over(order_by=func.date_trunc('month', OrderItem.created_at))
            .label('previous_month_revenue')
        )
        .group_by(func.date_trunc('month', OrderItem.created_at))
        .order_by(func.date_trunc('month', OrderItem.created_at).desc())
        .limit(12)  # Last 12 months
        .all()
    )
    return results

# SQL equivalent:
# SELECT c.name, COUNT(p.id), AVG(p.price), SUM(p.stock_quantity)
# FROM categories c JOIN products p ON c.id = p.category_id
# GROUP BY c.id, c.name
# HAVING COUNT(p.id) >= 2 AND AVG(p.price) > 40
# ORDER BY AVG(p.price) DESC;
```

**JSON Output:**
```json
{
  "query_type": "ADVANCED_GROUP_BY_HAVING",
  "description": "Complex grouping with filtering and conditional logic",
  "execution_time_ms": 65,
  "category_insights": {
    "description": "Categories meeting specific business criteria",
    "criteria": "Minimum 2 products AND average price > $40",
    "total_qualifying_categories": 3,
    "data": [
      {
        "category_name": "Electronics",
        "product_count": 4,
        "avg_price": 1024.99,
        "total_stock": 145,
        "potential_revenue": 148623.55,
        "high_stock_quantity": 95,
        "above_avg_price_count": 2,
        "insights": {
          "revenue_potential": "Very High",
          "stock_health": "Good - balanced inventory",
          "price_position": "Premium category with strong margins"
        }
      },
      {
        "category_name": "Home & Kitchen",
        "product_count": 2,
        "avg_price": 189.99,
        "total_stock": 65,
        "potential_revenue": 12349.35,
        "high_stock_quantity": 55,
        "above_avg_price_count": 1,
        "insights": {
          "revenue_potential": "Medium",
          "stock_health": "Adequate inventory levels",
          "price_position": "Mid-range with room for premium positioning"
        }
      },
      {
        "category_name": "Sports",
        "product_count": 2,
        "avg_price": 104.99,
        "total_stock": 85,
        "potential_revenue": 8924.15,
        "high_stock_quantity": 70,
        "above_avg_price_count": 0,
        "insights": {
          "revenue_potential": "Medium-Low",
          "stock_health": "Good stock levels",
          "price_position": "Competitive pricing, consider value-adds"
        }
      }
    ]
  },
  "monthly_trends": {
    "description": "Sales performance trends over last 12 months",
    "data": [
      {
        "month": "2023-11-01",
        "month_name": "November 2023",
        "total_orders": 89,
        "items_sold": 245,
        "monthly_revenue": 45678.99,
        "avg_order_value": 513.25,
        "previous_month_revenue": 42341.56,
        "growth_rate": 0.078,
        "performance": "7.8% increase from previous month"
      },
      {
        "month": "2023-10-01",
        "month_name": "October 2023", 
        "total_orders": 76,
        "items_sold": 198,
        "monthly_revenue": 42341.56,
        "avg_order_value": 557.12,
        "previous_month_revenue": 38902.45,
        "growth_rate": 0.088,
        "performance": "8.8% increase from previous month"
      }
    ],
    "trend_analysis": {
      "average_monthly_growth": 0.065,
      "best_performing_month": "November 2023",
      "seasonal_pattern": "Steady growth trend with holiday season boost",
      "recommendations": [
        "Capitalize on November momentum for December sales",
        "Investigate October's high average order value",
        "Plan inventory for continued growth trajectory"
      ]
    }
  }
}
```

---

## 🔍 Subqueries and Complex Query Patterns

**Think of it like:** Subqueries are like asking a question inside another question - "Show me products that cost more than the average price of all products in their category."

### 10. Scalar Subqueries

```python
def get_products_above_category_average(db: Session):
    """Products priced above their category's average price"""
    
    # Subquery to calculate average price per category
    category_avg_subquery = (
        db.query(
            Product.category_id,
            func.avg(Product.price).label('category_avg_price')
        )
        .group_by(Product.category_id)
        .subquery()
    )
    
    # Main query using the subquery
    results = (
        db.query(Product)
        .join(category_avg_subquery, Product.category_id == category_avg_subquery.c.category_id)
        .join(Category)
        .filter(Product.price > category_avg_subquery.c.category_avg_price)
        .add_columns(
            Category.name.label('category_name'),
            category_avg_subquery.c.category_avg_price,
            (Product.price - category_avg_subquery.c.category_avg_price).label('price_premium')
        )
        .order_by((Product.price - category_avg_subquery.c.category_avg_price).desc())
        .all()
    )
    return results

def get_products_with_above_average_orders(db: Session):
    """Products with order counts above the overall average"""
    
    # Calculate overall average orders per product
    avg_orders_scalar = (
        db.query(func.avg(func.count(OrderItem.id)))
        .join(Product)
        .group_by(Product.id)
        .scalar_subquery()
    )
    
    results = (
        db.query(Product)
        .outerjoin(OrderItem)
        .join(Category)
        .group_by(Product.id, Category.name)
        .having(func.count(OrderItem.id) > avg_orders_scalar)
        .add_columns(
            Category.name.label('category_name'),
            func.count(OrderItem.id).label('order_count'),
            avg_orders_scalar.label('average_orders')
        )
        .order_by(func.count(OrderItem.id).desc())
        .all()
    )
    return results

# SQL equivalent:
# SELECT p.*, c.name, cat_avg.avg_price
# FROM products p
# JOIN categories c ON p.category_id = c.id
# JOIN (
#     SELECT category_id, AVG(price) as avg_price 
#     FROM products 
#     GROUP BY category_id
# ) cat_avg ON p.category_id = cat_avg.category_id
# WHERE p.price > cat_avg.avg_price;
```

### 11. Correlated Subqueries

```python
def get_most_expensive_product_per_category(db: Session):
    """Find the most expensive product in each category using correlated subquery"""
    
    # Correlated subquery - references outer query
    max_price_subquery = (
        db.query(func.max(Product.price))
        .filter(Product.category_id == Category.id)
        .correlate(Category)
        .scalar_subquery()
    )
    
    results = (
        db.query(Category)
        .outerjoin(Product, 
            func.and_(
                Product.category_id == Category.id,
                Product.price == max_price_subquery
            )
        )
        .add_columns(
            Product.name.label('most_expensive_product'),
            Product.price.label('highest_price'),
            max_price_subquery.label('max_price_check')
        )
        .order_by(max_price_subquery.desc().nullslast())
        .all()
    )
    return results

def get_categories_with_recent_activity(db: Session):
    """Categories that have products ordered in the last 30 days"""
    thirty_days_ago = datetime.now() - timedelta(days=30)
    
    # EXISTS subquery - correlated
    recent_orders_exists = (
        db.query(OrderItem.id)
        .join(Product)
        .filter(
            Product.category_id == Category.id,
            OrderItem.created_at >= thirty_days_ago
        )
        .correlate(Category)
        .exists()
    )
    
    results = (
        db.query(Category)
        .filter(recent_orders_exists)
        .add_columns(
            # Count of recent orders for this category
            db.query(func.count(OrderItem.id))
            .join(Product)
            .filter(
                Product.category_id == Category.id,
                OrderItem.created_at >= thirty_days_ago
            )
            .correlate(Category)
            .scalar_subquery()
            .label('recent_order_count')
        )
        .order_by(Category.name)
        .all()
    )
    return results

# SQL equivalent:
# SELECT c.*, p.name, p.price
# FROM categories c
# LEFT JOIN products p ON p.category_id = c.id 
#   AND p.price = (SELECT MAX(price) FROM products WHERE category_id = c.id);
```

**JSON Output:**
```json
{
  "query_type": "SUBQUERIES_AND_COMPLEX_PATTERNS",
  "description": "Advanced queries using scalar and correlated subqueries",
  "execution_time_ms": 125,
  "scalar_subquery_results": {
    "products_above_category_average": {
      "description": "Products priced higher than their category average",
      "total_products": 6,
      "data": [
        {
          "product_id": 2,
          "product_name": "MacBook Pro M3",
          "price": 2499.99,
          "category_name": "Electronics",
          "category_avg_price": 1024.99,
          "price_premium": 1475.00,
          "premium_percentage": 143.9,
          "positioning": "Ultra-premium product significantly above category average"
        },
        {
          "product_id": 1,
          "product_name": "iPhone 15 Pro",
          "price": 1199.99,
          "category_name": "Electronics",
          "category_avg_price": 1024.99,
          "price_premium": 175.00,
          "premium_percentage": 17.1,
          "positioning": "Premium product moderately above category average"
        },
        {
          "product_id": 6,
          "product_name": "Coffee Maker",
          "price": 299.99,
          "category_name": "Home & Kitchen",
          "category_avg_price": 189.99,
          "price_premium": 110.00,
          "premium_percentage": 57.9,
          "positioning": "High-end appliance in mid-range category"
        }
      ],
      "category_analysis": {
        "Electronics": {
          "products_above_average": 2,
          "average_premium": 825.00,
          "strategy": "Premium positioning working well"
        },
        "Home & Kitchen": {
          "products_above_average": 1,
          "average_premium": 110.00,
          "strategy": "Room for more premium offerings"
        }
      }
    },
    "high_performing_products": {
      "description": "Products with above-average order volumes",
      "overall_average_orders": 12.5,
      "high_performers": 5,
      "data": [
        {
          "product_id": 1,
          "product_name": "iPhone 15 Pro",
          "category_name": "Electronics",
          "order_count": 25,
          "average_orders": 12.5,
          "performance_multiplier": 2.0,
          "status": "Top performer - double the average"
        },
        {
          "product_id": 5,
          "product_name": "Python Programming Book",
          "category_name": "Books",
          "order_count": 18,
          "average_orders": 12.5,
          "performance_multiplier": 1.44,
          "status": "Strong performer in education category"
        }
      ]
    }
  },
  "correlated_subquery_results": {
    "category_premium_products": {
      "description": "Most expensive product in each category",
      "data": [
        {
          "category_id": 1,
          "category_name": "Electronics",
          "most_expensive_product": "MacBook Pro M3",
          "highest_price": 2499.99,
          "category_position": "Flagship product driving category value"
        },
        {
          "category_id": 2,
          "category_name": "Books",
          "most_expensive_product": "Python Programming Book",
          "highest_price": 49.99,
          "category_position": "Premium educational content"
        },
        {
          "category_id": 7,
          "category_name": "Automotive",
          "most_expensive_product": null,
          "highest_price": null,
          "category_position": "Empty category - needs product development"
        }
      ]
    },
    "active_categories": {
      "description": "Categories with orders in the last 30 days",
      "analysis_period": "Last 30 days",
      "active_categories": 4,
      "data": [
        {
          "category_id": 1,
          "category_name": "Electronics",
          "recent_order_count": 67,
          "activity_level": "Very High - consistently strong sales"
        },
        {
          "category_id": 2,
          "category_name": "Books",
          "recent_order_count": 23,
          "activity_level": "High - steady educational demand"
        },
        {
          "category_id": 3,
          "category_name": "Home & Kitchen",
          "recent_order_count": 8,
          "activity_level": "Moderate - seasonal patterns"
        },
        {
          "category_id": 4,
          "category_name": "Sports",
          "recent_order_count": 5,
          "activity_level": "Low - consider promotional campaigns"
        }
      ]
    }
  },
  "business_insights": {
    "pricing_strategy": {
      "premium_positioning": "Electronics category successfully supports premium pricing",
      "opportunity": "Home & Kitchen category has potential for more premium products",
      "risk": "Books category may be price-sensitive"
    },
    "inventory_management": {
      "focus_categories": ["Electronics", "Books"],
      "growth_opportunities": ["Home & Kitchen", "Sports"],
      "requires_attention": ["Automotive", "Jewelry"]
    },
    "performance_optimization": [
      "Expand Electronics premium segment",
      "Develop Home & Kitchen premium line",
      "Implement promotional campaigns for Sports category",
      "Consider discontinuing empty categories or aggressive stocking"
    ]
  }
}
```

---

## 📊 Query Performance Summary

This comprehensive guide has covered every major query pattern in SQLAlchemy from basic SELECT statements to complex subqueries. Here's what you've learned:

### 🎯 **Query Types Covered**
1. **Basic Queries**: SELECT, WHERE, ORDER BY, LIMIT
2. **JOIN Operations**: INNER, LEFT, RIGHT, FULL OUTER
3. **Aggregations**: GROUP BY, HAVING, statistical functions
4. **Subqueries**: Scalar, correlated, EXISTS patterns
5. **Advanced Patterns**: Window functions, CTEs, complex analytics

### 📈 **JSON Output Benefits**
- **Detailed Execution Metrics**: Timing, record counts, performance analysis
- **Business Insights**: Actionable recommendations and data interpretation
- **Error Context**: Clear explanations when queries fail
- **Optimization Guidance**: Index usage, query planning suggestions

### 🚀 **Performance Best Practices**
- Use appropriate indexes for JOIN conditions
- Implement pagination for large result sets
- Leverage eager loading to prevent N+1 queries
- Monitor query execution times and optimize accordingly
- Use EXPLAIN ANALYZE for query optimization

Ready to implement these patterns in your FastAPI application!
