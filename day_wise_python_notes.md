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

# Deep Day-Wise Theory and Code Explanation

Is section mein har important day ka theory plus practical code flow detail mein diya gaya hai. Goal yeh hai ki learner code dekhkar yeh bata sake:

- Yeh code kis problem ko solve kar raha hai.
- Isme input kya hai.
- Processing kaise ho rahi hai.
- Output kya aayega.
- Har line ka role kya hai.

---

## Day 12 Deep Explanation - Functions in Python

Function ka main purpose code ko reusable banana hai. Agar same logic 5 jagah chahiye, toh 5 baar same code likhne ke bajay ek function bana do aur usko call kar lo.

Real-world use case:

| Situation | Function ka Use |
|---|---|
| Calculator | Add, subtract, multiply ke separate functions |
| Student app | Marks calculate karne ka function |
| Banking app | Deposit aur withdrawal ke functions |
| Automation | Email send karne ka function |

Practical code:

```python
def calculate_total(marks1, marks2, marks3):
    total = marks1 + marks2 + marks3
    return total

def calculate_percentage(total):
    percentage = total / 300 * 100
    return percentage

student_total = calculate_total(80, 75, 90)
student_percentage = calculate_percentage(student_total)

print("Total Marks:", student_total)
print("Percentage:", student_percentage)
```

Line-by-line explanation:

| Line | Code | Detailed Explanation |
|---|---|---|
| 1 | `def calculate_total(marks1, marks2, marks3):` | Function define ho raha hai. Is function ko 3 marks chahiye. Yeh marks parameters ke form mein receive honge. |
| 2 | `total = marks1 + marks2 + marks3` | Teeno marks add ho rahe hain. Result `total` variable mein store hota hai. |
| 3 | `return total` | Function total value ko caller ke paas wapas bhejta hai. |
| 5 | `def calculate_percentage(total):` | Second function define ho raha hai. Isko total marks chahiye. |
| 6 | `percentage = total / 300 * 100` | Total marks ko maximum marks 300 se divide karke 100 se multiply kiya ja raha hai. |
| 7 | `return percentage` | Percentage result function ke bahar return hota hai. |
| 9 | `student_total = calculate_total(80, 75, 90)` | First function call ho raha hai. 80, 75, 90 values parameters mein jaati hain. Return value `student_total` mein store hoti hai. |
| 10 | `student_percentage = calculate_percentage(student_total)` | Total ko percentage function mein pass kiya gaya. Return value `student_percentage` mein store hoti hai. |
| 12 | `print("Total Marks:", student_total)` | Total marks output mein show hote hain. |
| 13 | `print("Percentage:", student_percentage)` | Percentage output mein show hoti hai. |

Expected output:

```text
Total Marks: 245
Percentage: 81.66666666666667
```

Important concept:

Function ko directly print karna zaroori nahi hota. Better approach yeh hai ki function result return kare, phir hum us result ko print, save, email ya kisi aur calculation mein use kar sakein.

---

## Day 14 Deep Explanation - File Handling and Exception Handling

File handling ka use tab hota hai jab hume data permanently save karna ho. Normal variable program close hote hi delete ho jaata hai, lekin file mein data save rahta hai.

Exception handling ka use tab hota hai jab error aane ka chance ho. Example: file exist nahi karti, user wrong input deta hai, internet down hota hai, API fail hoti hai.

Practical code:

```python
try:
    file = open("student.txt", "w")
    file.write("Name: Aman\n")
    file.write("Course: Python\n")
    file.close()

    file = open("student.txt", "r")
    data = file.read()
    file.close()

    print(data)

except FileNotFoundError:
    print("File not found.")

except Exception as error:
    print("Something went wrong:", error)

finally:
    print("File operation completed.")
```

Line-by-line explanation:

| Line | Code | Detailed Explanation |
|---|---|---|
| 1 | `try:` | Risky code try block ke andar likha jaata hai. Agar error aaya, program crash nahi hoga, except block chalega. |
| 2 | `file = open("student.txt", "w")` | `student.txt` file write mode mein open hoti hai. Agar file exist nahi karti toh Python create kar dega. Agar exist karti hai toh old data overwrite ho sakta hai. |
| 3 | `file.write("Name: Aman\n")` | File mein first line write hoti hai. `\n` new line create karta hai. |
| 4 | `file.write("Course: Python\n")` | File mein second line write hoti hai. |
| 5 | `file.close()` | File close karna important hai, taaki data properly save ho aur resource free ho. |
| 7 | `file = open("student.txt", "r")` | Same file read mode mein open hoti hai. |
| 8 | `data = file.read()` | File ka pura content read hota hai aur `data` variable mein store hota hai. |
| 9 | `file.close()` | Read operation ke baad file close hoti hai. |
| 11 | `print(data)` | File ka content screen par print hota hai. |
| 13 | `except FileNotFoundError:` | Agar file read karte waqt file missing ho, toh yeh block run hota hai. |
| 14 | `print("File not found.")` | User-friendly error message show hota hai. |
| 16 | `except Exception as error:` | General error handler hai. Agar koi aur unexpected error aaye toh yeh catch karega. |
| 17 | `print("Something went wrong:", error)` | Actual error message ke saath output show hota hai. Debugging ke liye useful. |
| 19 | `finally:` | Finally block error aaye ya na aaye, hamesha run hota hai. Cleanup messages ke liye useful. |
| 20 | `print("File operation completed.")` | Final message batata hai ki file operation ka attempt complete ho gaya. |

Expected output:

```text
Name: Aman
Course: Python

File operation completed.
```

Better practice:

`with open(...) as file:` use karna better hota hai kyunki file automatically close ho jaati hai.

---

## Day 15 Deep Explanation - Student Record File System

Student Record File System ek practical mini project hai. Isme hum student data file mein save karte hain, read karte hain, search karte hain aur update/delete logic samajhte hain.

Real-world use case:

- Coaching institute student records.
- Attendance system.
- Basic CRM.
- School result storage.

Simple project code:

```python
def add_student():
    roll = input("Enter roll number: ")
    name = input("Enter student name: ")
    course = input("Enter course name: ")

    with open("students.txt", "a") as file:
        file.write(f"{roll},{name},{course}\n")

    print("Student record added.")

def show_students():
    try:
        with open("students.txt", "r") as file:
            records = file.readlines()

        if len(records) == 0:
            print("No records found.")
        else:
            for record in records:
                roll, name, course = record.strip().split(",")
                print(f"Roll: {roll}, Name: {name}, Course: {course}")

    except FileNotFoundError:
        print("No student file found.")

def search_student():
    search_roll = input("Enter roll number to search: ")
    found = False

    try:
        with open("students.txt", "r") as file:
            for record in file:
                roll, name, course = record.strip().split(",")

                if roll == search_roll:
                    print(f"Found: {name} is enrolled in {course}")
                    found = True
                    break

        if found == False:
            print("Student not found.")

    except FileNotFoundError:
        print("No student file found.")
```

Line-by-line explanation:

| Line | Code | Detailed Explanation |
|---|---|---|
| 1 | `def add_student():` | Student add karne ke liye function define hota hai. |
| 2 | `roll = input("Enter roll number: ")` | User se roll number input liya ja raha hai. File mein roll unique ID ki tarah kaam karega. |
| 3 | `name = input("Enter student name: ")` | Student ka naam input hota hai. |
| 4 | `course = input("Enter course name: ")` | Student ka course input hota hai. |
| 6 | `with open("students.txt", "a") as file:` | File append mode mein open hoti hai. Append mode old records ko delete nahi karta, new record end mein add karta hai. |
| 7 | `file.write(f"{roll},{name},{course}\n")` | Student data comma-separated format mein file mein save hota hai. Ek student ek line mein store hota hai. |
| 9 | `print("Student record added.")` | Confirmation message show hota hai. |
| 11 | `def show_students():` | Saare students show karne ke liye function define hota hai. |
| 12 | `try:` | File missing hone ka chance hai, isliye risky read code try mein rakha gaya. |
| 13 | `with open("students.txt", "r") as file:` | Student file read mode mein open hoti hai. |
| 14 | `records = file.readlines()` | File ki saari lines list ke form mein read hoti hain. |
| 16 | `if len(records) == 0:` | Check karta hai file empty hai ya nahi. |
| 17 | `print("No records found.")` | Empty file ke case mein message show hota hai. |
| 19 | `for record in records:` | Har student record par loop chalega. |
| 20 | `roll, name, course = record.strip().split(",")` | Line se newline remove hota hai, phir comma ke basis par roll, name, course alag variables mein split hote hain. |
| 21 | `print(f"Roll: {roll}, Name: {name}, Course: {course}")` | Student record readable format mein print hota hai. |
| 23 | `except FileNotFoundError:` | Agar file exist nahi karti, toh yeh block run hota hai. |
| 24 | `print("No student file found.")` | User ko clear message milta hai. |
| 26 | `def search_student():` | Student search karne ke liye function define hota hai. |
| 27 | `search_roll = input("Enter roll number to search: ")` | User jis roll number ko search karna chahta hai woh input hota hai. |
| 28 | `found = False` | Flag variable banaya. Starting mein assume karte hain student nahi mila. |
| 31 | `with open("students.txt", "r") as file:` | File read mode mein open hoti hai. |
| 32 | `for record in file:` | File ki har line directly loop mein read hoti hai. |
| 33 | `roll, name, course = record.strip().split(",")` | Current line ko parts mein convert kiya ja raha hai. |
| 35 | `if roll == search_roll:` | Current record ka roll user ke roll se compare hota hai. |
| 36 | `print(f"Found: {name} is enrolled in {course}")` | Match milne par student detail print hoti hai. |
| 37 | `found = True` | Flag update hota hai, matlab student mil gaya. |
| 38 | `break` | Student mil gaya, ab baaki records check karne ki zaroorat nahi. Loop stop. |
| 40 | `if found == False:` | Loop ke baad check hota hai ki student mila ya nahi. |
| 41 | `print("Student not found.")` | Agar flag abhi bhi False hai, toh not found message print hota hai. |
| 43 | `except FileNotFoundError:` | File missing case handle hota hai. |
| 44 | `print("No student file found.")` | Clear error message show hota hai. |

Expected file data:

```text
101,Aman,Python
102,Sara,Flask
103,Ravi,Automation
```

Important:

CSV-style data beginner projects ke liye easy hota hai, lekin real applications mein database use hota hai.

---

## Day 16 Deep Explanation - OOP and Bank Account System

OOP ka matlab Object-Oriented Programming. Isme hum real-world cheezon ko class aur object ke form mein model karte hain.

Bank Account example:

| Real World | Python OOP |
|---|---|
| Account blueprint | Class |
| Aman ka account | Object |
| Account holder name | Attribute |
| Deposit money | Method |
| Withdraw money | Method |

Project code:

```python
class BankAccount:
    def __init__(self, holder_name, balance):
        self.holder_name = holder_name
        self.balance = balance

    def deposit(self, amount):
        self.balance = self.balance + amount
        print("Amount deposited successfully.")

    def withdraw(self, amount):
        if amount <= self.balance:
            self.balance = self.balance - amount
            print("Withdrawal successful.")
        else:
            print("Insufficient balance.")

    def check_balance(self):
        print(f"{self.holder_name}, your balance is {self.balance}")

account1 = BankAccount("Aman", 5000)
account1.deposit(2000)
account1.withdraw(1000)
account1.check_balance()
```

Line-by-line explanation:

| Line | Code | Detailed Explanation |
|---|---|---|
| 1 | `class BankAccount:` | Class define ho rahi hai. Yeh bank account ka blueprint hai. |
| 2 | `def __init__(self, holder_name, balance):` | Constructor method hai. Jab object create hota hai, yeh automatically run hota hai. |
| 3 | `self.holder_name = holder_name` | Object ke andar holder name save hota hai. `self` current object ko represent karta hai. |
| 4 | `self.balance = balance` | Object ke andar balance save hota hai. Har account ka apna separate balance hoga. |
| 6 | `def deposit(self, amount):` | Deposit method define hota hai. Isko amount chahiye jo add karna hai. |
| 7 | `self.balance = self.balance + amount` | Current balance mein deposit amount add hota hai. |
| 8 | `print("Amount deposited successfully.")` | Confirmation message show hota hai. |
| 10 | `def withdraw(self, amount):` | Withdrawal method define hota hai. |
| 11 | `if amount <= self.balance:` | Check hota hai ki withdrawal amount available balance se kam ya equal hai ya nahi. |
| 12 | `self.balance = self.balance - amount` | Balance se amount minus hota hai. |
| 13 | `print("Withdrawal successful.")` | Successful withdrawal message show hota hai. |
| 14 | `else:` | Agar amount balance se zyada hai, toh else chalega. |
| 15 | `print("Insufficient balance.")` | User ko insufficient balance message milega. |
| 17 | `def check_balance(self):` | Balance check karne ka method define hota hai. |
| 18 | `print(f"{self.holder_name}, your balance is {self.balance}")` | Holder name aur current balance print hota hai. |
| 20 | `account1 = BankAccount("Aman", 5000)` | BankAccount class ka object create hota hai. Constructor ko name aur opening balance milta hai. |
| 21 | `account1.deposit(2000)` | Account mein 2000 deposit hota hai. Balance 5000 se 7000 ho jaata hai. |
| 22 | `account1.withdraw(1000)` | Account se 1000 withdraw hota hai. Balance 7000 se 6000 ho jaata hai. |
| 23 | `account1.check_balance()` | Final balance print hota hai. |

Expected output:

```text
Amount deposited successfully.
Withdrawal successful.
Aman, your balance is 6000
```

Important OOP point:

`self` ko simple words mein samjho: "jis object par method call ho raha hai, us object ka data." Agar `account1.deposit(2000)` call hua, toh `self` account1 ko refer karega.

---

## Day 17 Deep Explanation - Python Automation Capstone

Automation ka matlab repetitive kaam ko code se karwana. Example: folder create karna, files organize karna, email send karna, SMS bhejna, WhatsApp message bhejna.

Automation project ka safe flow:

| Step | Meaning |
|---|---|
| 1 | Required input lo |
| 2 | Validate karo |
| 3 | Action perform karo |
| 4 | Error handle karo |
| 5 | Success/failure message show karo |

Practical file automation code:

```python
import os

folder_name = input("Enter folder name: ").strip()

if folder_name == "":
    print("Folder name cannot be empty.")
else:
    if os.path.exists(folder_name):
        print("Folder already exists.")
    else:
        os.mkdir(folder_name)
        print("Folder created successfully.")
```

Line-by-line explanation:

| Line | Code | Detailed Explanation |
|---|---|---|
| 1 | `import os` | OS module import hota hai. Isse folder/file operations aur system related kaam kar sakte hain. |
| 3 | `folder_name = input("Enter folder name: ").strip()` | User se folder name liya ja raha hai. `strip()` extra spaces remove karta hai. |
| 5 | `if folder_name == "":` | Check hota hai ki user ne empty input toh nahi diya. |
| 6 | `print("Folder name cannot be empty.")` | Empty input ke liye clear message show hota hai. |
| 7 | `else:` | Agar folder name empty nahi hai, toh actual folder logic chalega. |
| 8 | `if os.path.exists(folder_name):` | Check karta hai ki folder/file already exist karta hai ya nahi. |
| 9 | `print("Folder already exists.")` | Agar folder pehle se hai, toh duplicate create nahi karte. |
| 10 | `else:` | Agar folder exist nahi karta, toh new folder create karenge. |
| 11 | `os.mkdir(folder_name)` | New folder create hota hai. |
| 12 | `print("Folder created successfully.")` | Success message show hota hai. |

Email automation structure:

```python
import os
import smtplib

sender_email = os.getenv("SENDER_EMAIL")
sender_password = os.getenv("SENDER_PASSWORD")
receiver_email = input("Receiver email: ")
message = input("Message: ")

with smtplib.SMTP("smtp.gmail.com", 587) as server:
    server.starttls()
    server.login(sender_email, sender_password)
    server.sendmail(sender_email, receiver_email, message)

print("Email sent successfully.")
```

Line-by-line explanation:

| Line | Code | Detailed Explanation |
|---|---|---|
| 1 | `import os` | Environment variables read karne ke liye OS module use hota hai. |
| 2 | `import smtplib` | SMTP library email send karne ke liye use hoti hai. |
| 4 | `sender_email = os.getenv("SENDER_EMAIL")` | Sender email environment variable se read hota hai. Isse email code mein hard-code nahi hota. |
| 5 | `sender_password = os.getenv("SENDER_PASSWORD")` | Password/app password secure tarike se environment variable se read hota hai. |
| 6 | `receiver_email = input("Receiver email: ")` | User se receiver ka email address liya jaata hai. |
| 7 | `message = input("Message: ")` | User se email ka message content liya jaata hai. |
| 9 | `with smtplib.SMTP("smtp.gmail.com", 587) as server:` | Gmail SMTP server se connection create hota hai. Port 587 TLS ke liye common hai. |
| 10 | `server.starttls()` | Connection secure banaya jaata hai. |
| 11 | `server.login(sender_email, sender_password)` | Sender email aur password ke saath login hota hai. |
| 12 | `server.sendmail(sender_email, receiver_email, message)` | Actual email send hoti hai. |
| 14 | `print("Email sent successfully.")` | Success message show hota hai. |

Important safety:

- Real password code mein mat likho.
- Gmail ke liye normal password ke bajay App Password use hota hai.
- API keys aur tokens ko GitHub par push mat karo.
- `.env` file ko `.gitignore` mein add karo.

Capstone explanation:

Automation dashboard mein menu-based program bana sakte ho:

```text
1. Create folder
2. Save note
3. Send email
4. Send SMS
5. Send WhatsApp
6. Exit
```

Har option ke liye separate function banao. Isse code clean rahega aur debugging easy hogi.

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
