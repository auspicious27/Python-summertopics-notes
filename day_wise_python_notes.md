# Python Day 12 to Day 17 - Complete Hinglish Notes

Functions, File Handling, Exception Handling, Mini Projects, Modules, OOP, Automation, SMTP, SMS APIs, and WhatsApp Messages

Language style: Proper Hinglish with simple English technical terms.

Goal: Day-wise topics ko structured way mein samjhana with practical code and line-by-line explanation.

---

## Day Wise Index

| Day | Main Topic | Project |
|---|---|---|
| Day 12 | Functions in Python | Function practice |
| Day 14 | File Handling and Exception Handling | Safe file read/write |
| Day 15 | Mini Project 5 | Student Record File System |
| Day 16 | Modules, Libraries and OOP | Bank Account System |
| Day 17 | Python Automation and Capstone | File/email/SMS/WhatsApp automation |

---

# Day 12 - Functions in Python

## Topics Covered

- Defining functions
- Function calling
- Parameters and arguments
- Return values
- Default arguments
- Keyword arguments
- Lambda functions
- Scope of variables

---

## 1. Defining and Calling Functions

Function ek reusable code block hota hai.

## Code

```python
def greet():
    print("Hello, welcome to Python functions")

greet()
```

## Output

```text
Hello, welcome to Python functions
```

## Explanation

| Code | Hinglish Explanation |
|---|---|
| `def greet():` | Function define ho raha hai. Function ka naam `greet` hai. |
| `print(...)` | Function ke andar ka kaam. |
| `greet()` | Function call ho raha hai. Function tabhi run hota hai jab call karte hain. |

---

## 2. Parameters and Arguments

Parameter function definition mein hota hai. Argument actual value hoti hai.

```python
def welcome(name):
    print(f"Welcome {name}")

welcome("Rahul")
welcome("Priya")
```

Output:

```text
Welcome Rahul
Welcome Priya
```

Explanation:

| Term | Example | Meaning |
|---|---|---|
| Parameter | `name` | Function ke andar variable |
| Argument | `"Rahul"` | Function call ke time actual value |

---

## 3. Return Values

`return` function ka result bahar bhejta hai.

```python
def add(a, b):
    result = a + b
    return result

answer = add(10, 20)
print(answer)
```

Output:

```text
30
```

Line explanation:

| Line | Code | Meaning |
|---|---|---|
| 1 | `def add(a, b):` | Function two inputs leta hai. |
| 2 | `result = a + b` | Addition hoti hai. |
| 3 | `return result` | Result bahar send hota hai. |
| 5 | `answer = add(10, 20)` | Function call ka result answer mein store hota hai. |
| 6 | `print(answer)` | Answer print hota hai. |

---

## 4. Default Arguments

Default argument tab use hota hai jab value na mile to backup value use karni ho.

```python
def create_user(name, role="student"):
    print(f"Name: {name}, Role: {role}")

create_user("Rahul")
create_user("Admin", "admin")
```

Output:

```text
Name: Rahul, Role: student
Name: Admin, Role: admin
```

Explanation:

`role="student"` default value hai. Agar role pass nahi karte, student use hota hai.

---

## 5. Keyword Arguments

Keyword arguments mein value parameter ke naam ke saath pass hoti hai.

```python
def profile(name, city, course):
    print(f"{name} from {city} is learning {course}")

profile(course="Python", name="Rahul", city="Delhi")
```

Output:

```text
Rahul from Delhi is learning Python
```

Explanation:

Order matter nahi karta because values names ke saath pass hui hain.

---

## 6. Lambda Functions

Lambda small one-line function hota hai.

```python
square = lambda x: x * x

print(square(5))
```

Output:

```text
25
```

Explanation:

| Code | Meaning |
|---|---|
| `lambda x:` | Ek input leta hai |
| `x * x` | Square return karta hai |
| `square(5)` | 5 ka square |

---

## 7. Scope of Variables

Scope ka matlab variable kaha accessible hai.

```python
name = "Global Rahul"

def show_name():
    name = "Local Priya"
    print(name)

show_name()
print(name)
```

Output:

```text
Local Priya
Global Rahul
```

Explanation:

Function ke andar wala `name` local variable hai. Function ke bahar wala `name` global variable hai.

---

# Day 14 - File Handling and Exception Handling

## Topics Covered

- File read/write operations
- File modes
- Data storage techniques
- `try`, `except`, `finally`
- Error handling techniques
- Exception handling with files

---

## 1. File Write Operation

```python
file = open("data.txt", "w")
file.write("Hello, this is file handling.")
file.close()
```

Explanation:

| Code | Hinglish Explanation |
|---|---|
| `open("data.txt", "w")` | File write mode mein open hoti hai. Agar file nahi hai to create hogi. |
| `write(...)` | Text file mein write hota hai. |
| `close()` | File close hoti hai. |

Important:

`w` mode old data overwrite kar sakta hai.

---

## 2. File Read Operation

```python
file = open("data.txt", "r")
content = file.read()
file.close()

print(content)
```

Explanation:

| Code | Meaning |
|---|---|
| `open(..., "r")` | Read mode |
| `read()` | File ka content read karta hai |
| `content` | Read data variable mein store hota hai |

---

## 3. File Append Operation

```python
file = open("data.txt", "a")
file.write("\nThis is new line.")
file.close()
```

Explanation:

`a` append mode hai. New data old data ke end mein add hota hai.

---

## 4. File Modes

| Mode | Meaning |
|---|---|
| `r` | Read |
| `w` | Write and overwrite |
| `a` | Append |
| `x` | Create new file only |

---

## 5. Exception Handling

Exception handling errors ko handle karta hai.

```python
try:
    file = open("missing.txt", "r")
    content = file.read()
    print(content)
except FileNotFoundError:
    print("File not found.")
finally:
    print("File operation completed.")
```

Output:

```text
File not found.
File operation completed.
```

Explanation:

| Block | Meaning |
|---|---|
| `try` | Risky code |
| `except` | Error handle |
| `finally` | Always run |

---

# Day 15 - Mini Project 5: Student Record File System

## Project Features

- Add student records
- Update student details
- Delete student records
- Search student data
- File-based data storage

---

## Project Idea

Student records file mein store honge. Har record ek line mein hoga.

Format:

```text
roll,name,course
```

Example:

```text
101,Rahul,Python
```

---

## Full Code

```python
def add_student():
    roll = input("Enter roll number: ")
    name = input("Enter name: ")
    course = input("Enter course: ")

    file = open("students.txt", "a")
    file.write(f"{roll},{name},{course}\n")
    file.close()

    print("Student record added.")

def show_students():
    try:
        file = open("students.txt", "r")
        records = file.readlines()
        file.close()

        for record in records:
            print(record.strip())
    except FileNotFoundError:
        print("No student records found.")

def search_student():
    search_roll = input("Enter roll number to search: ")

    try:
        file = open("students.txt", "r")
        records = file.readlines()
        file.close()

        found = False

        for record in records:
            roll, name, course = record.strip().split(",")
            if roll == search_roll:
                print(f"Found: {roll} - {name} - {course}")
                found = True

        if not found:
            print("Student not found.")
    except FileNotFoundError:
        print("No student records found.")

add_student()
show_students()
search_student()
```

## Detailed Explanation

| Code | Hinglish Explanation |
|---|---|
| `add_student()` | New student record add karta hai. |
| `input(...)` | User se roll, name, course leta hai. |
| `open("students.txt", "a")` | Append mode mein file open hoti hai. |
| `file.write(...)` | Student data file mein save hota hai. |
| `show_students()` | File ke saare records read and print karta hai. |
| `readlines()` | File ki saari lines list mein return karta hai. |
| `record.strip()` | Extra newline remove karta hai. |
| `search_student()` | Roll number ke basis par student search karta hai. |
| `split(",")` | CSV line ko roll, name, course mein divide karta hai. |
| `found = False` | Search result track karta hai. |
| `if not found` | Agar record nahi mila to message print hota hai. |

---

# Day 16 - Modules, Libraries and OOP

## Topics Covered

- Built-in modules
- Creating custom modules
- Classes and objects
- Constructors
- Inheritance
- Encapsulation
- Bank Account System

---

## 1. Built-in Module

```python
import math

print(math.sqrt(25))
```

Output:

```text
5.0
```

Explanation:

`math` built-in module hai. `sqrt()` square root calculate karta hai.

---

## 2. Custom Module

Create `calculator.py`:

```python
def add(a, b):
    return a + b
```

Create `main.py`:

```python
import calculator

print(calculator.add(10, 20))
```

Output:

```text
30
```

Explanation:

Custom module apna reusable Python file hota hai.

---

## 3. Classes and Objects

Class blueprint hoti hai. Object us blueprint se created actual item hota hai.

```python
class Student:
    def __init__(self, name, course):
        self.name = name
        self.course = course

    def show_details(self):
        print(f"{self.name} is learning {self.course}")

student1 = Student("Rahul", "Python")
student1.show_details()
```

Output:

```text
Rahul is learning Python
```

Explanation:

| Code | Meaning |
|---|---|
| `class Student:` | Student class create hui |
| `__init__` | Constructor, object create hote time run hota hai |
| `self.name` | Object ka name property |
| `show_details()` | Method |
| `student1 = Student(...)` | Object create hua |

---

## Mini Project - Bank Account System

```python
class BankAccount:
    def __init__(self, account_holder, balance):
        self.account_holder = account_holder
        self.balance = balance

    def deposit(self, amount):
        self.balance += amount
        print(f"Deposited: {amount}")

    def withdraw(self, amount):
        if amount <= self.balance:
            self.balance -= amount
            print(f"Withdrawn: {amount}")
        else:
            print("Insufficient balance.")

    def check_balance(self):
        print(f"Balance: {self.balance}")

account = BankAccount("Rahul", 1000)
account.deposit(500)
account.withdraw(300)
account.check_balance()
```

Output:

```text
Deposited: 500
Withdrawn: 300
Balance: 1200
```

Explanation:

| Code | Hinglish Explanation |
|---|---|
| `BankAccount` | Bank account ka class blueprint |
| `__init__` | Account holder and balance set karta hai |
| `deposit()` | Balance mein amount add karta hai |
| `withdraw()` | Balance check karke amount minus karta hai |
| `check_balance()` | Current balance show karta hai |
| `account = BankAccount(...)` | New account object create hota hai |

---

# Day 17 - Python Automation and Capstone Project

## Topics Covered

- OS module
- File automation
- Running system commands
- Sending email using SMTP
- Sending SMS using APIs
- Sending WhatsApp messages
- Handling credentials securely

---

## 1. OS Module

```python
import os

print(os.getcwd())
print(os.listdir())
```

Explanation:

| Code | Meaning |
|---|---|
| `os.getcwd()` | Current working directory |
| `os.listdir()` | Current folder files list |

---

## 2. File Automation

```python
import os

folder_name = "reports"

if not os.path.exists(folder_name):
    os.mkdir(folder_name)
    print("Folder created.")
else:
    print("Folder already exists.")
```

Explanation:

| Code | Hinglish Explanation |
|---|---|
| `os.path.exists()` | Folder exist karta hai ya nahi check karta hai |
| `os.mkdir()` | New folder create karta hai |

---

## 3. Running System Commands

```python
import os

os.system("dir")
```

Windows par `dir` command current folder files show karta hai.

---

## 4. Sending Email using SMTP

Same as Session 4 email automation, but capstone mein credentials secure rakhna important hai.

Better:

```python
import os

email = os.getenv("EMAIL_USER")
password = os.getenv("EMAIL_PASSWORD")
```

Explanation:

Environment variables secrets ko code se bahar rakhte hain.

---

## 5. Sending SMS using APIs

Twilio API use kar sakte hain.

Important:

- Account SID secret rakho
- Auth token secret rakho
- Phone numbers verify karo
- API usage cost check karo

---

## 6. WhatsApp Messages

PyWhatKit use kar sakte hain.

Important:

- WhatsApp Web login required
- Browser open ho sakta hai
- Internet required
- Spam automation mat karo

---

## Capstone Project Idea - Automation Dashboard

Features:

- Create folder
- Save note
- Send email
- Send SMS
- Send WhatsApp message

This project multiple concepts combine karta hai:

| Concept | Use |
|---|---|
| Functions | Separate features |
| OS module | Folder/file automation |
| File handling | Notes save |
| SMTP | Email |
| Twilio | SMS |
| PyWhatKit | WhatsApp |
| Credentials | Secure setup |

---

# Final Revision

| Day | Key Learning |
|---|---|
| Day 12 | Functions and scope |
| Day 14 | File handling and exceptions |
| Day 15 | Student record project |
| Day 16 | OOP and bank account project |
| Day 17 | Automation and capstone |

Happy Coding.
