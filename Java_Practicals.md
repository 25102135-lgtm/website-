# Java Practical: All Experiment Codes

A comprehensive collection of all Java Practical Experiments and Exercises, covering Core Java (OOP, Inheritance, Exception Handling), Web Technologies (HTML, CSS, JavaScript), Servlets & JSP with JDBC, and React.

---

## Table of Contents

1. [Experiment 1: Class and Objects](#experiment-1-class-and-objects)
   - [Core Experiment: Student & StudentDemo](#exp-1-student-and-studentdemo)
   - [Exercise 1: Student Details & GPA Calculation](#exp-1-exercise-1-student-details-and-gpa-calculation)
   - [Exercise 2: Bank Account System](#exp-1-exercise-2-bank-account-system)
2. [Experiment 2: Constructor & Method Overloading](#experiment-2-constructor--method-overloading)
   - [Core Experiment: Employee Overloaded Constructors](#exp-2-employee-overloaded-constructors)
   - [Exercise 1: Student Details with Copy Constructor](#exp-2-exercise-1-student-details-with-copy-constructor)
   - [Exercise 2: Computing Photo Book Bill (Overloaded Methods)](#exp-2-exercise-2-computing-photo-book-bill)
3. [Experiment 3: Inheritance & Exception Handling](#experiment-3-inheritance--exception-handling)
   - [Core Experiment A: SuperDemo (Inheritance with super)](#exp-3-superdemo)
   - [Core Experiment B: Inbuilt Exception Handling](#exp-3-inbuilt-exception-handling)
   - [Core Experiment C: Custom Exception (InvalidAgeException)](#exp-3-custom-exception)
   - [Exercise 1: Poem Inheritance (Couplet, Limerick, Haiku)](#exp-3-exercise-1-poem-inheritance)
   - [Exercise 2: Exception Handling in Constructors](#exp-3-exercise-2-exception-handling-in-constructors)
4. [Experiment 4: HTML, CSS & JavaScript](#experiment-4-html-css--javascript)
   - [Core Experiment: Static Website](#exp-4-static-website)
   - [Exercise 1: Random Quote Generator with Dynamic Colors](#exp-4-exercise-1-quote-generator)
   - [Exercise 2: Interactive To-Do List](#exp-4-exercise-2-to-do-list)
5. [Experiment 5: JavaScript Logic & Validation](#experiment-5-javascript-logic--validation)
   - [Core Experiment: Email Address Validation](#exp-5-email-address-validation)
   - [Exercise 1: Donut Subtotal Calculator](#exp-5-exercise-1-donut-subtotal-calculator)
   - [Exercise 2: Anagram Checker](#exp-5-exercise-2-anagram-checker)
6. [Experiment 6: Interactive Calculator & Algorithms](#experiment-6-interactive-calculator--algorithms)
   - [Core Experiment: Simple Arithmetic & Math Calculator](#exp-6-calculator)
   - [Exercise 1: FizzBuzz Implementation](#exp-6-exercise-1-fizzbuzz)
   - [Exercise 2: Prime Number Generator](#exp-6-exercise-2-prime-number-generator)
7. [Experiment 7: Java Servlets](#experiment-7-java-servlets)
   - [Core Experiment: FirstServlet (GenericServlet)](#exp-7-firstservlet)
   - [Exercise 1: Greet User via HttpServlet](#exp-7-exercise-1-greet-user)
   - [Exercise 2: Servlet Lifecycle Demonstration](#exp-7-exercise-2-servlet-lifecycle)
8. [Experiment 8: JSP, Servlets & JDBC](#experiment-8-jsp-servlets--jdbc)
   - [Core Experiment: User Login Authentication System](#exp-8-user-login-authentication)
   - [Exercise 1: Employee Phonebook Directory](#exp-8-exercise-1-employee-phonebook)
   - [Exercise 2: Student Registration System](#exp-8-exercise-2-student-registration-system)
9. [Experiment 9: JSP (JavaServer Pages)](#experiment-9-jsp-javaserver-pages)
   - [Core Experiment: Hello World JSP](#exp-9-hello-world-jsp)
   - [Exercise 1: Display Current Date & Time](#exp-9-exercise-1-date-and-time)
   - [Exercise 2: User Information Form & Response](#exp-9-exercise-2-user-information-form)
10. [Experiment 10: React Frontend](#experiment-10-react-frontend)
    - [Core Experiment: React State Clicker](#exp-10-react-state-clicker)
    - [Exercise 1: Color Picker](#exp-10-exercise-1-color-picker)
    - [Exercise 2: Counter Component](#exp-10-exercise-2-counter-component)

---

## Experiment 1: Class and Objects

### Exp 1: Student and StudentDemo

```java
import java.util.Scanner;

class Student {
    private int rollNo;
    String name;
    double percent;

    void setDetails() {
        Scanner sc = new Scanner(System.in);
        System.out.println("Enter Roll Number:");
        rollNo = sc.nextInt();
        System.out.println("Enter Name:");
        name = sc.next();
        System.out.println("Enter Percentage:");
        percent = sc.nextDouble();
    }

    void displayDetails() {
        System.out.println("\n----Student Details----");
        System.out.println("Roll No: " + rollNo);
        System.out.println("Name: " + name);
        System.out.println("Percentage: " + percent);
    }
}

public class StudentDemo {
    public static void main(String[] args) {
        Student s = new Student();
        s.setDetails();
        s.displayDetails();
    }
}
```

### Exp 1: Exercise 1: Student Details and GPA Calculation

```java
import java.util.Scanner;

class Student {
    // Defining Data members
    int id;
    int crHours;
    int crPoints;
    double gpa;

    // Defining member functions
    void setData(int i, int ch, int cp) {
        id = i;
        crHours = ch;
        crPoints = cp;
    }

    void Display() {
        System.out.println("ID: " + id);
        System.out.println("Credit Hours : " + crHours);
        System.out.println("Credit Points: " + crPoints);
        System.out.println("GPA : " + gpa);
    }

    void calculateGpa() {
        gpa = (double) crPoints / crHours;
    }
}

public class ShowStudent {
    public static void main(String[] args) {
        int id, ch, cp;
        Student s = new Student();
        Scanner sc = new Scanner(System.in);

        System.out.println("Enter your ID");
        id = sc.nextInt();
        System.out.println("Enter your Credit Hours");
        ch = sc.nextInt();
        System.out.println("Enter your Credit points");
        cp = sc.nextInt();

        s.setData(id, ch, cp);
        s.calculateGpa();
        s.Display();
    }
}
```

### Exp 1: Exercise 2: Bank Account System

```java
import java.util.Scanner;

class BankAccount {
    String name;
    int accountNumber;
    String accountType;
    double balance;

    void assign(String n, int accNo, String type, double bal) {
        name = n;
        accountNumber = accNo;
        accountType = type;
        balance = bal;
    }

    void deposit(double amount) {
        balance = balance + amount;
        System.out.println("Amount Deposited: " + amount);
    }

    void withdraw(double amount) {
        if (amount <= balance) {
            balance = balance - amount;
            System.out.println("Amount Withdrawn: " + amount);
        } else {
            System.out.println("Insufficient Balance");
        }
    }

    void display() {
        System.out.println("Depositor Name :" + name);
        System.out.println("Balance: " + balance);
    }
}

public class BankAccountDemo {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        BankAccount b = new BankAccount();

        System.out.println("Enter Name: ");
        String name = sc.next();
        System.out.println("Enter Account Number:");
        int accNo = sc.nextInt();
        System.out.println("Enter Account Type:");
        String type = sc.next();
        System.out.println("Enter the Initial Balance:");
        double bal = sc.nextDouble();

        b.assign(name, accNo, type, bal);

        System.out.println("Enter the Amount to be Deposited:");
        double amt = sc.nextDouble();
        b.deposit(amt);

        System.out.println("Enter the Amount to be Withdrawn:");
        double amount = sc.nextDouble();
        b.withdraw(amount);

        b.display();
    }
}
```

---

## Experiment 2: Constructor & Method Overloading

### Exp 2: Employee Overloaded Constructors

```java
public class Employee {
    String name;
    int id;
    double salary;

    Employee() {
        name = "Unknown";
        id = 0;
        salary = 0;
    }

    Employee(String n, int m) {
        name = n;
        id = m;
        salary = 25000;
    }

    Employee(String n, int m, double s) {
        name = n;
        id = m;
        salary = s;
    }

    void display() {
        System.out.println("Name: " + name + ", ID: " + id + ", Salary: " + salary);
    }

    public static void main(String[] args) {
        Employee e1 = new Employee();
        Employee e2 = new Employee("Rahul", 102);
        Employee e3 = new Employee("Soham", 103, 50000);
        Employee e4 = e2;

        e1.display();
        e2.display();
        e3.display();
        e4.display();

        e2.name = "Vedant";
        e2.id = 131;
        e2.salary = 10000;

        e2.display();
        e4.display();
    }
}
```

### Exp 2: Exercise 1: Student Details with Copy Constructor

```java
import java.util.Scanner;

class Student {
    private int id;
    private int creditHours;
    private int creditPoints;
    private double gpa;

    Student() {
        id = 9999;
        creditHours = 3;
        creditPoints = 12;
    }

    Student(Student s) {
        id = s.id;
        creditHours = s.creditHours;
        creditPoints = s.creditPoints;
    }

    void setData(int id, int cp, int ch) {
        this.id = id;
        creditPoints = cp;
        creditHours = ch;
    }

    void calculate() {
        gpa = (double) creditPoints / creditHours;
    }

    void display() {
        System.out.println("ID Number: " + id);
        System.out.println("Credit Points: " + creditPoints);
        System.out.println("Credit Hours: " + creditHours);
        System.out.println("GPA: " + gpa);
    }
}

public class ShowStudent2 {
    public static void main(String[] args) {
        Student s1 = new Student();
        Scanner sc = new Scanner(System.in);

        System.out.println("Enter id, Credit points, Credit Hours");
        int id = sc.nextInt();
        int cp = sc.nextInt();
        int ch = sc.nextInt();

        s1.setData(id, cp, ch);
        s1.calculate();
        s1.display();

        Student s2 = new Student(s1);
        s2.calculate();
        s2.display();
    }
}
```

### Exp 2: Exercise 2: Computing Photo Book Bill

```java
import java.util.Scanner;

class Billing {
    double computeBill(double price) {
        return price + (price * 0.08);
    }

    double computeBill(double price, int quantity) {
        double total = price * quantity;
        return total + (total * 0.08);
    }

    double computeBill(double price, int quantity, double coupon) {
        double total = (price * quantity) - coupon;
        return total + (total * 0.08);
    }
}

public class BillingDemo {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        Billing obj = new Billing();

        System.out.print("Enter price of one photo book: ");
        double price1 = sc.nextDouble();
        double total1 = obj.computeBill(price1);

        System.out.print("Enter price of photo book: ");
        double price2 = sc.nextDouble();
        System.out.print("Enter quantity: ");
        int quantity = sc.nextInt();
        double total2 = obj.computeBill(price2, quantity);

        System.out.print("Enter price of photo book: ");
        double price3 = sc.nextDouble();
        System.out.print("Enter quantity: ");
        int quantity2 = sc.nextInt();
        System.out.print("Enter coupon value: ");
        double coupon = sc.nextDouble();
        double total3 = obj.computeBill(price3, quantity2, coupon);

        System.out.println("\nBill of one photo book: " + total1);
        System.out.println("Bill of multiple photo books: " + total2);
        System.out.println("Bill with coupon: " + total3);
    }
}
```

---

## Experiment 3: Inheritance & Exception Handling

### Exp 3: SuperDemo

```java
class Person {
    String name;
    int id;

    Person(String name, int id) {
        this.name = name;
        this.id = id;
        System.out.println("Person constructor called.");
    }

    void displayDetails() {
        System.out.println("Name: " + name);
        System.out.println("ID: " + id);
    }
}

class Employee extends Person {
    double salary;

    Employee(String name, int id, double salary) {
        super(name, id);
        this.salary = salary;
        System.out.println("Employee constructor called.");
    }

    void displayDetails() {
        super.displayDetails();
        System.out.println("Salary: " + salary);
    }
}

public class SuperDemo {
    public static void main(String[] args) {
        Employee emp = new Employee("Ravi", 101, 50000.0);
        emp.displayDetails();
    }
}
```

### Exp 3: Inbuilt Exception Handling

```java
public class InbuiltExceptionDemo {
    public static void main(String[] args) {
        int a = 10;
        int b = 0;
        try {
            int result = a / b;
            System.out.println("Result: " + result);
        } catch (ArithmeticException e) {
            System.out.println("You are trying to divide a number by zero, Exception caught: " + e);
        }
        System.out.println("Program continues inspite of the exception taking place......");
        System.out.println("There may be multiple actions listed in rest of the program,");
    }
}
```

### Exp 3: Custom Exception

```java
class InvalidAgeException extends Exception {
    InvalidAgeException(String message) {
        super(message);
    }
}

public class CustomExceptionDemo {
    static void checkAge(int age) throws InvalidAgeException {
        if (age < 18) {
            throw new InvalidAgeException("Age must be at least 18.");
        } else {
            System.out.println("Valid age for registration.");
        }
    }

    public static void main(String[] args) {
        try {
            checkAge(16);
        } catch (InvalidAgeException e) {
            System.out.println("Caught Exception: " + e.getMessage());
        }
    }
}
```

### Exp 3: Exercise 1: Poem Inheritance

```java
import java.util.Scanner;

class Poem {
    String title;
    int lines;

    Poem(String title, int lines) {
        this.title = title;
        this.lines = lines;
    }

    void display() {
        System.out.println("Title : " + this.title);
        System.out.println("Lines : " + this.lines);
    }
}

class Couplet extends Poem {
    Couplet(String title) {
        super(title, 2);
    }
}

class Limerick extends Poem {
    Limerick(String title) {
        super(title, 5);
    }
}

class Haiku extends Poem {
    Haiku(String title) {
        super(title, 3);
    }
}

public class DemoPoems {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.println("Enter the name of title Couplet");
        String a = sc.nextLine();
        Couplet c = new Couplet(a);

        System.out.println("Enter the name of title for Limerick");
        String b = sc.nextLine();
        Limerick l = new Limerick(b);

        System.out.println("Enter the name of title for Haiku");
        String d = sc.nextLine();
        Haiku h = new Haiku(d);

        System.out.println("Couplet");
        c.display();
        System.out.println();

        System.out.println("Limerick");
        l.display();
        System.out.println();

        System.out.println("Haiku");
        h.display();
    }
}
```

### Exp 3: Exercise 2: Exception Handling in Constructors

```java
class Base {
    Base() throws Exception {
        System.out.println("Base Class Constructor");
        throw new Exception("Exception from Base Constructor");
    }
}

class Derived extends Base {
    Derived() throws Exception {
        try {
            System.out.println("Derived Class Constructor");
        } catch (Exception e) {
            System.out.println("Caught in Derived: " + e.getMessage());
        }
    }
}

public class Trail {
    public static void main(String[] args) {
        try {
            Derived d = new Derived();
        } catch (Exception e) {
            System.out.println("Caught in main class: " + e.getMessage());
        }
    }
}
```

---

## Experiment 4: HTML, CSS & JavaScript

### Exp 4: Static Website

#### 1. `index.html`
```html
<!DOCTYPE html>
<html>
<head>
    <title>Welcome to My Static Website</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <header>
        <h1>Welcome to My Static Website</h1>
        <nav>
            <ul>
                <li><a href="#">Home</a></li>
                <li><a href="#">About</a></li>
                <li><a href="#">Contact</a></li>
            </ul>
        </nav>
    </header>
    <main>
        <h2>Hello, Dear Student!</h2>
        <p>This is a sample static website built using HTML, CSS, and JavaScript.</p>
        <button onclick="showMessage()">Click Me</button>
        <p id="message"></p>
    </main>
    <footer>
        <p>Full Stack Java</p>
    </footer>
    <script src="script.js"></script>
</body>
</html>
```

#### 2. `script.js`
```javascript
function showMessage() {
    const message = document.getElementById("message");
    message.textContent = "Thank you for clicking! Enjoy browsing ";
}
```

#### 3. `style.css`
```css
body {
    font-family: Arial, sans-serif;
    margin: 0;
    padding: 0;
    background-color: #f9f9f9;
    color: #333;
}

header {
    background-color: #007acc;
    color: white;
    padding: 20px;
    text-align: center;
}

nav ul {
    list-style: none;
    padding: 0;
    display: flex;
    justify-content: center;
    margin-top: 10px;
}

nav li {
    margin: 0 15px;
}

nav a {
    color: white;
    text-decoration: none;
    font-weight: bold;
}

main {
    padding: 20px;
    text-align: center;
}

button {
    padding: 10px 20px;
    font-size: 16px;
    cursor: pointer;
}

footer {
    background-color: #eee;
    text-align: center;
    padding: 15px;
    margin-top: 40px;
}
```

### Exp 4: Exercise 1: Quote Generator

#### 1. `index.html`
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Quote Generator</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <p id="quote">Click the button to get a quote!</p>
    <button onclick="newQuote()">New Quote</button>
    <script src="script.js"></script>
</body>
</html>
```

#### 2. `script.js`
```javascript
const quotes = [
    "Believe in yourself and keep going!",
    "Success is not final, failure is not fatal.",
    "Dream big and work hard!",
    "Don't worry, be happy!",
    "Your only limit is your mind.",
    "I am not lazy, I am on energy-saving mode.",
    "Study now, enjoy later!",
    "Every day is a new opportunity."
];

function newQuote() {
    const randomIndex = Math.floor(Math.random() * quotes.length);
    document.getElementById("quote").innerText = quotes[randomIndex];
    const r = Math.floor(Math.random() * 256);
    const g = Math.floor(Math.random() * 256);
    const b = Math.floor(Math.random() * 256);
    document.getElementById("quote").style.color = `rgb(${r}, ${g}, ${b})`;
}
```

#### 3. `style.css`
```css
body {
    text-align: center;
    font-family: Arial, sans-serif;
    margin-top: 200px;
}

#quote {
    font-size: 24px;
    margin-bottom: 30px;
}

button {
    padding: 12px 25px;
    font-size: 18px;
    cursor: pointer;
}
```

### Exp 4: Exercise 2: To-Do List

#### 1. `index.html`
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>To-Do List</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <h1>To-Do List</h1>
    <input type="text" id="taskInput" placeholder="Enter a task">
    <button onclick="addTask()">Add Task</button>
    <ul id="taskList"></ul>
    <script src="script.js"></script>
</body>
</html>
```

#### 2. `script.js`
```javascript
function addTask() {
    const input = document.getElementById("taskInput");
    const taskText = input.value.trim();

    if (taskText === "") {
        alert("Please enter a task!");
        return;
    }

    const li = document.createElement("li");
    li.innerText = taskText;

    li.addEventListener("click", function() {
        li.classList.toggle("completed");
    });

    const deleteButton = document.createElement("span");
    deleteButton.innerText = " ❌";
    deleteButton.className = "delete";
    deleteButton.addEventListener("click", function(event) {
        event.stopPropagation();
        li.remove();
    });

    li.appendChild(deleteButton);
    document.getElementById("taskList").appendChild(li);
    input.value = "";
}
```

#### 3. `style.css`
```css
body {
    text-align: center;
    font-family: Arial, sans-serif;
    margin-top: 100px;
}

input {
    padding: 10px;
    width: 250px;
    font-size: 16px;
}

button {
    padding: 10px 20px;
    font-size: 16px;
    cursor: pointer;
}

ul {
    list-style-type: none;
    padding: 0;
    margin: 30px auto;
    width: 350px;
}

li {
    padding: 10px;
    margin: 8px;
    background-color: #f2f2f2;
    cursor: pointer;
}

.completed {
    text-decoration: line-through;
}

.delete {
    float: right;
    cursor: pointer;
}
```

---

## Experiment 5: JavaScript Logic & Validation

### Exp 5: Email Address Validation

#### 1. `index.html`
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Welcome to My Static Website</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <header>
        <h1>Welcome to My Static Website</h1>
        <nav>
            <ul>
                <li><a href="#">Home</a></li>
                <li><a href="#">About</a></li>
                <li><a href="#">Contact</a></li>
            </ul>
        </nav>
    </header>
    <main>
        <h2>Hello, Dear Students!</h2>
        <p>This is a sample static website built using HTML, CSS, and JavaScript.</p>
        <button onclick="showMessage()">Click Me</button>
        <p id="message"></p>

        <h3>Subscribe to our Newsletter</h3>
        <form onsubmit="return validateEmail()">
            <input type="text" id="email" placeholder="Enter your email">
            <button type="submit">Submit</button>
        </form>
    </main>
    <footer>
        <p>FULL STACK JAVA PROGRAMS</p>
    </footer>
    <script src="script.js"></script>
</body>
</html>
```

#### 2. `script.js`
```javascript
function showMessage() {
    const message = document.getElementById("message");
    message.textContent = "Thank you for clicking! Enjoy browsing ";
}

function validateEmail() {
    const emailInput = document.getElementById("email");
    const email = emailInput.value;

    if (email.indexOf("@") === -1 || email.indexOf(".") === -1) {
        alert("Invalid email address. Please include '@' and '.' characters.");
        emailInput.focus();
        return false;
    }
    alert("Email is valid!");
    return true;
}
```

#### 3. `style.css`
```css
body {
    font-family: Arial, sans-serif;
    margin: 0;
    padding: 0;
    background-color: #f9f9f9;
    color: #333;
}

header {
    background-color: #007acc;
    color: white;
    padding: 20px;
    text-align: center;
}

nav ul {
    list-style: none;
    padding: 0;
    display: flex;
    justify-content: center;
    margin-top: 10px;
}

nav li {
    margin: 0 15px;
}

nav a {
    color: white;
    text-decoration: none;
    font-weight: bold;
}

main {
    padding: 20px;
    text-align: center;
}

button {
    padding: 10px 20px;
    font-size: 16px;
    cursor: pointer;
}

footer {
    background-color: #eee;
    text-align: center;
    padding: 15px;
    margin-top: 40px;
}
```

### Exp 5: Exercise 1: Donut Subtotal Calculator

```javascript
function calculateSubtotal(quantity, pricePerDonut) {
    let numberOfDonuts;

    if (typeof quantity === "string" && quantity.toLowerCase() === "dozen") {
        numberOfDonuts = 12;
    } else {
        numberOfDonuts = Number(quantity);
    }

    let subtotal = numberOfDonuts * pricePerDonut;
    return subtotal;
}
```

### Exp 5: Exercise 2: Anagram Checker

```javascript
function areAnagrams(str1, str2) {
    str1 = str1.toLowerCase();
    str2 = str2.toLowerCase();

    if (str1.length !== str2.length) {
        return false;
    }

    let sortedStr1 = str1.split("").sort().join("");
    let sortedStr2 = str2.split("").sort().join("");

    return sortedStr1 === sortedStr2;
}

console.log(areAnagrams("listen", "silent"));   // true
console.log(areAnagrams("hello", "world"));     // false
console.log(areAnagrams("triangle", "integral")); // true
```

---

## Experiment 6: Interactive Calculator & Algorithms

### Exp 6: Calculator

#### 1. `index.html`
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Simple Calculator</title>
    <link rel="stylesheet" href="calstyle.css">
</head>
<body>
    <div class="container">
        <h1>Simple Calculator</h1>
        <input type="number" id="num1" placeholder="Enter first number">
        <input type="number" id="num2" placeholder="Enter second number">
        <div class="buttons">
            <button onclick="add()">+</button>
            <button onclick="subtract()">−</button>
            <button onclick="multiply()">×</button>
            <button onclick="divide()">÷</button>
            <button onclick="square()">x²</button>
            <button onclick="percentage()">%</button>
        </div>
        <h2 id="result">Result:</h2>
    </div>
    <script src="calscript.js"></script>
</body>
</html>
```

#### 2. `calstyle.css`
```css
body {
    font-family: Arial, sans-serif;
    background-color: #f2f2f2;
}

.container {
    width: 350px;
    margin: 60px auto;
    background: white;
    padding: 20px;
    text-align: center;
    border-radius: 10px;
    box-shadow: 0px 0px 10px gray;
}

input {
    width: 90%;
    padding: 10px;
    margin: 10px 0;
    font-size: 16px;
}

.buttons {
    margin-top: 15px;
}

button {
    width: 60px;
    padding: 10px;
    margin: 5px;
    font-size: 18px;
    cursor: pointer;
}

button:hover {
    background-color: lightblue;
}

h2 {
    margin-top: 20px;
    color: blue;
}
```

#### 3. `calscript.js`
```javascript
function getNumbers() {
    let num1 = Number(document.getElementById("num1").value);
    let num2 = Number(document.getElementById("num2").value);
    return [num1, num2];
}

function add() {
    let numbers = getNumbers();
    let result = numbers[0] + numbers[1];
    document.getElementById("result").innerHTML = "Result: " + result;
}

function subtract() {
    let numbers = getNumbers();
    let result = numbers[0] - numbers[1];
    document.getElementById("result").innerHTML = "Result: " + result;
}

function multiply() {
    let numbers = getNumbers();
    let result = numbers[0] * numbers[1];
    document.getElementById("result").innerHTML = "Result: " + result;
}

function divide() {
    let numbers = getNumbers();
    if (numbers[1] == 0) {
        document.getElementById("result").innerHTML = "Cannot divide by zero";
        return;
    }
    let result = numbers[0] / numbers[1];
    document.getElementById("result").innerHTML = "Result: " + result;
}

function square() {
    let numbers = getNumbers();
    let result = numbers[0] ** 2;
    document.getElementById("result").innerHTML = "Result: " + result;
}

function percentage() {
    let numbers = getNumbers();
    if (numbers[1] == 0) {
        document.getElementById("result").innerHTML = "Cannot calculate percentage with zero";
        return;
    }
    let result = (numbers[0] / numbers[1]) * 100;
    document.getElementById("result").innerHTML = "Percentage: " + result + "%";
}
```

### Exp 6: Exercise 1: FizzBuzz

```javascript
for (let i = 1; i <= 100; i++) {
    if (i % 3 === 0 && i % 5 === 0) {
        console.log("FizzBuzz");
    } else if (i % 3 === 0) {
        console.log("Fizz");
    } else if (i % 5 === 0) {
        console.log("Buzz");
    } else {
        console.log(i);
    }
}
```

### Exp 6: Exercise 2: Prime Number Generator

```javascript
function isPrime(num) {
    if (num < 2) {
        return false;
    }
    for (let i = 2; i < num; i++) {
        if (num % i === 0) {
            return false;
        }
    }
    return true;
}

for (let i = 1; i <= 50; i++) {
    if (isPrime(i)) {
        console.log(i);
    }
}
```

---

## Experiment 7: Java Servlets

### Exp 7: FirstServlet

#### 1. `FirstServlet.java`
```java
import java.io.*;
import javax.servlet.*;

public class FirstServlet extends GenericServlet {
    public void service(ServletRequest req, ServletResponse resp)
            throws ServletException, IOException {
        resp.setContentType("text/html");
        PrintWriter pw = resp.getWriter();
        pw.println("<html>");
        pw.println("<head>");
        pw.println("<title>My First Servlet</title>");
        pw.println("</head>");
        pw.println("<body>");
        pw.println("<h1>Welcome To Servlet World!</h1>");
        pw.println("</body>");
        pw.println("</html>");
        pw.close();
    }
}
```

#### 2. `web.xml`
```xml
<web-app>
    <servlet>
        <servlet-name>FirstServlet</servlet-name>
        <servlet-class>FirstServlet</servlet-class>
    </servlet>
    <servlet-mapping>
        <servlet-name>FirstServlet</servlet-name>
        <url-pattern>/FirstServlet</url-pattern>
    </servlet-mapping>
</web-app>
```

### Exp 7: Exercise 1: Greet User

#### 1. `Index.html`
```html
<!DOCTYPE html>
<html>
<head>
    <title>Hello</title>
</head>
<body>
    <form action="Hello" method="get">
        <label>If you don't mind me asking, what is your name?</label>
        <input type="text" name="name">
        <input type="submit" value="Hello">
    </form>
</body>
</html>
```

#### 2. `Hello.java`
```java
import java.io.IOException;
import java.io.PrintWriter;
import javax.servlet.ServletException;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;

public class Hello extends HttpServlet {
    protected void doGet(HttpServletRequest request,
            HttpServletResponse response)
            throws ServletException, IOException {
        String name = request.getParameter("name");
        response.setContentType("text/html");
        PrintWriter out = response.getWriter();
        out.println("<html>");
        out.println("<head>");
        out.println("<title>Hello</title>");
        out.println("</head>");
        out.println("<body>");
        out.println("<h2>Hello, " + name + "</h2>");
        out.println("</body>");
        out.println("</html>");
    }
}
```

#### 3. `web.xml`
```xml
<web-app>
    <servlet>
        <servlet-name>Hello</servlet-name>
        <servlet-class>Hello</servlet-class>
    </servlet>
    <servlet-mapping>
        <servlet-name>Hello</servlet-name>
        <url-pattern>/Hello</url-pattern>
    </servlet-mapping>
</web-app>
```

### Exp 7: Exercise 2: Servlet Lifecycle

#### 1. `Lifecycle.java`
```java
import java.io.IOException;
import java.io.PrintWriter;
import javax.servlet.ServletConfig;
import javax.servlet.ServletException;
import javax.servlet.ServletRequest;
import javax.servlet.ServletResponse;
import javax.servlet.http.HttpServlet;

public class Lifecycle extends HttpServlet {
    @Override
    public void init(ServletConfig config) throws ServletException {
        super.init(config);
        System.out.println("Servlet is initialized");
    }

    @Override
    public void service(ServletRequest request, ServletResponse response)
            throws ServletException, IOException {
        System.out.println("Service method is called");
        response.setContentType("text/html");
        PrintWriter out = response.getWriter();
        out.println("<html>");
        out.println("<head>");
        out.println("<title>Lifecycle</title>");
        out.println("</head>");
        out.println("<body>");
        out.println("<h2>Servlet Life Cycle Demonstration</h2>");
        out.println("<p>Service method executed successfully.</p>");
        out.println("</body>");
        out.println("</html>");
    }

    @Override
    public void destroy() {
        System.out.println("Servlet is destroyed");
    }
}
```

#### 2. `web.xml`
```xml
<web-app>
    <servlet>
        <servlet-name>Lifecycle</servlet-name>
        <servlet-class>Lifecycle</servlet-class>
    </servlet>
    <servlet-mapping>
        <servlet-name>Lifecycle</servlet-name>
        <url-pattern>/Lifecycle</url-pattern>
    </servlet-mapping>
</web-app>
```

---

## Experiment 8: JSP, Servlets & JDBC

### Exp 8: User Login Authentication

#### 1. `LoginServlet.java`
```java
import java.io.IOException;
import java.sql.*;
import javax.servlet.*;
import javax.servlet.annotation.WebServlet;
import javax.servlet.http.*;

@WebServlet("/LoginServlet")
public class LoginServlet extends HttpServlet {
    private static final String DB_URL = "jdbc:mysql://localhost:3306/login_db";
    private static final String DB_USER = "root";
    private static final String DB_PASSWORD = "YOUR_DATABASE_PASSWORD";

    protected void doPost(HttpServletRequest request,
            HttpServletResponse response)
            throws ServletException, IOException {
        String uname = request.getParameter("username");
        String pwd = request.getParameter("password");

        try {
            Class.forName("com.mysql.cj.jdbc.Driver");
            Connection conn = DriverManager.getConnection(DB_URL, DB_USER, DB_PASSWORD);

            PreparedStatement ps = conn.prepareStatement(
                "SELECT * FROM users WHERE username=? AND password=?"
            );
            ps.setString(1, uname);
            ps.setString(2, pwd);

            ResultSet rs = ps.executeQuery();
            if (rs.next()) {
                request.setAttribute("username", uname);
                RequestDispatcher rd = request.getRequestDispatcher("welcome.jsp");
                rd.forward(request, response);
            } else {
                RequestDispatcher rd = request.getRequestDispatcher("error.jsp");
                rd.forward(request, response);
            }
            rs.close();
            ps.close();
            conn.close();
        } catch (Exception e) {
            throw new ServletException("Login Failed", e);
        }
    }
}
```

#### 2. `login.jsp`
```jsp
<%@ page language="java" contentType="text/html; charset=UTF-8" pageEncoding="UTF-8" %>
<!DOCTYPE html>
<html>
<head>
    <title>Login Form</title>
</head>
<body>
    <h2>Login Form</h2>
    <form action="LoginServlet" method="post">
        Username:
        <input type="text" name="username" required>
        <br><br>
        Password:
        <input type="password" name="password" required>
        <br><br>
        <input type="submit" value="Login">
    </form>
</body>
</html>
```

#### 3. `error.jsp`
```jsp
<%@ page language="java" contentType="text/html; charset=UTF-8" pageEncoding="UTF-8" %>
<!DOCTYPE html>
<html>
<head>
    <title>Login Failed</title>
</head>
<body>
    <h2>Login Failed</h2>
    <p>Invalid username or password. Try again.</p>
    <a href="login.jsp">Back to Login</a>
</body>
</html>
```

#### 4. `welcome.jsp`
```jsp
<%@ page language="java" contentType="text/html; charset=UTF-8" pageEncoding="UTF-8" %>
<!DOCTYPE html>
<html>
<head>
    <title>Welcome</title>
</head>
<body>
    <h2>Welcome, <%= request.getAttribute("username") %>!</h2>
    <p>You have successfully logged in.</p>
</body>
</html>
```

#### 5. `web.xml`
```xml
<web-app>
    <servlet>
        <servlet-name>LoginServlet</servlet-name>
        <servlet-class>LoginServlet</servlet-class>
    </servlet>
    <servlet-mapping>
        <servlet-name>LoginServlet</servlet-name>
        <url-pattern>/LoginServlet</url-pattern>
    </servlet-mapping>
</web-app>
```

### Exp 8: Exercise 1: Employee Phonebook

#### 1. `PhoneBookServlet.java`
```java
import java.io.IOException;
import java.io.PrintWriter;
import java.sql.*;
import javax.servlet.ServletException;
import javax.servlet.annotation.WebServlet;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;

@WebServlet("/phonebook")
public class PhonebookServlet extends HttpServlet {
    private static final String DB_URL = "jdbc:mysql://localhost:3306/login_db";
    private static final String DB_USER = "root";
    private static final String DB_PASSWORD = "YOUR_DATABASE_PASSWORD";

    protected void doGet(HttpServletRequest request,
            HttpServletResponse response)
            throws ServletException, IOException {
        response.setContentType("text/html");
        PrintWriter out = response.getWriter();
        out.println("<html>");
        out.println("<head>");
        out.println("<title>Employee Phonebook</title>");
        out.println("</head>");
        out.println("<body>");
        out.println("<h1>Employee Phonebook</h1>");
        out.println("<ul>");

        try {
            Class.forName("com.mysql.cj.jdbc.Driver");
            Connection conn = DriverManager.getConnection(DB_URL, DB_USER, DB_PASSWORD);
            Statement stmt = conn.createStatement();
            ResultSet rs = stmt.executeQuery("SELECT name, phone FROM employees");

            while (rs.next()) {
                String name = rs.getString("name");
                String phone = rs.getString("phone");
                out.println("<li>" + name + " - " + phone + "</li>");
            }
            rs.close();
            stmt.close();
            conn.close();
        } catch (Exception e) {
            out.println("<p>Error: " + e.getMessage() + "</p>");
        }

        out.println("</ul>");
        out.println("</body>");
        out.println("</html>");
    }
}
```

#### 2. `web.xml`
```xml
<web-app>
    <servlet>
        <servlet-name>PhonebookServlet</servlet-name>
        <servlet-class>PhonebookServlet</servlet-class>
    </servlet>
    <servlet-mapping>
        <servlet-name>PhonebookServlet</servlet-name>
        <url-pattern>/phonebook</url-pattern>
    </servlet-mapping>
</web-app>
```

### Exp 8: Exercise 2: Student Registration System

#### 1. `RegisterServlet.java`
```java
import java.io.IOException;
import java.io.PrintWriter;
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.PreparedStatement;
import javax.servlet.ServletException;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;

public class RegisterServlet extends HttpServlet {
    private static final String DB_URL = "jdbc:mysql://localhost:3306/login_db";
    private static final String DB_USER = "root";
    private static final String DB_PASSWORD = "YOUR_DATABASE_PASSWORD";

    protected void doPost(HttpServletRequest request,
            HttpServletResponse response)
            throws ServletException, IOException {
        String name = request.getParameter("name");
        String course = request.getParameter("course");
        response.setContentType("text/html");
        PrintWriter out = response.getWriter();

        try {
            Class.forName("com.mysql.cj.jdbc.Driver");
            Connection con = DriverManager.getConnection(DB_URL, DB_USER, DB_PASSWORD);

            String sql = "INSERT INTO students (name, course) VALUES (?, ?)";
            PreparedStatement ps = con.prepareStatement(sql);
            ps.setString(1, name);
            ps.setString(2, course);
            ps.executeUpdate();

            out.println("<html>");
            out.println("<body>");
            out.println("<h2>Student registered successfully!</h2>");
            out.println("</body>");
            out.println("</html>");

            ps.close();
            con.close();
        } catch (Exception e) {
            out.println("<h3>Error: " + e.getMessage() + "</h3>");
        }
    }
}
```

#### 2. `Register.jsp`
```jsp
<!DOCTYPE html>
<html>
<head>
    <title>Register Student</title>
</head>
<body>
    <h1>Register Student</h1>
    <form action="register" method="post">
        Name:
        <input type="text" name="name" required>
        <br><br>
        Course:
        <select name="course" required>
            <option value="Python">Python</option>
            <option value="Java">Java</option>
            <option value="C++">C++</option>
            <option value="Web Development">Web Development</option>
        </select>
        <br><br>
        <input type="submit" value="Register">
    </form>
</body>
</html>
```

#### 3. `web.xml`
```xml
<web-app>
    <servlet>
        <servlet-name>RegisterServlet</servlet-name>
        <servlet-class>RegisterServlet</servlet-class>
    </servlet>
    <servlet-mapping>
        <servlet-name>RegisterServlet</servlet-name>
        <url-pattern>/register</url-pattern>
    </servlet-mapping>
</web-app>
```

---

## Experiment 9: JSP (JavaServer Pages)

### Exp 9: Hello World JSP

```jsp
<html>
<head>
    <title>First Program</title>
</head>
<body>
    <h1>Output of JSP file</h1>
    <%
        out.println("Hello World");
    %>
</body>
</html>
```

### Exp 9: Exercise 1: Date and Time

```jsp
<%@ page import="java.util.Date" %>
<html>
<head>
    <title>JSP Test</title>
</head>
<body>
    <h1>JSP Test</h1>
    <%
        Date currentDate = new Date();
    %>
    Time: <%= currentDate %>
</body>
</html>
```

### Exp 9: Exercise 2: User Information Form

#### 1. `userinfo.html`
```html
<!DOCTYPE html>
<html>
<head>
    <title>User Information Form</title>
</head>
<body>
    <form action="userinfo.jsp" method="post">
        <table>
            <tr>
                <td>Name:</td>
                <td><input type="text" name="name" required></td>
            </tr>
            <tr>
                <td>Birth Date:</td>
                <td>
                    <input type="date" name="birthdate" required>
                    (Use format yyyy-mm-dd)
                </td>
            </tr>
            <tr>
                <td>Email Address:</td>
                <td>
                    <input type="email" name="email" required>
                    (Use format name@company.com)
                </td>
            </tr>
            <tr>
                <td>Lucky Number:</td>
                <td>
                    <input type="number" name="luckynumber" required>
                    (Digits only)
                </td>
            </tr>
            <tr>
                <td colspan="2">
                    <input type="submit" value="Submit">
                </td>
            </tr>
        </table>
    </form>
</body>
</html>
```

#### 2. `userinfo.jsp`
```jsp
<%@ page language="java" contentType="text/html; charset=UTF-8" %>
<%
    String name = request.getParameter("name");
    String birthDate = request.getParameter("birthdate");
    String email = request.getParameter("email");
    String luckyNumberString = request.getParameter("luckynumber");
    int luckyNumber = Integer.parseInt(luckyNumberString);
%>
<!DOCTYPE html>
<html>
<head>
    <title>User Information</title>
</head>
<body>
    <h2>User Information</h2>
    <table border="1">
        <tr>
            <th>Name</th>
            <td><%= name %></td>
        </tr>
        <tr>
            <th>Birth Date</th>
            <td><%= birthDate %></td>
        </tr>
        <tr>
            <th>Email Address</th>
            <td><%= email %></td>
        </tr>
        <tr>
            <th>Lucky Number</th>
            <td><%= luckyNumber %></td>
        </tr>
    </table>
</body>
</html>
```

---

## Experiment 10: React Frontend

### Exp 10: React State Clicker

`App.js`
```javascript
import { useState } from 'react';
import './App.css';

function App() {
    const [message, setMessage] = useState("Happy Learning React!");

    return (
        <div>
            <h1>{message}</h1>
            <button onClick={() => setMessage("You just Reacted by clicking!")}>
                Click Me
            </button>
        </div>
    );
}

export default App;
```

### Exp 10: Exercise 1: Color Picker

`App.js`
```javascript
import { useState } from 'react';
import './App.css';

function App() {
    const [selectedColor, setSelectedColor] = useState('');

    const handleColorClick = (color) => {
        setSelectedColor(color);
    };

    return (
        <div>
            <h2>Select a Color</h2>
            <button
                onClick={() => handleColorClick('Red')}
                style={{
                    margin: '5px',
                    backgroundColor: 'red',
                    color: 'white',
                    padding: '10px 20px'
                }}
            >
                Red
            </button>
            <button
                onClick={() => handleColorClick('Blue')}
                style={{
                    margin: '5px',
                    backgroundColor: 'blue',
                    color: 'white',
                    padding: '10px 20px'
                }}
            >
                Blue
            </button>
            <button
                onClick={() => handleColorClick('Green')}
                style={{
                    margin: '5px',
                    backgroundColor: 'green',
                    color: 'white',
                    padding: '10px 20px'
                }}
            >
                Green
            </button>
            <button
                onClick={() => handleColorClick('Yellow')}
                style={{
                    margin: '5px',
                    backgroundColor: 'gold',
                    color: 'black',
                    padding: '10px 20px'
                }}
            >
                Yellow
            </button>
            {selectedColor && (
                <h3>You have selected {selectedColor}.</h3>
            )}
        </div>
    );
}

export default App;
```

### Exp 10: Exercise 2: Counter Component

`App.js`
```javascript
import React, { useState } from 'react';
import logo from './logo.svg';
import './App.css';

function App() {
    const [count, setCount] = useState(0);

    return (
        <div>
            <h1>Counter: {count}</h1>
            <button onClick={() => setCount(count + 1)}>
                Increase
            </button>
            <button onClick={() => setCount(count - 1)}>
                Decrease
            </button>
        </div>
    );
}

export default App;
```
