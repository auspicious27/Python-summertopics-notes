# Python Sessions 3 to 6 - Complete Hinglish Notes

Functions, APIs, GUI Development, Automation, File Handling, Flask, Tkinter Projects, Turtle Game, and Desktop Applications

Language style: Proper Hinglish with simple English technical terms.

Goal: Is document ko padhkar learner easily samajh sake aur teacher har code line ko explain kar sake.

---

## Session Wise Index

| Session | Main Area | Topics |
|---|---|---|
| Session 3 | Functions, APIs, GUI | Functions, lists, dictionaries, sets, PyWhatKit, Twilio, Tkinter, calculator/dashboard |
| Session 4 | Automation, GUI, File Handling | Parameters, calculator, WhatsApp/SMS/email automation, TTS, speech recognition, Tkinter, file handling |
| Session 5 | File Handling, Flask, Tkinter | Advanced file handling, exception handling, OS module, Flask routes, scientific calculator |
| Session 6 | Turtle Game, Desktop Apps | To-do app, Turtle game, score, keyboard controls, PyInstaller, EXE creation |

---

# Session 3 - Python Functions, APIs and GUI Development

## Session 3 Learning Goal

Is session mein learner samjhega:

- Function kya hota hai
- Code reuse kaise hota hai
- List, dictionary, set ka practical use
- PyWhatKit se WhatsApp automation ka idea
- Twilio API se SMS ka concept
- API authentication kya hota hai
- Tkinter se basic GUI kaise banta hai
- Calculator ko CLI se GUI mein kaise convert karte hain

---

## 1. Python Functions

Function ka simple meaning:

```text
Ek kaam ko ek naam de do, phir us kaam ko baar-baar call karo.
```

Real-life example:

TV remote ka power button. Button press karo, TV on/off hota hai. Aapko andar ka circuit baar-baar manually operate nahi karna padta.

Python function bhi aise hi hota hai.

## Example - Simple Function

```python
def greet():
    print("Welcome to Python Session 3")

greet()
```

## Output

```text
Welcome to Python Session 3
```

## Line-by-Line Explanation

| Line | Code | Hinglish Explanation |
|---|---|---|
| 1 | `def greet():` | `def` function define karne ka keyword hai. `greet` function ka naam hai. |
| 2 | `print(...)` | Function ke andar ka kaam. Jab function call hoga tab ye line chalegi. |
| 4 | `greet()` | Function call ho raha hai. Is line ke bina function run nahi hota. |

## Why Function?

Without function:

```python
print("Welcome Rahul")
print("Welcome Priya")
print("Welcome Aman")
```

With function:

```python
def welcome(name):
    print(f"Welcome {name}")

welcome("Rahul")
welcome("Priya")
welcome("Aman")
```

Function code ko reusable banata hai.

---

## 2. Code Reusability and Function-Based Programming

Code reusability ka matlab hai same logic ko baar-baar copy-paste karne ke bajay function bana kar use karna.

## Example - Discount Calculator

```python
def calculate_discount(price, discount_percent):
    discount = price * discount_percent / 100
    final_price = price - discount
    return final_price

print(calculate_discount(1000, 10))
print(calculate_discount(2000, 20))
```

## Output

```text
900.0
1600.0
```

## Line-by-Line Explanation

| Line | Code | Hinglish Explanation |
|---|---|---|
| 1 | `def calculate_discount(price, discount_percent):` | Function do inputs leta hai: price and discount percentage. |
| 2 | `discount = price * discount_percent / 100` | Discount amount calculate ho raha hai. |
| 3 | `final_price = price - discount` | Original price se discount minus ho raha hai. |
| 4 | `return final_price` | Final value function ke bahar bheji ja rahi hai. |
| 6 | `calculate_discount(1000, 10)` | Price 1000 aur discount 10 percent diya gaya. |
| 7 | `calculate_discount(2000, 20)` | Same function different values ke saath reuse hua. |

Real-world use:

Shopping app, billing software, coupon system.

---

## 3. Lists in Python

List multiple values ka collection hoti hai.

## Example - Student Names

```python
students = ["Rahul", "Priya", "Aman"]

students.append("Neha")

for student in students:
    print(student)
```

## Output

```text
Rahul
Priya
Aman
Neha
```

## Explanation

| Code | Hinglish Explanation |
|---|---|
| `students = [...]` | Students ki list create hui. |
| `append("Neha")` | List ke end mein Neha add hui. |
| `for student in students:` | Har student one by one loop mein aayega. |
| `print(student)` | Current student print hoga. |

Real-world use:

Attendance, shopping cart, task list, message list.

---

## 4. Dictionaries in Python

Dictionary key-value pair data store karti hai.

## Example - Student Profile

```python
student = {
    "name": "Rahul",
    "course": "Python",
    "marks": 85
}

print(student["name"])
print(student["course"])
```

## Output

```text
Rahul
Python
```

## Explanation

| Code | Hinglish Explanation |
|---|---|
| `{}` | Dictionary create karta hai. |
| `"name": "Rahul"` | `name` key ki value Rahul hai. |
| `student["name"]` | Name key ki value access ho rahi hai. |
| `student["course"]` | Course key ki value access ho rahi hai. |

Real-world use:

User profile, API response, product details, student record.

---

## 5. Sets in Python

Set unique values store karta hai. Duplicate remove ho jaate hain.

## Example - Unique Skills

```python
skills = {"Python", "Linux", "Python", "AWS"}

print(skills)
```

## Output

```text
{'Python', 'Linux', 'AWS'}
```

Note: Output order change ho sakta hai.

## Explanation

`Python` duplicate tha, but set ne duplicate remove kar diya.

Real-world use:

Unique users, unique emails, unique skills, common students.

---

## 6. PyWhatKit Library and Automated WhatsApp Messaging

PyWhatKit Python library hai jo WhatsApp message automation, YouTube search, Google search jaise tasks mein help karti hai.

Install:

```bash
pip install pywhatkit
```

## Example - WhatsApp Message

```python
import pywhatkit

phone_number = "+911234567890"
message = "Hello, this is an automated message from Python."

pywhatkit.sendwhatmsg_instantly(phone_number, message)
```

## Code Explanation

| Line | Code | Hinglish Explanation |
|---|---|---|
| 1 | `import pywhatkit` | PyWhatKit library import ho rahi hai. |
| 3 | `phone_number = ...` | Receiver ka phone number store hua. Country code zaroori hai. |
| 4 | `message = ...` | Jo message send karna hai wo variable mein store hua. |
| 6 | `sendwhatmsg_instantly(...)` | WhatsApp Web ke through message send karne ki attempt karta hai. |

Important:

- WhatsApp Web login hona chahiye.
- Browser open ho sakta hai.
- Internet required hai.
- Real automation mein user permission and privacy ka dhyan rakho.

---

## 7. Twilio API Integration and SMS Communication

Twilio SMS send karne ke liye API service provide karta hai.

Install:

```bash
pip install twilio
```

## Example - SMS Send

```python
from twilio.rest import Client

account_sid = "YOUR_ACCOUNT_SID"
auth_token = "YOUR_AUTH_TOKEN"

client = Client(account_sid, auth_token)

message = client.messages.create(
    body="Hello from Python and Twilio",
    from_="+1234567890",
    to="+911234567890"
)

print(message.sid)
```

## Line-by-Line Explanation

| Line | Code | Hinglish Explanation |
|---|---|---|
| 1 | `from twilio.rest import Client` | Twilio ka Client class import ho raha hai. |
| 3 | `account_sid` | Twilio account ka ID. |
| 4 | `auth_token` | Twilio authentication token. Secret hota hai. |
| 6 | `Client(...)` | Twilio client object create hota hai. |
| 8 | `client.messages.create(...)` | Twilio API ko request bhejkar SMS create/send karta hai. |
| 9 | `body=...` | SMS ka text message. |
| 10 | `from_=...` | Twilio sender number. |
| 11 | `to=...` | Receiver phone number. |
| 14 | `print(message.sid)` | Message ka unique ID print hota hai. |

Security:

Credentials code mein hardcode mat karo. Environment variables use karo.

---

## 8. API Authentication and Setup

API authentication ka matlab hai API ko prove karna ki aap authorized user ho.

Common authentication:

- API key
- Auth token
- Username/password
- OAuth token

Twilio example:

```python
client = Client(account_sid, auth_token)
```

Meaning:

Twilio check karta hai ki account SID and auth token valid hain ya nahi.

---

## 9. Tkinter Basics and GUI Development

Tkinter Python ka built-in GUI library hai.

GUI ka matlab:

```text
Graphical User Interface
```

Window, button, label, input box ye sab GUI widgets hain.

## Example - Basic Window

```python
import tkinter as tk

root = tk.Tk()
root.title("My First GUI")
root.geometry("300x200")

label = tk.Label(root, text="Welcome to Tkinter")
label.pack()

button = tk.Button(root, text="Click Me")
button.pack()

root.mainloop()
```

## Line-by-Line Explanation

| Line | Code | Hinglish Explanation |
|---|---|---|
| 1 | `import tkinter as tk` | Tkinter library import hui, short name `tk` diya. |
| 3 | `root = tk.Tk()` | Main application window create hui. |
| 4 | `root.title(...)` | Window ka title set hua. |
| 5 | `root.geometry("300x200")` | Window size width 300, height 200. |
| 7 | `tk.Label(...)` | Label widget create hua. |
| 8 | `label.pack()` | Label window mein show hua. |
| 10 | `tk.Button(...)` | Button widget create hua. |
| 11 | `button.pack()` | Button window mein show hua. |
| 13 | `root.mainloop()` | GUI event loop start hua. Window open rahegi. |

---

## 10. Calculator Project Conversion - CLI to GUI

## CLI Calculator Logic

```python
def add(a, b):
    return a + b

print(add(10, 5))
```

GUI mein same function button click par run hoga.

## Simple GUI Calculator

```python
import tkinter as tk

def add_numbers():
    num1 = int(entry1.get())
    num2 = int(entry2.get())
    result = num1 + num2
    result_label.config(text=f"Result: {result}")

root = tk.Tk()
root.title("Simple Calculator")

entry1 = tk.Entry(root)
entry1.pack()

entry2 = tk.Entry(root)
entry2.pack()

add_button = tk.Button(root, text="Add", command=add_numbers)
add_button.pack()

result_label = tk.Label(root, text="Result:")
result_label.pack()

root.mainloop()
```

## Code Explanation

| Code | Hinglish Explanation |
|---|---|
| `entry1.get()` | First input box se value leta hai. |
| `int(...)` | Text ko number mein convert karta hai. |
| `result = num1 + num2` | Addition hoti hai. |
| `result_label.config(...)` | Label ka text update hota hai. |
| `command=add_numbers` | Button click par function run hota hai. |

---

# Session 4 - Python Automation, GUI and File Handling

## Session 4 Learning Goal

Is session mein learner samjhega:

- Function parameters and return
- Calculator application
- WhatsApp/SMS/email automation
- Text-to-speech
- Speech recognition
- Tkinter GUI widgets
- File handling
- Secret note app

---

## 1. Function Parameters and Return Statements

Parameter function definition mein hota hai. Argument function call ke time actual value hoti hai.

```python
def multiply(a, b):
    return a * b

answer = multiply(4, 5)
print(answer)
```

Output:

```text
20
```

Explanation:

| Code | Hinglish Explanation |
|---|---|
| `a, b` | Parameters hain. |
| `return a * b` | Multiplication ka result bahar bhejta hai. |
| `multiply(4, 5)` | 4 and 5 arguments hain. |
| `answer = ...` | Return value answer mein store hui. |

---

## 2. Email Automation

Python se email send karne ke liye `smtplib` use kar sakte hain.

## Example

```python
import smtplib

sender = "your_email@gmail.com"
password = "your_app_password"
receiver = "receiver@gmail.com"

message = "Subject: Test Email\n\nHello, this email is sent using Python."

server = smtplib.SMTP("smtp.gmail.com", 587)
server.starttls()
server.login(sender, password)
server.sendmail(sender, receiver, message)
server.quit()

print("Email sent successfully")
```

## Explanation

| Line | Code | Hinglish Explanation |
|---|---|---|
| 1 | `import smtplib` | Email sending library import hoti hai. |
| 3-5 | Variables | Sender, password, receiver details store hote hain. |
| 7 | `message` | Email subject and body. |
| 9 | `SMTP(...)` | Gmail SMTP server connect hota hai. |
| 10 | `starttls()` | Secure connection start hota hai. |
| 11 | `login(...)` | Email account login hota hai. |
| 12 | `sendmail(...)` | Email send hoti hai. |
| 13 | `quit()` | Server connection close hota hai. |

Security:

Real password code mein mat likho. App password/environment variable use karo.

---

## 3. PyTTX3 Text-to-Speech

`pyttsx3` text ko voice mein convert karta hai.

Install:

```bash
pip install pyttsx3
```

## Example

```python
import pyttsx3

engine = pyttsx3.init()
engine.say("Hello, welcome to Python automation")
engine.runAndWait()
```

## Explanation

| Code | Hinglish Explanation |
|---|---|
| `pyttsx3.init()` | Speech engine start hota hai. |
| `engine.say(...)` | Jo text bolna hai wo set hota hai. |
| `engine.runAndWait()` | Voice output run hota hai. |

---

## 4. Voice Properties Control

```python
import pyttsx3

engine = pyttsx3.init()
engine.setProperty("rate", 140)
engine.setProperty("volume", 0.8)
engine.say("This is controlled voice output")
engine.runAndWait()
```

Explanation:

| Code | Meaning |
|---|---|
| `rate` | Voice speed |
| `volume` | Voice volume, 0.0 to 1.0 |

---

## 5. Speech Recognition Library

Speech recognition voice ko text mein convert karta hai.

Install:

```bash
pip install SpeechRecognition
pip install pyaudio
```

## Example

```python
import speech_recognition as sr

recognizer = sr.Recognizer()

with sr.Microphone() as source:
    print("Speak now...")
    audio = recognizer.listen(source)

text = recognizer.recognize_google(audio)
print("You said:", text)
```

## Explanation

| Code | Hinglish Explanation |
|---|---|
| `sr.Recognizer()` | Speech recognizer object create hota hai. |
| `sr.Microphone()` | Microphone input source banta hai. |
| `listen(source)` | Voice record hoti hai. |
| `recognize_google(audio)` | Google speech service se voice text mein convert hoti hai. |

Note:

Internet required ho sakta hai.

---

## 6. File Handling in Python

File handling ka matlab hai file read, write, append karna.

## Write File

```python
file = open("notes.txt", "w")
file.write("This is my first note.")
file.close()
```

Explanation:

| Code | Meaning |
|---|---|
| `open("notes.txt", "w")` | Write mode mein file open. Existing data overwrite ho sakta hai. |
| `write(...)` | Text file mein write karta hai. |
| `close()` | File close karta hai. |

## Read File

```python
file = open("notes.txt", "r")
content = file.read()
file.close()

print(content)
```

## Append File

```python
file = open("notes.txt", "a")
file.write("\nThis is another note.")
file.close()
```

---

## 7. Secret Note Application

## Code

```python
password = "1234"

user_password = input("Enter password: ")

if user_password == password:
    note = input("Enter your secret note: ")
    file = open("secret.txt", "w")
    file.write(note)
    file.close()
    print("Secret note saved.")
else:
    print("Wrong password.")
```

## Explanation

| Code | Hinglish Explanation |
|---|---|
| `password = "1234"` | Correct password set hua. |
| `input(...)` | User se password liya. |
| `if user_password == password:` | Password match check hua. |
| `note = input(...)` | Secret note input liya. |
| `open("secret.txt", "w")` | File write mode mein open hui. |
| `file.write(note)` | Note file mein save hua. |
| `else` | Wrong password par message. |

---

# Session 5 - Python File Handling, Flask and Tkinter Projects

## Session 5 Learning Goal

Is session mein learner samjhega:

- Advanced file handling
- File modes
- Exception handling
- OS module
- Flask basics
- API development basics
- Tkinter coordinate system
- Scientific calculator enhancement

---

## 1. File Open Modes

| Mode | Meaning |
|---|---|
| `r` | Read mode |
| `w` | Write mode, old data overwrite |
| `a` | Append mode |
| `x` | Create new file, error if exists |

---

## 2. File Existence Checking with OS Module

```python
import os

if os.path.exists("data.txt"):
    print("File exists")
else:
    print("File does not exist")
```

Explanation:

| Code | Meaning |
|---|---|
| `import os` | OS module import hota hai. |
| `os.path.exists(...)` | File exist karti hai ya nahi check karta hai. |

---

## 3. Exception Handling

Exception handling errors ko handle karta hai taaki program crash na ho.

```python
try:
    file = open("missing.txt", "r")
    content = file.read()
    file.close()
    print(content)
except FileNotFoundError:
    print("File not found.")
finally:
    print("Program finished.")
```

Explanation:

| Block | Meaning |
|---|---|
| `try` | Risky code yahan likhte hain |
| `except` | Error aane par handle karta hai |
| `finally` | Error aaye ya na aaye, ye block run hota hai |

---

## 4. Flask Library Introduction

Flask Python ka lightweight web framework hai.

Install:

```bash
pip install flask
```

## Simple Flask App

```python
from flask import Flask

app = Flask(__name__)

@app.route("/")
def home():
    return "Welcome to Flask"

app.run(debug=True)
```

## Explanation

| Line | Code | Hinglish Explanation |
|---|---|---|
| 1 | `from flask import Flask` | Flask class import hoti hai. |
| 3 | `app = Flask(__name__)` | Flask app object create hota hai. |
| 5 | `@app.route("/")` | Home URL route define hota hai. |
| 6 | `def home():` | Route ke liye function. |
| 7 | `return ...` | Browser mein response show hota hai. |
| 9 | `app.run(debug=True)` | Flask server start hota hai. |

Run:

```bash
python app.py
```

Open:

```text
http://127.0.0.1:5000/
```

---

## 5. API Development Basics

Flask se simple API bana sakte hain.

```python
from flask import Flask, jsonify

app = Flask(__name__)

@app.route("/api/student")
def student():
    data = {
        "name": "Rahul",
        "course": "Python"
    }
    return jsonify(data)

app.run(debug=True)
```

Output in browser:

```json
{
  "course": "Python",
  "name": "Rahul"
}
```

Explanation:

`jsonify()` Python dictionary ko JSON response mein convert karta hai.

---

## 6. Tkinter Scientific Calculator Enhancement

Math library use karke advanced calculations kar sakte hain.

```python
import math

print(math.sqrt(25))
print(math.pow(2, 3))
print(math.sin(0))
```

Output:

```text
5.0
8.0
0.0
```

Explanation:

| Function | Meaning |
|---|---|
| `sqrt()` | Square root |
| `pow()` | Power |
| `sin()` | Sine value |

---

# Session 6 - Python Turtle Game and Desktop Applications

## Session 6 Learning Goal

Is session mein learner samjhega:

- To-do list functions
- Turtle library
- Simple game development
- Player movement
- Food collection
- Score tracking
- Keyboard controls
- PyInstaller
- Python code ko EXE mein convert karna

---

## 1. To-Do List with Functions

```python
tasks = []

def add_task(task):
    tasks.append(task)
    print("Task added.")

def show_tasks():
    for index, task in enumerate(tasks, start=1):
        print(f"{index}. {task}")

def delete_task(task_number):
    if 1 <= task_number <= len(tasks):
        removed = tasks.pop(task_number - 1)
        print("Deleted:", removed)
    else:
        print("Invalid task number.")

add_task("Study Python")
add_task("Practice Turtle")
show_tasks()
delete_task(1)
show_tasks()
```

## Explanation

| Function | Meaning |
|---|---|
| `add_task()` | Task list mein task add karta hai |
| `show_tasks()` | Saare tasks print karta hai |
| `delete_task()` | Task number ke basis par delete karta hai |

Important:

Functions code ko organized banate hain.

---

## 2. Turtle Library Introduction

Turtle graphics drawing and simple games ke liye use hoti hai.

## Simple Turtle Code

```python
import turtle

screen = turtle.Screen()
screen.title("My Turtle Game")

player = turtle.Turtle()
player.shape("turtle")
player.color("blue")

player.forward(100)

screen.mainloop()
```

## Explanation

| Code | Hinglish Explanation |
|---|---|
| `import turtle` | Turtle library import hoti hai. |
| `turtle.Screen()` | Game/window screen create hoti hai. |
| `screen.title(...)` | Window title set hota hai. |
| `turtle.Turtle()` | Player turtle object create hota hai. |
| `shape("turtle")` | Player shape turtle set hota hai. |
| `color("blue")` | Player color blue hota hai. |
| `forward(100)` | Turtle 100 pixels aage move hota hai. |
| `mainloop()` | Window open rakhta hai. |

---

## 3. Keyboard Controls

```python
import turtle

screen = turtle.Screen()
player = turtle.Turtle()

def move_up():
    player.sety(player.ycor() + 20)

def move_down():
    player.sety(player.ycor() - 20)

screen.listen()
screen.onkey(move_up, "Up")
screen.onkey(move_down, "Down")

screen.mainloop()
```

## Explanation

| Code | Meaning |
|---|---|
| `player.ycor()` | Current Y coordinate |
| `sety(...)` | New Y coordinate set karta hai |
| `screen.listen()` | Keyboard input listen karta hai |
| `onkey(move_up, "Up")` | Up key press par move_up function chalega |

---

## 4. Food Collection and Score Tracking

```python
import turtle
import random

score = 0

screen = turtle.Screen()
player = turtle.Turtle()
food = turtle.Turtle()
food.shape("circle")
food.color("red")
food.penup()
food.goto(random.randint(-200, 200), random.randint(-200, 200))

score_writer = turtle.Turtle()
score_writer.hideturtle()
score_writer.penup()
score_writer.goto(-200, 200)
score_writer.write(f"Score: {score}")
```

Explanation:

| Code | Meaning |
|---|---|
| `random.randint(-200, 200)` | Random coordinate generate karta hai |
| `food.goto(...)` | Food random place par move hota hai |
| `score = 0` | Starting score |
| `score_writer.write(...)` | Score screen par show hota hai |

---

## 5. PyInstaller Introduction

PyInstaller Python code ko executable file mein convert karta hai.

Install:

```bash
pip install pyinstaller
```

Convert:

```bash
pyinstaller --onefile app.py
```

GUI app ke liye:

```bash
pyinstaller --onefile --windowed app.py
```

Output:

```text
dist/app.exe
```

Explanation:

| Command | Meaning |
|---|---|
| `--onefile` | Single EXE file banata hai |
| `--windowed` | Console window hide karta hai, GUI apps ke liye useful |

---

# Final Revision

| Topic | Key Point |
|---|---|
| Functions | Reusable code |
| Lists | Multiple values |
| Dictionaries | Key-value data |
| Sets | Unique values |
| PyWhatKit | WhatsApp automation |
| Twilio | SMS API |
| Tkinter | GUI apps |
| File Handling | Read/write/append |
| Flask | Web app/API |
| Turtle | Games/graphics |
| PyInstaller | Python to EXE |

Happy Coding.
