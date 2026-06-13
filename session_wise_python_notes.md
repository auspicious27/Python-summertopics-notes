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

Simple English meaning:

A function is a named block of code that performs one specific task. Once we create a function, we can run it whenever we need by calling its name.

Hinglish meaning:

Function ek aisa code block hai jisko hum ek naam de dete hain. Jab bhi woh kaam karwana ho, bas function ka naam call kar do. Code dobara likhne ki zaroorat nahi padti.

Real-life example:

TV remote ka power button. Button press karo, TV on/off hota hai. Aapko andar ka circuit baar-baar manually operate nahi karna padta. Button ke andar logic already set hai.

Python function bhi aise hi hota hai. Function ke andar logic hota hai, aur function call karne par woh logic run hota hai.

---

## Function ka Basic Structure

```python
def function_name():
    code_to_run
```

Syntax breakdown:

| Part | Meaning |
|---|---|
| `def` | Python keyword. Isse Python ko pata chalta hai ki hum function define kar rahe hain. |
| `function_name` | Function ka naam. Naam meaningful hona chahiye, jaise `greet`, `add_numbers`, `send_email`. |
| `()` | Parentheses. Iske andar inputs/parameters aa sakte hain. Agar input nahi chahiye toh empty parentheses rahenge. |
| `:` | Colon. Yeh batata hai ki function ka block ab start ho raha hai. |
| Indented code | Function ke andar ka code. Usually 4 spaces indentation hoti hai. |

Important:

- Function define karne se function run nahi hota.
- Function run karne ke liye function ko call karna padta hai.
- Function call ka syntax hota hai: `function_name()`.

---

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
| 1 | `def greet():` | `def` keyword Python ko batata hai ki yahan ek function create ho raha hai. `greet` function ka naam hai. Parentheses empty hain, iska matlab yeh function user se koi input nahi le raha. Colon `:` ke baad function body start hoti hai. |
| 2 | `print("Welcome to Python Session 3")` | Yeh function ke andar ka actual kaam hai. Kyunki line 4 spaces indent mein hai, Python samajhta hai ki yeh line `greet` function ka part hai. Jab tak function call nahi hoga, yeh print execute nahi hoga. |
| 4 | `greet()` | Yeh function call hai. Yahin se function actually run hota hai. Python line 4 par `greet()` dekhta hai, phir upar function definition mein jaakar function ke andar wali line execute karta hai. |

Execution flow:

| Step | What Python Does |
|---|---|
| 1 | Python `def greet():` dekhta hai aur function ko memory mein store kar leta hai. |
| 2 | Python function ke andar wali line ko abhi run nahi karta. |
| 3 | Python `greet()` line par pahunchta hai. |
| 4 | Function call hota hai aur `print(...)` execute hota hai. |
| 5 | Output screen par show hota hai. |

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

Line-by-line explanation:

| Line | Code | Explanation |
|---|---|---|
| 1 | `def welcome(name):` | Function define hua. `name` parameter hai. Parameter ek temporary variable hota hai jo function call ke time value receive karta hai. |
| 2 | `print(f"Welcome {name}")` | f-string use ho rahi hai. `{name}` ki jagah actual name print hoga. |
| 4 | `welcome("Rahul")` | Function call hua. `"Rahul"` argument hai. Yeh value `name` parameter mein jaayegi. Output: `Welcome Rahul`. |
| 5 | `welcome("Priya")` | Same function dobara call hua, but argument alag hai. Is baar `name = "Priya"` hoga. |
| 6 | `welcome("Aman")` | Same function third time use hua. Code repeat nahi kiya, sirf function call repeat ki. |

Function code ko reusable banata hai. Agar welcome message change karna ho, toh sirf function ke andar ek line change karni padegi. Har call ko separately update nahi karna padega.

---

## Parameters and Arguments

Beginners ko yeh topic confusing lag sakta hai, isliye simple words mein samjho:

| Term | Meaning | Example |
|---|---|---|
| Parameter | Function definition ke andar variable | `def welcome(name):` mein `name` parameter hai |
| Argument | Function call ke time actual value | `welcome("Rahul")` mein `"Rahul"` argument hai |

Easy trick:

```text
Parameter receives.
Argument sends.
```

Example:

```python
def student_intro(name, course):
    print(f"My name is {name}")
    print(f"I am learning {course}")

student_intro("Aman", "Python")
```

Line-by-line explanation:

| Line | Code | Explanation |
|---|---|---|
| 1 | `def student_intro(name, course):` | Function two parameters leta hai: `name` and `course`. Matlab function ko run hone ke liye do values chahiye. |
| 2 | `print(f"My name is {name}")` | `name` parameter ki value print hoti hai. |
| 3 | `print(f"I am learning {course}")` | `course` parameter ki value print hoti hai. |
| 5 | `student_intro("Aman", "Python")` | `"Aman"` first argument hai, isliye `name` mein jaayega. `"Python"` second argument hai, isliye `course` mein jaayega. |

Output:

```text
My name is Aman
I am learning Python
```

Common mistake:

```python
student_intro("Aman")
```

Yeh error dega, kyunki function ko 2 arguments chahiye the but humne sirf 1 diya.

---

## Return Statement

`print()` aur `return` same nahi hote.

| Concept | Meaning |
|---|---|
| `print()` | Sirf screen par value show karta hai |
| `return` | Function ke result ko bahar bhejta hai taaki usse reuse kar sakein |

Example:

```python
def add_numbers(a, b):
    total = a + b
    return total

result = add_numbers(10, 20)
print("Answer:", result)
```

Line-by-line explanation:

| Line | Code | Explanation |
|---|---|---|
| 1 | `def add_numbers(a, b):` | Function define hua jo two numbers receive karega. |
| 2 | `total = a + b` | Dono numbers add hote hain aur result `total` variable mein store hota hai. |
| 3 | `return total` | Function result ko bahar bhej raha hai. Yeh result function call ki jagah replace ho jaata hai. |
| 5 | `result = add_numbers(10, 20)` | Function call hua. Return value `30` aayi aur `result` variable mein store ho gayi. |
| 6 | `print("Answer:", result)` | Stored result screen par print hota hai. |

Output:

```text
Answer: 30
```

Why return is useful:

- Result ko variable mein store kar sakte hain.
- Result ko doosre function mein pass kar sakte hain.
- Result ko file mein save kar sakte hain.
- Result ko GUI label par show kar sakte hain.
- Result ko API response mein bhej sakte hain.

---

## Function Naming Rules and Good Practice

Function ka naam clear hona chahiye. Naam dekhkar samajh aana chahiye ki function kya karta hai.

Good names:

```python
calculate_total()
send_email()
add_task()
show_students()
```

Bad names:

```python
abc()
x()
do()
thing()
```

Rules:

| Rule | Example |
|---|---|
| Function name number se start nahi ho sakta | `1add()` invalid |
| Spaces allowed nahi hain | `add number()` invalid |
| Snake case use karna best hai | `add_number()` valid |
| Meaningful name use karo | `calculate_bill()` better than `calc()` |

---

## Function Scope

Scope ka matlab variable kahan available hai.

```python
def demo():
    message = "Hello"
    print(message)

demo()
```

Here, `message` function ke andar create hua hai. Isliye usko local variable bolte hain.

Wrong example:

```python
def demo():
    message = "Hello"

demo()
print(message)
```

Yeh error dega because `message` function ke bahar available nahi hai.

Simple rule:

```text
Function ke andar bana variable usually function ke andar hi use hota hai.
```

---

## 2. Code Reusability and Function-Based Programming

Code reusability ka matlab hai same logic ko baar-baar copy-paste karne ke bajay function bana kar use karna.

Simple English:

Reusable code means writing logic once and using it many times.

Hinglish:

Ek baar logic likho, phir use baar-baar call karo. Isse code clean hota hai, error kam hote hain, aur changes easy hote hain.

Real-world example:

Maan lo ek billing software hai. Har product par discount calculate karna hai. Agar discount formula 20 jagah copy-paste kiya, aur baad mein formula change ho gaya, toh 20 jagah update karna padega. Function use karoge toh sirf ek jagah update karna padega.

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

Detailed concept explanation:

| Concept | In This Code |
|---|---|
| Function name | `calculate_discount` |
| Parameters | `price`, `discount_percent` |
| Arguments in first call | `1000`, `10` |
| Arguments in second call | `2000`, `20` |
| Processing | Discount calculate karna |
| Return value | Final price after discount |

Step-by-step dry run for first call:

```python
print(calculate_discount(1000, 10))
```

| Step | Value |
|---|---|
| `price` | `1000` |
| `discount_percent` | `10` |
| `discount` | `1000 * 10 / 100 = 100.0` |
| `final_price` | `1000 - 100.0 = 900.0` |
| Returned value | `900.0` |
| Printed output | `900.0` |

Step-by-step dry run for second call:

```python
print(calculate_discount(2000, 20))
```

| Step | Value |
|---|---|
| `price` | `2000` |
| `discount_percent` | `20` |
| `discount` | `2000 * 20 / 100 = 400.0` |
| `final_price` | `2000 - 400.0 = 1600.0` |
| Returned value | `1600.0` |
| Printed output | `1600.0` |

Why this is better than copy-paste:

| Without Function | With Function |
|---|---|
| Same formula baar-baar likhna padta hai | Formula ek hi jagah hota hai |
| Mistake hone ka chance zyada | Mistake fix karna easy |
| Code long ho jaata hai | Code short aur clean hota hai |
| Reuse difficult | Reuse simple |

---

## Function-Based Programming Approach

Function-based programming ka matlab program ko small-small functions mein divide karna.

Example: Calculator project ko aise divide kar sakte hain:

| Function | Work |
|---|---|
| `add(a, b)` | Addition |
| `subtract(a, b)` | Subtraction |
| `multiply(a, b)` | Multiplication |
| `divide(a, b)` | Division |
| `show_menu()` | User ko options dikhana |
| `main()` | Program ka main flow control karna |

Mini example:

```python
def add(a, b):
    return a + b

def subtract(a, b):
    return a - b

def main():
    num1 = 10
    num2 = 5
    print("Addition:", add(num1, num2))
    print("Subtraction:", subtract(num1, num2))

main()
```

Line-by-line explanation:

| Line | Code | Explanation |
|---|---|---|
| 1 | `def add(a, b):` | Addition ke liye separate function banaya. Yeh two numbers lega. |
| 2 | `return a + b` | Dono numbers add karke result return karega. |
| 4 | `def subtract(a, b):` | Subtraction ke liye separate function banaya. |
| 5 | `return a - b` | First number se second number minus karke result return karega. |
| 7 | `def main():` | Main function program ka controller hai. Iske andar program ka flow rakha gaya. |
| 8 | `num1 = 10` | First number store kiya. |
| 9 | `num2 = 5` | Second number store kiya. |
| 10 | `print("Addition:", add(num1, num2))` | `add` function call hua, result print hua. |
| 11 | `print("Subtraction:", subtract(num1, num2))` | `subtract` function call hua, result print hua. |
| 13 | `main()` | Program start karne ke liye main function call kiya. |

Output:

```text
Addition: 15
Subtraction: 5
```

Beginner tip:

Jab bhi project bada ho raha ho, apne aap se pucho:

```text
Kya is kaam ko ek separate function bana sakta hoon?
```

Agar answer yes hai, toh function bana do. Code easier to explain and easier to debug ho jaata hai.

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

# Deep Theory and Full Code Walkthrough

Is section ka purpose yeh hai ki learner sirf code copy na kare, balki yeh bhi samjhe ki code ka flow kaise chal raha hai. Har program ko samajhne ka simple formula hai:

| Step | Meaning |
|---|---|
| Input | User se ya program ke andar se data lena |
| Process | Data par logic apply karna |
| Output | Final result screen, file, message, API ya GUI par dikhana |

Example: Calculator app mein numbers input hote hain, addition/subtraction process hota hai, aur result output hota hai.

---

## 1. Functions - Theory with Practical Understanding

Function ek reusable block hota hai. Agar ek kaam baar-baar karna hai, toh us code ko function ke andar rakh do. Isse code clean, short aur easy to maintain ho jaata hai.

Real-world use case:

- Login system mein password check karne ke liye function.
- Billing app mein discount calculate karne ke liye function.
- GUI calculator mein har button ke action ke liye function.
- Automation project mein email bhejne ke liye function.

Practical code:

```python
def calculate_discount(price, discount_percent):
    discount_amount = price * discount_percent / 100
    final_price = price - discount_amount
    return final_price

amount = calculate_discount(1000, 10)
print("Final amount:", amount)
```

Line-by-line explanation:

| Line | Code | Detailed Explanation |
|---|---|---|
| 1 | `def calculate_discount(price, discount_percent):` | `def` keyword function banane ke liye use hota hai. `calculate_discount` function ka naam hai. `price` aur `discount_percent` parameters hain, matlab function ko kaam karne ke liye yeh values chahiye. Colon batata hai ki ab function ka block start hoga. |
| 2 | `discount_amount = price * discount_percent / 100` | Yeh line discount ki amount calculate karti hai. Agar price 1000 hai aur discount 10 hai, toh formula hoga `1000 * 10 / 100`, result 100 aayega. |
| 3 | `final_price = price - discount_amount` | Original price me se discount amount minus hota hai. Example: `1000 - 100 = 900`. |
| 4 | `return final_price` | `return` function se result bahar bhejta hai. Print karne ke bajay return karna better hota hai kyunki result ko baad mein kisi aur calculation mein use kar sakte hain. |
| 6 | `amount = calculate_discount(1000, 10)` | Function call ho raha hai. `1000` price banega aur `10` discount_percent banega. Function jo return karega woh `amount` variable mein store hoga. |
| 7 | `print("Final amount:", amount)` | Final result screen par print hota hai. Output hoga: `Final amount: 900.0`. |

Important point:

Function ke andar jo variables bante hain, woh normally function ke bahar direct available nahi hote. Isko local scope bolte hain.

---

## 2. Lists, Dictionaries and Sets - Practical Data Handling

List multiple values store karne ke liye use hoti hai. Dictionary key-value data ke liye use hoti hai. Set unique values ke liye use hota hai.

Real-world use case:

| Data Type | Real Example |
|---|---|
| List | To-do tasks, shopping items, student names |
| Dictionary | Student details, product details, user profile |
| Set | Unique email IDs, unique course names, duplicate-free tags |

Practical code:

```python
students = [
    {"name": "Aman", "marks": 85},
    {"name": "Sara", "marks": 92},
    {"name": "Ravi", "marks": 85}
]

unique_marks = set()

for student in students:
    print(student["name"], "scored", student["marks"])
    unique_marks.add(student["marks"])

print("Unique marks:", unique_marks)
```

Line-by-line explanation:

| Line | Code | Detailed Explanation |
|---|---|---|
| 1 | `students = [` | Ek list start ho rahi hai. Is list ke andar multiple students ka data store hoga. |
| 2 | `{"name": "Aman", "marks": 85},` | Yeh ek dictionary hai. `name` key ke andar student ka naam hai aur `marks` key ke andar marks hain. |
| 3 | `{"name": "Sara", "marks": 92},` | Second student ka data same structure mein store hai. Same keys use karna good practice hai. |
| 4 | `{"name": "Ravi", "marks": 85}` | Third student ka data. Ravi ke marks Aman jaise same hain, isliye set mein duplicate remove ho jayega. |
| 7 | `unique_marks = set()` | Empty set banaya. Isme sirf unique marks store honge. |
| 9 | `for student in students:` | Loop list ke har dictionary item par chalega. Har round mein ek student ka data `student` variable mein aayega. |
| 10 | `print(student["name"], "scored", student["marks"])` | Dictionary se `name` aur `marks` access ho rahe hain. Output readable sentence ke form mein print hota hai. |
| 11 | `unique_marks.add(student["marks"])` | Current student ke marks set mein add ho rahe hain. Agar marks already present hain, set duplicate add nahi karega. |
| 13 | `print("Unique marks:", unique_marks)` | Final unique marks print honge. Example output: `{92, 85}`. |

---

## 3. Twilio SMS API - Theory and Full Practical Flow

API ka matlab hota hai ek application ka doosri service se baat karna. Twilio ek external service hai jisse Python code SMS bhej sakta hai.

SMS bhejne ka flow:

| Step | What Happens |
|---|---|
| 1 | Twilio account create karo |
| 2 | Account SID aur Auth Token lo |
| 3 | Twilio phone number lo |
| 4 | Python package install karo |
| 5 | Code se SMS send karo |

Install:

```bash
pip install twilio
```

Practical code:

```python
from twilio.rest import Client

account_sid = "YOUR_ACCOUNT_SID"
auth_token = "YOUR_AUTH_TOKEN"

client = Client(account_sid, auth_token)

message = client.messages.create(
    body="Hello, this is a test SMS from Python.",
    from_="+1234567890",
    to="+919999999999"
)

print("Message SID:", message.sid)
```

Line-by-line explanation:

| Line | Code | Detailed Explanation |
|---|---|---|
| 1 | `from twilio.rest import Client` | Twilio library se `Client` class import ho rahi hai. Client Twilio API ke saath connection create karta hai. |
| 3 | `account_sid = "YOUR_ACCOUNT_SID"` | Account SID Twilio account ka unique ID hota hai. Isse Twilio ko pata chalta hai ki request kis account se aa rahi hai. |
| 4 | `auth_token = "YOUR_AUTH_TOKEN"` | Auth token password jaisa secret hota hai. Isko public GitHub par kabhi hard-code nahi karna chahiye. |
| 6 | `client = Client(account_sid, auth_token)` | SID aur token ke saath Twilio client object ban raha hai. Ab isi object se SMS send karenge. |
| 8 | `message = client.messages.create(` | Twilio ko SMS create/send karne ki request bheji ja rahi hai. Jo response milega woh `message` variable mein store hoga. |
| 9 | `body="Hello, this is a test SMS from Python.",` | SMS ka actual text content hai. User ke phone par yahi message dikhega. |
| 10 | `from_="+1234567890",` | Sender number hai. Python mein `from` keyword reserved hai, isliye Twilio parameter ka naam `from_` hota hai. |
| 11 | `to="+919999999999"` | Receiver phone number hai. Country code ke saath number likhna zaroori hai. |
| 14 | `print("Message SID:", message.sid)` | Agar SMS request successful hui, toh Twilio ek message SID deta hai. Yeh tracking ID ki tarah hota hai. |

Security note:

Real project mein credentials environment variables se lo:

```python
import os

account_sid = os.getenv("TWILIO_ACCOUNT_SID")
auth_token = os.getenv("TWILIO_AUTH_TOKEN")
```

Isse secret values code mein directly nahi dikhti.

---

## 4. Tkinter GUI - Theory and Calculator Flow

Tkinter Python ki built-in GUI library hai. GUI ka matlab graphical user interface, jahan user buttons, labels aur input boxes ke through program use karta hai.

GUI app ka basic flow:

| Part | Meaning |
|---|---|
| Window | Main app screen |
| Label | Text show karne ke liye |
| Entry | User input lene ke liye |
| Button | Click action ke liye |
| Function | Button click par logic run karne ke liye |

Practical code:

```python
import tkinter as tk

def add_numbers():
    num1 = float(entry1.get())
    num2 = float(entry2.get())
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

Line-by-line explanation:

| Line | Code | Detailed Explanation |
|---|---|---|
| 1 | `import tkinter as tk` | Tkinter library import hoti hai. `as tk` short name hai, taaki baar-baar `tkinter` na likhna pade. |
| 3 | `def add_numbers():` | Button click hone par yeh function run hoga. Function ke andar calculator ka logic hai. |
| 4 | `num1 = float(entry1.get())` | `entry1.get()` first input box ka text read karta hai. `float()` us text ko number mein convert karta hai. |
| 5 | `num2 = float(entry2.get())` | Second input box se value read hoti hai aur number mein convert hoti hai. |
| 6 | `result = num1 + num2` | Dono numbers ka addition hota hai. |
| 7 | `result_label.config(text=f"Result: {result}")` | Label ka text update hota hai. f-string result ko readable format mein show karta hai. |
| 9 | `root = tk.Tk()` | Main window create hoti hai. Har Tkinter app ka ek root window hota hai. |
| 10 | `root.title("Simple Calculator")` | Window ke top bar mein title set hota hai. |
| 12 | `entry1 = tk.Entry(root)` | Pehla input box create hota hai. `root` ka matlab yeh widget main window ke andar dikhega. |
| 13 | `entry1.pack()` | `pack()` widget ko window par place karta hai. Agar pack nahi karenge toh widget dikhega nahi. |
| 15 | `entry2 = tk.Entry(root)` | Dusra input box create hota hai. |
| 16 | `entry2.pack()` | Dusra input box window par show hota hai. |
| 18 | `add_button = tk.Button(root, text="Add", command=add_numbers)` | Button create hota hai. Button ka text `Add` hai. Click hone par `add_numbers` function run hoga. |
| 19 | `add_button.pack()` | Button screen par place hota hai. |
| 21 | `result_label = tk.Label(root, text="Result:")` | Result show karne ke liye label create hota hai. |
| 22 | `result_label.pack()` | Label window par show hota hai. |
| 24 | `root.mainloop()` | App continuously run hota hai. Yeh line window ko open rakhti hai aur user clicks handle karti hai. |

Common error:

Agar user input box mein text daal de, jaise `abc`, toh `float("abc")` error dega. Real app mein `try-except` add karna chahiye.

---

## 5. File Handling - Theory and Secret Note Practical

File handling ka matlab Python se files read, write aur append karna. Yeh tab useful hota hai jab data program close hone ke baad bhi save rakhna ho.

File modes:

| Mode | Meaning |
|---|---|
| `r` | Read mode, file existing honi chahiye |
| `w` | Write mode, old data overwrite ho sakta hai |
| `a` | Append mode, old data ke end mein new data add hota hai |
| `x` | Create mode, file already exist hui toh error |

Secret note app code:

```python
password = input("Create password: ")
note = input("Write your secret note: ")

with open("secret_note.txt", "w") as file:
    file.write(password + "\n")
    file.write(note)

check_password = input("Enter password to read note: ")

with open("secret_note.txt", "r") as file:
    saved_password = file.readline().strip()
    saved_note = file.read()

if check_password == saved_password:
    print("Your note:", saved_note)
else:
    print("Wrong password.")
```

Line-by-line explanation:

| Line | Code | Detailed Explanation |
|---|---|---|
| 1 | `password = input("Create password: ")` | User se password liya ja raha hai. `input()` hamesha string return karta hai. |
| 2 | `note = input("Write your secret note: ")` | User se secret note liya ja raha hai. Yeh note file mein save hoga. |
| 4 | `with open("secret_note.txt", "w") as file:` | File write mode mein open ho rahi hai. `with` ka benefit yeh hai ki kaam complete hone ke baad file automatically close ho jaati hai. |
| 5 | `file.write(password + "\n")` | Password file ki first line mein save hota hai. `\n` new line add karta hai, taaki note next line se start ho. |
| 6 | `file.write(note)` | User ka note file mein write hota hai. |
| 8 | `check_password = input("Enter password to read note: ")` | Note read karne se pehle user se password dobara pucha ja raha hai. |
| 10 | `with open("secret_note.txt", "r") as file:` | Same file read mode mein open ho rahi hai. |
| 11 | `saved_password = file.readline().strip()` | `readline()` sirf first line read karta hai. `strip()` extra newline/spaces hata deta hai. |
| 12 | `saved_note = file.read()` | Remaining file content read hota hai, jo actual note hai. |
| 14 | `if check_password == saved_password:` | User ka entered password saved password se compare hota hai. |
| 15 | `print("Your note:", saved_note)` | Password sahi hua toh note show hota hai. |
| 16 | `else:` | Agar password match nahi hua toh else block chalega. |
| 17 | `print("Wrong password.")` | Wrong password message show hota hai. |

Important:

Yeh beginner-level logic hai. Real security ke liye password ko plain text mein save nahi karte, hashing use karte hain.

---

## 6. Flask - Theory and Web Route Explanation

Flask Python ka lightweight web framework hai. Isse browser mein web page ya API response show kar sakte hain.

Flask app flow:

| Step | Meaning |
|---|---|
| 1 | Flask import karo |
| 2 | App object create karo |
| 3 | Route define karo |
| 4 | Function response return kare |
| 5 | Server run karo |

Practical code:

```python
from flask import Flask

app = Flask(__name__)

@app.route("/")
def home():
    return "Welcome to my Flask app"

@app.route("/about")
def about():
    return "This page explains the project."

if __name__ == "__main__":
    app.run(debug=True)
```

Line-by-line explanation:

| Line | Code | Detailed Explanation |
|---|---|---|
| 1 | `from flask import Flask` | Flask class import hoti hai. Isi se web application object banega. |
| 3 | `app = Flask(__name__)` | Flask app object create hota hai. `__name__` Python ko current file ka context batata hai. |
| 5 | `@app.route("/")` | Route decorator hai. Jab browser root URL `/` open karega, neeche wala function run hoga. |
| 6 | `def home():` | Home route ka function. Function ka naam kuch bhi ho sakta hai, lekin unique hona chahiye. |
| 7 | `return "Welcome to my Flask app"` | Browser ko response return hota hai. Yeh text page par dikhega. |
| 9 | `@app.route("/about")` | `/about` URL ke liye route define hota hai. |
| 10 | `def about():` | About page ka function hai. |
| 11 | `return "This page explains the project."` | About route ka response browser mein show hota hai. |
| 13 | `if __name__ == "__main__":` | Yeh check karta hai ki file directly run ho rahi hai ya import ho rahi hai. Direct run hone par server start hoga. |
| 14 | `app.run(debug=True)` | Flask development server start hota hai. `debug=True` development ke time helpful errors show karta hai. |

Run:

```bash
python app.py
```

Open:

```text
http://127.0.0.1:5000/
http://127.0.0.1:5000/about
```

---

## 7. Turtle Game - Theory and Keyboard Movement

Turtle beginner-friendly graphics library hai. Isme screen, player, movement aur keyboard event handle kar sakte hain.

Game flow:

| Part | Meaning |
|---|---|
| Screen | Game window |
| Player turtle | Moving object |
| Food turtle | Collectible item |
| Score | Points tracking |
| Keyboard event | User control |

Keyboard movement code:

```python
import turtle

screen = turtle.Screen()
player = turtle.Turtle()

def move_up():
    y = player.ycor()
    player.sety(y + 20)

screen.listen()
screen.onkey(move_up, "Up")

screen.mainloop()
```

Line-by-line explanation:

| Line | Code | Detailed Explanation |
|---|---|---|
| 1 | `import turtle` | Turtle library import hoti hai. Isse graphics window aur turtle object bana sakte hain. |
| 3 | `screen = turtle.Screen()` | Game window create hoti hai. Keyboard events isi screen par listen honge. |
| 4 | `player = turtle.Turtle()` | Player object create hota hai. Screen par arrow/turtle shape dikh sakti hai. |
| 6 | `def move_up():` | Function define hota hai jo player ko upar move karega. |
| 7 | `y = player.ycor()` | Player ka current y-coordinate read hota hai. Y-coordinate vertical position batata hai. |
| 8 | `player.sety(y + 20)` | Player ki y-position 20 pixels badh jaati hai, isliye player upar move hota hai. |
| 10 | `screen.listen()` | Screen keyboard input listen karna start karti hai. Iske bina key press work nahi karega. |
| 11 | `screen.onkey(move_up, "Up")` | Jab user keyboard ka Up arrow press karega, `move_up` function run hoga. |
| 13 | `screen.mainloop()` | Window open rakhta hai aur events handle karta hai. |

Practice idea:

Isi pattern se `move_down`, `move_left`, `move_right` functions bana sakte ho.

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
