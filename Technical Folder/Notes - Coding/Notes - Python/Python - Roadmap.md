# Python Skill Roadmap — In-Depth Syllabus

## Realistic Timeline

| Pace | Time to "can contribute to a real project" |
|---|---|
| Full-time (4–6 hrs/day) | **9–11 weeks** |
| Part-time (1–2 hrs/day) | **16–20 weeks (~4–5 months)** |

This gets a novice to *working proficiency* across all 9 modules below. Fluency needs 6–12 months of real project reps after this. Every subtopic should end with a tiny exercise, not just reading.

---

# 📁 Module 1: Python Basics

## Variables & Data Types
A variable is a labeled box holding a value; Python infers the type automatically.
| Type | Example |
|---|---|
| `int` | `age = 24` |
| `float` | `price = 99.5` |
| `str` | `name = "Asha"` |
| `bool` | `is_active = True` |
| `list` / `tuple` / `dict` / `set` | covered in Module 2 |
| `NoneType` | `x = None` |
```python
age = 24
price = 99.99
print(type(age))        # <class 'int'>
age_text = str(age)     # type casting
```
**Real world:** A signup form stores `username` (str), `age` (int), `newsletter_opt_in` (bool).

## Input & Output
`input()` reads from the user (always returns a string); `print()` displays output.
```python
name = input("Enter your name: ")
age = int(input("Enter your age: "))       # cast to int
print(f"Hello {name}, you are {age} years old.")
print("Price: {:.2f}".format(99.5))         # formatted output
```
**Real world:** A command-line billing tool that asks the cashier to type in item price and quantity.

## Operators
| Type | Examples |
|---|---|
| Arithmetic | `+ - * / // % **` |
| Comparison | `== != > < >= <=` |
| Logical | `and or not` |
| Assignment | `= += -= *= /=` |
| Membership | `in`, `not in` |
| Identity | `is`, `is not` |
```python
total = 100 // 3        # 33 (floor division)
remainder = 100 % 3     # 1
is_valid = (age >= 18) and (has_id == True)
print("apple" in ["apple", "banana"])   # True
```
**Real world:** `discount = price * 0.1 if is_member else 0` — pricing logic on checkout.

## Conditional Statements
Branch code based on a condition.
```python
marks = 78
if marks >= 90:
    grade = "A"
elif marks >= 75:
    grade = "B"
else:
    grade = "C"

status = "Adult" if age >= 18 else "Minor"   # ternary (one-line if/else)
```
**Real world:** Loan eligibility check — approve/reject based on income, credit score, age.

## Loops
**for loop** — iterate over a known sequence.
```python
for item in ["apple", "banana"]:
    print(item)
for i in range(5):          # 0,1,2,3,4
    print(i)
```
**while loop** — repeat until a condition is False.
```python
attempts = 0
while attempts < 3:
    print("Trying login...")
    attempts += 1
```
**Nested loops**, **loop control** (`break`, `continue`, `pass`), and loop `else`:
```python
for row in range(3):
    for col in range(3):
        if col == 2:
            break
        print(row, col)
```
**Real world:** Looping through 10,000 order rows to flag `status == "failed"`; retry-until-success API calls.

---

# 📁 Module 2: Core Python Concepts

## Lists
Ordered, mutable collection.
```python
fruits = ["apple", "banana", "cherry"]
fruits.append("mango")
fruits.remove("banana")
fruits.sort()
print(fruits[0], fruits[-1], fruits[1:3])   # indexing & slicing
squares = [x*x for x in range(5)]           # list comprehension
```
**Real world:** A shopping cart storing item names in the order they were added.

## Tuples
Ordered, **immutable** — can't be changed after creation. Faster than lists, used for fixed data.
```python
coordinates = (12.9, 77.6)
lat, lon = coordinates      # unpacking
```
**Real world:** GPS coordinates, RGB color values — values that should never accidentally change.

## Sets
Unordered, no duplicates. Great for uniqueness checks and math-style set operations.
```python
ids_a = {101, 102, 103}
ids_b = {102, 103, 104}
print(ids_a & ids_b)    # intersection {102, 103}
print(ids_a | ids_b)    # union
print(ids_a - ids_b)    # difference
```
**Real world:** Finding customers who bought in both January and February (`jan_set & feb_set`).

## Dictionaries
Key-value pairs — the most-used structure in real apps.
```python
user = {"name": "Asha", "age": 24, "city": "Bengaluru"}
user["email"] = "asha@mail.com"      # add key
for key, value in user.items():
    print(key, value)
```
**Real world:** A single API response representing one user record, or JSON config settings.

## Strings
Text data — immutable, richly supported with built-in methods.
```python
name = "  Asha Sharma  "
print(name.strip().lower())          # "asha sharma"
print(name.strip().split(" "))       # ['Asha', 'Sharma']
print(f"Hello, {name.strip()}!")     # f-string formatting
print("Asha" in name)                # membership check
```
**Real world:** Cleaning messy user-entered names/emails before saving to a database.

## Functions
Named, reusable blocks of logic.
```python
def total_price(items, discount=0):     # 'discount' has a default value
    return sum(items) * (1 - discount)

def total(*numbers):                     # *args — variable positional args
    return sum(numbers)

def profile(**info):                     # **kwargs — variable keyword args
    print(info)

square = lambda x: x * x                 # lambda (anonymous one-liner)

def factorial(n):                        # recursion
    return 1 if n <= 1 else n * factorial(n - 1)
```
**Real world:** `calculate_total_price()` reused across the cart page, invoice, and refund calculator.

---

# 📁 Module 3: Problem Solving

## Patterns
Nested loops to print shapes — trains loop-thinking.
```python
for i in range(1, 5):
    print("*" * i)
# *
# **
# ***
# ****
```
**Real world:** Rare in production, but the #1 interview warm-up for loop logic.

## Number Problems
```python
def is_prime(n):
    if n < 2: return False
    for i in range(2, int(n**0.5) + 1):
        if n % i == 0: return False
    return True

def fibonacci(n):
    a, b = 0, 1
    for _ in range(n):
        print(a, end=" ")
        a, b = b, a + b
```
**Real world:** Prime checks in cryptography basics; Fibonacci in algorithm interviews.

## String Problems
```python
def is_palindrome(s):
    s = s.lower().replace(" ", "")
    return s == s[::-1]           # [::-1] reverses the string

print(is_palindrome("Nurses Run"))   # True
```
**Real world:** Validating input formats, detecting duplicate/mirrored codes.

## List Problems
```python
nums = [4, 2, 9, 2, 7, 9]
unique = list(set(nums))              # remove duplicates
second_largest = sorted(set(nums))[-2]
```
**Real world:** De-duplicating a customer email list before a mass mailer.

## Searching
```python
def linear_search(arr, target):
    for i, val in enumerate(arr):
        if val == target: return i
    return -1

def binary_search(arr, target):        # arr must be sorted
    lo, hi = 0, len(arr) - 1
    while lo <= hi:
        mid = (lo + hi) // 2
        if arr[mid] == target: return mid
        elif arr[mid] < target: lo = mid + 1
        else: hi = mid - 1
    return -1
```
**Real world:** Binary search powers fast lookups in sorted databases/indexes.

## Sorting Basics
```python
nums = [5, 2, 9, 1]
nums.sort()                          # in-place, built-in (Timsort — use this in practice)
sorted_copy = sorted(nums, reverse=True)

def bubble_sort(arr):                # understand the concept, don't use in production
    for i in range(len(arr)):
        for j in range(len(arr) - i - 1):
            if arr[j] > arr[j+1]:
                arr[j], arr[j+1] = arr[j+1], arr[j]
```
**Real world:** Sorting a leaderboard by score, or products by price.

---

# 📁 Module 4: Object-Oriented Python

## Classes & Objects
A **class** is a blueprint; an **object** is one instance built from it.
```python
class Product:
    def __init__(self, name, price):
        self.name = name
        self.price = price

laptop = Product("Laptop", 55000)
```

## Constructors
`__init__` runs automatically when an object is created — sets up initial state.
```python
class BankAccount:
    def __init__(self, owner, balance=0):
        self.owner = owner
        self.balance = balance
```

## Inheritance
A class reuses another class's code.
```python
class SavingsAccount(BankAccount):        # inherits everything from BankAccount
    def add_interest(self, rate):
        self.balance += self.balance * rate
```

## Encapsulation
Hide internal details; convention: `_protected`, `__private`.
```python
class Account:
    def __init__(self, balance):
        self.__balance = balance          # private — not directly accessible outside
    def get_balance(self):
        return self.__balance
```

## Polymorphism
Same method name, different behavior per class.
```python
class Dog:
    def speak(self): return "Woof"
class Cat:
    def speak(self): return "Meow"

for animal in [Dog(), Cat()]:
    print(animal.speak())
```

## Real OOP Examples
A mini "Library Management" system tying it all together:
```python
class Book:
    def __init__(self, title, available=True):
        self.title = title
        self.available = available

class Library:
    def __init__(self):
        self.books = []
    def add_book(self, book):
        self.books.append(book)
    def borrow(self, title):
        for b in self.books:
            if b.title == title and b.available:
                b.available = False
                return f"You borrowed {title}"
        return "Not available"
```
**Real world:** Every Django/Flask model (`User`, `Order`, `Product`) is a class built this way.

---

# 📁 Module 5: File Handling & Errors

## Read Files
```python
with open("notes.txt") as f:
    print(f.read())          # whole file
    # f.readline() → one line, f.readlines() → list of lines
```

## Write Files
```python
with open("sales.txt", "w") as f:   # 'w' overwrites, 'a' appends
    f.write("2026-08-25, 4500\n")
```

## CSV Files
```python
import csv
with open("users.csv") as f:
    reader = csv.DictReader(f)
    for row in reader:
        print(row["name"], row["email"])
```

## JSON Files
```python
import json
with open("config.json") as f:
    config = json.load(f)          # JSON file → Python dict
with open("output.json", "w") as f:
    json.dump({"status": "done"}, f)
```

## Exception Handling
```python
try:
    with open("report.txt") as f:
        data = f.read()
    result = 10 / 0
except FileNotFoundError:
    print("File missing.")
except ZeroDivisionError:
    print("Can't divide by zero.")
finally:
    print("Cleanup runs no matter what.")
```

## Logging Basics
Better than `print()` for real apps — timestamps, severity levels, saved to file.
```python
import logging
logging.basicConfig(filename="app.log", level=logging.INFO)
logging.info("Script started")
logging.error("Something failed")
```
**Real world:** Parsing an uploaded `employees.csv` to bulk-create accounts, with errors logged instead of crashing the whole script.

---

# 📁 Module 6: Python Libraries

## NumPy Basics
Fast numerical arrays — the foundation under Pandas and ML libraries.
```python
import numpy as np
arr = np.array([1, 2, 3, 4])
print(arr.mean(), arr.sum(), arr * 2)
matrix = np.array([[1,2],[3,4]])
```
**Real world:** Fast bulk math on sensor readings or financial time-series.

## Pandas Basics
Tabular data — "Excel, but scriptable."
```python
import pandas as pd
df = pd.read_csv("sales.csv")
df.groupby("month")["revenue"].sum()
df[df["revenue"] > 5000]           # filter
```
**Real world:** Turning a 50,000-row sales export into a monthly revenue summary.

## Matplotlib Basics
Charts and plots.
```python
import matplotlib.pyplot as plt
plt.plot([1,2,3], [10,20,15])
plt.title("Sales Trend")
plt.xlabel("Month"); plt.ylabel("Revenue")
plt.savefig("chart.png")
```
**Real world:** A monthly revenue trend chart attached to a report email.

## Requests
Call APIs over HTTP.
```python
import requests
r = requests.get("https://api.exchangerate.host/latest", params={"base": "USD"})
print(r.json()["rates"]["INR"])
```
**Real world:** Pulling live currency/weather data into a dashboard.

## BeautifulSoup
Parse HTML to extract data from web pages.
```python
from bs4 import BeautifulSoup
import requests
html = requests.get("https://example.com").text
soup = BeautifulSoup(html, "html.parser")
titles = [h.text for h in soup.find_all("h2")]
```
**Real world:** Scraping product prices from a competitor's website daily.

## Streamlit Basics
Turn a Python script into a shareable web app in minutes — no HTML/CSS needed.
```python
import streamlit as st
st.title("Expense Tracker")
amount = st.number_input("Enter expense amount")
if st.button("Add"):
    st.write(f"Added ₹{amount}")
```
**Real world:** Quickly demoing a data tool to your manager without building a full frontend.

---

# 📁 Module 7: Automation Skills

## File Organizer
```python
import os, shutil
for f in os.listdir("downloads"):
    if f.endswith(".pdf"):
        shutil.move(f"downloads/{f}", f"pdfs/{f}")
```
**Real world:** Auto-sorting a messy Downloads folder by file type every night.

## Email Automation
```python
import smtplib
with smtplib.SMTP("smtp.gmail.com", 587) as server:
    server.starttls()
    server.login("you@gmail.com", "app_password")
    server.sendmail("you@gmail.com", "boss@company.com", "Subject: Report\n\nDone.")
```
**Real world:** Auto-emailing the daily sales report at 9 AM without manual work.

## Web Scraping
```python
from bs4 import BeautifulSoup
import requests
html = requests.get("https://example.com/products").text
soup = BeautifulSoup(html, "html.parser")
prices = [p.text for p in soup.select(".price")]
```
**Real world:** Tracking a competitor's product prices automatically.

## API Automation
```python
import requests, schedule, time
def sync_data():
    r = requests.get("https://api.example.com/latest")
    print(r.json())
schedule.every(1).hours.do(sync_data)
while True:
    schedule.run_pending(); time.sleep(60)
```
**Real world:** Pulling fresh exchange rates into your system every hour automatically.

## Excel Automation
```python
import openpyxl
wb = openpyxl.load_workbook("report.xlsx")
wb["Sheet1"]["A1"] = "Updated by script"
wb.save("report.xlsx")
```
**Real world:** Auto-filling a weekly Excel report template with fresh numbers.

## Task Scheduler
```python
import schedule, time
def daily_report():
    print("Sending report...")
schedule.every().day.at("09:00").do(daily_report)
while True:
    schedule.run_pending()
    time.sleep(60)
```
**Real world:** Running the whole pipeline above (scrape → process → email) every night, unattended.

---

# 📁 Module 8: Backend Basics

## Flask Basics
```python
from flask import Flask, request, jsonify
app = Flask(__name__)

@app.route("/user/<name>")
def get_user(name):
    return jsonify({"message": f"Hello {name}"})

if __name__ == "__main__":
    app.run(debug=True)
```

## FastAPI Basics
Modern, faster, auto-generates docs, validates data via type hints.
```python
from fastapi import FastAPI
from pydantic import BaseModel

app = FastAPI()

class Order(BaseModel):
    item: str
    qty: int

@app.post("/order")
def create_order(order: Order):
    return {"status": "created", "item": order.item}
```
Run: `uvicorn main:app --reload` → docs auto-generated at `/docs`.

## REST APIs
The convention behind Flask/FastAPI endpoints.
| Method | Purpose |
|---|---|
| GET | fetch data |
| POST | create data |
| PUT/PATCH | update data |
| DELETE | remove data |
Status codes: `200` OK, `201` Created, `401` Unauthorized, `404` Not Found, `500` Server Error.

## Databases
Connecting your API to persistent storage.
```python
import sqlite3
conn = sqlite3.connect("shop.db")
cur = conn.cursor()
cur.execute("SELECT name FROM products WHERE price > ?", (500,))
print(cur.fetchall())
```
**Real world:** Storing every order placed through the API in a `orders` table.

## Authentication Basics
Verifying who's calling your API.
```python
from fastapi import Header, HTTPException

def verify_token(x_token: str = Header(...)):
    if x_token != "SECRET123":
        raise HTTPException(status_code=401, detail="Invalid token")
```
**Real world:** Requiring an API key before a client can place an order or read user data.

## Deploy Your API
Getting it live for others to use — e.g., on **Render**, **Railway**, or a VPS.
```bash
pip freeze > requirements.txt
# Push to GitHub, connect repo to Render/Railway, set start command:
uvicorn main:app --host 0.0.0.0 --port 8000
```
**Real world:** Turning your FastAPI project from "runs on my laptop" into a public URL others can call.

---

# 📁 Module 9: Portfolio Projects

Each project combines multiple modules above — build these to prove skill, not just describe it.

## Expense Tracker
**Stack:** Python + File/CSV handling + Streamlit. Log expenses, categorize, show totals by category/month.

## Weather App
**Stack:** Requests (weather API) + Flask/FastAPI or Streamlit UI. User enters a city → live weather shown.

## Web Scraper
**Stack:** Requests + BeautifulSoup + Pandas. Scrape product prices/listings → save clean data to CSV.

## URL Shortener
**Stack:** FastAPI + Database (SQLite). POST a long URL → get a short code → GET the short code → redirect to original.

## Automation Bot
**Stack:** Task Scheduler + Email Automation + Excel Automation. Runs nightly: pulls data, builds a report, emails it — zero manual work.

## AI Note Summarizer
**Stack:** File Handling (read .txt/.pdf) + Requests (call an LLM API) + Streamlit UI. Paste/upload notes → get a short summary back.

---

## Suggested Weekly Plan
- **Weeks 1–2:** Python Basics
- **Weeks 3–4:** Core Python Concepts (+ start Git in parallel from day 1)
- **Weeks 5–6:** Problem Solving
- **Weeks 7–8:** Object-Oriented Python
- **Week 9:** File Handling & Errors
- **Weeks 10–11:** Python Libraries
- **Weeks 12–13:** Automation Skills
- **Weeks 14–16:** Backend Basics
- **Weeks 17–20:** Portfolio Projects (build all 6, one per week where possible)

**Golden rule:** each subtopic ends with a tiny exercise, and each module ends with one small project — that's what actually builds proficiency, not reading.
