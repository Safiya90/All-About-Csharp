# All-About-C#
## Variables##
Variables in C# are named containers that store data in your program. They're essential because they let you save information that can be used or changed as your program runs.

Declaring and Initializing Variables
To use variables in C#, you need to:

1. Declare the variable
Specify the data type and name:
<pre>int studentAge;
string courseName;</pre>
2. Initialize the variable
Assign values after declaration:
<pre>studentAge = 20;
courseName = "Programming 101";</pre>
3. Declare and initialize at once:
   <pre>int studentAge = 20;
string courseName = "Programming 101";</pre>
# Main Data Types in C#:
| Type     | Description       | Example         |
| -------- | ----------------- | --------------- |
| `int`    | Whole numbers     | `42`            |
| `double` | Decimal numbers   | `3.14`          |
| `string` | Text              | `"Hello"`       |
| `bool`   | True/false values | `true`, `false` |
| `char`   | Single characters | `'A'`           |

# Important Concepts:
**Descriptive names:** Use clear names like totalScore instead of x.

**Case-sensitive:** age and Age are different variables.

**Type-specific:** A variable can only store data of its declared type.

**Scope:** Variables can only be accessed where they're in scope.

# Example:#
   <pre>int score = 95;
string studentName = "Alex";
bool isPassing = true;

// Update variable values
score = 97;

// Use variables in calculations
int bonusPoints = 5;
int finalScore = score + bonusPoints;  // equals 102

// Display variable values
Console.WriteLine($"{studentName} has a score of {finalScore}");
</pre>


# C# Data Types

C# has a rich set of data types that allow you to work with different kinds of information in your programs. Here's a comprehensive overview:

---

## Value Types

Value types directly contain their data and are stored on the stack. When you assign a value type to another variable, it creates a copy of the value.

### Integer Types

- **byte**: 8-bit unsigned integer (0 to 255)  
  ```csharp
  byte age = 25;
  ```
- **sbyte**: 8-bit signed integer (-128 to 127)  
  ```csharp
  sbyte temperature = -10;
  ```
- **short**: 16-bit signed integer (-32,768 to 32,767)  
  ```csharp
  short population = 30000;
  ```
- **ushort**: 16-bit unsigned integer (0 to 65,535)  
  ```csharp
  ushort itemCount = 50000;
  ```
- **int**: 32-bit signed integer (-2,147,483,648 to 2,147,483,647)  
  ```csharp
  int score = 98750;
  ```
- **uint**: 32-bit unsigned integer (0 to 4,294,967,295)  
  ```csharp
  uint viewCount = 3000000000;
  ```
- **long**: 64-bit signed integer (-9,223,372,036,854,775,808 to 9,223,372,036,854,775,807)  
  ```csharp
  long nationalDebt = 24000000000000L;
  ```
- **ulong**: 64-bit unsigned integer (0 to 18,446,744,073,709,551,615)  
  ```csharp
  ulong distanceInMeters = 9460730472580800UL; // Light year in meters
  ```

### Floating Point Types

- **float**: 32-bit single-precision (~7 digits precision)  
  ```csharp
  float height = 1.75f; // Note the 'f' suffix
  ```
- **double**: 64-bit double-precision (~15-16 digits precision)  
  ```csharp
  double pi = 3.14159265359;
  ```

### Decimal Type

- **decimal**: 128-bit high-precision decimal (28-29 significant digits)  
  ```csharp
  decimal accountBalance = 1345.67m; // Note the 'm' suffix
  ```

### Boolean Type

- **bool**: Represents true or false  
  ```csharp
  bool isApproved = true;
  ```

### Character Type

- **char**: Single 16-bit Unicode character  
  ```csharp
  char grade = 'A';
  ```

---

## Reference Types

Reference types store a reference to the actual data, which is stored on the heap. When you assign a reference type to another variable, both variables reference the same object.

### String Type

- **string**: Sequence of characters  
  ```csharp
  string name = "John Smith";
  ```

### Object Type

- **object**: Base type for all other types in C#  
  ```csharp
  object anyValue = 42; // Can hold any type
  ```

### Array Types

Arrays store multiple values of the same type  
```csharp
int[] scores = { 85, 92, 78, 90 };
string[] names = new string[3]; // Creates array with 3 empty slots
```

### Class Types

User-defined reference types  
```csharp
Person student = new Person(); // Assuming Person class exists
```

### Interface Types

Define contracts for classes to implement  
```csharp
IEnumerable<int> numbers = new List<int>();
```

---

## Special Types

### Dynamic Type

- **dynamic**: Bypasses compile-time type checking  
  ```csharp
  dynamic value = 10;
  value = "Now I'm a string"; // Valid at runtime
  ```

### Nullable Types

Allow value types to represent null values  
```csharp
int? nullableAge = null;
double? nullablePrice = 19.99;
```

---

## Type Conversion

### Implicit Conversion

Happens automatically when no data loss is possible:  
```csharp
int number = 100;
long bigNumber = number; // Implicit conversion from int to long
```

### Explicit Conversion (Casting)

Required when data loss might occur:  
```csharp
double price = 19.99;
int roundedPrice = (int)price; // Explicitly cast to int, result is 19
```

### Helper Methods

```csharp
string input = "42";
int value = Convert.ToInt32(input); // Convert string to int
// or
int value = int.Parse(input);
// Safe parsing
int.TryParse(input, out int result); // Returns bool indicating success
```

---

## Type Checking

### Using `typeof` and `GetType()`

```csharp
if (typeof(string) == value.GetType())
{
    Console.WriteLine("Value is a string");
}
```

### Using `is` Operator

```csharp
if (value is string)
{
    string text = value as string;
    // or with pattern matching
    if (value is string text2)
    {
        // Use text2 here
    }
}
```

---

## Best Practices

- Choose the right type for your data to optimize memory usage.
- Use `int` for most whole numbers unless you have specific range requirements.
- Use `double` for general floating-point calculations and `decimal` for financial calculations.
- Be careful with implicit and explicit conversions to avoid data loss.
- Use nullable types when you need to represent the absence of a value.
- Consider memory usage when working with large datasets.

---

Understanding data types is fundamental to writing efficient and bug-free C# code, as it ensures your data is stored and manipulated correctly.

---

# Interactions in C#

Interactions in C# refer to how different parts of code communicate with each other and with users. Here's a concise overview of key interaction types in C#:


## User Interactions

### Console Applications

```csharp
// Get input from user
Console.Write("Enter your name: ");
string name = Console.ReadLine();

// Display output to user
Console.WriteLine($"Hello, {name}!");

// Waiting for key press
Console.WriteLine("Press any key to continue...");
Console.ReadKey();
```

### Windows Forms (Desktop GUI)

```csharp
// Button click event handler
private void submitButton_Click(object sender, EventArgs e)
{
    string input = textBox1.Text;
    resultLabel.Text = $"You entered: {input}";
    MessageBox.Show("Data submitted successfully!");
}
```

### WPF (Windows Presentation Foundation)

```xml
<!-- XAML Button with click event -->
<Button Content="Click Me" Click="Button_Click"/>
```

```csharp
// C# event handler
private void Button_Click(object sender, RoutedEventArgs e)
{
    ResultTextBlock.Text = "Button was clicked!";
}
```

---

## Object Interactions

### Method Calls

```csharp
// Define a class with methods
public class Calculator
{
    public int Add(int a, int b)
    {
        return a + b;
    }
}

// Use the class
Calculator calc = new Calculator();
int result = calc.Add(5, 3); // result = 8
```

### Events and Delegates

```csharp
// Define a delegate and event
public delegate void PriceChangedEventHandler(decimal oldPrice, decimal newPrice);
public event PriceChangedEventHandler PriceChanged;

// Raise the event
private decimal _price;
public decimal Price
{
    get { return _price; }
    set
    {
        if (_price != value)
        {
            decimal oldPrice = _price;
            _price = value;
            // Notify subscribers
            PriceChanged?.Invoke(oldPrice, _price);
        }
    }
}

// Subscribe to the event
product.PriceChanged += (oldPrice, newPrice) => 
    Console.WriteLine($"Price changed from {oldPrice} to {newPrice}");
```

# Math Operations in C#

C# provides a comprehensive set of mathematical operations and tools to perform calculations in your applications. Here's a concise overview:

## Basic Arithmetic Operations

```csharp
// Addition
int sum = 5 + 3;  // 8

// Subtraction
int difference = 10 - 4;  // 6

// Multiplication
int product = 6 * 7;  // 42

// Division
int quotient = 20 / 4;  // 5
double preciseQuotient = 10.0 / 3.0;  // 3.3333...

// Modulus (remainder)
int remainder = 10 % 3;  // 1
```

## Assignment Operators

```csharp
int x = 10;
x += 5;  // x = x + 5 (value: 15)
x -= 3;  // x = x - 3 (value: 12)
x *= 2;  // x = x * 2 (value: 24)
x /= 4;  // x = x / 4 (value: 6)
x %= 4;  // x = x % 4 (value: 2)
```

## Increment and Decrement

```csharp
int counter = 5;
counter++;  // counter = counter + 1 (value: 6)
counter--;  // counter = counter - 1 (value: 5)

// Prefix vs Postfix
int a = 5;
int b = ++a;  // Increment a first, then assign (a=6, b=6)
int c = 5;
int d = c++;  // Assign first, then increment (c=6, d=5)
```

## Math Class Functions

```csharp
// Constants
double pi = Math.PI;       // 3.141592653589793
double e = Math.E;         // 2.718281828459045

// Basic functions
double absolute = Math.Abs(-10.5);    // 10.5
double rounded = Math.Round(3.7);     // 4.0
double ceiling = Math.Ceiling(3.2);   // 4.0
double floor = Math.Floor(3.8);       // 3.0
double truncated = Math.Truncate(3.8); // 3.0

// Power and roots
double squared = Math.Pow(4, 2);      // 16.0
double cubed = Math.Pow(2, 3);        // 8.0
double squareRoot = Math.Sqrt(16);    // 4.0
double cubeRoot = Math.Pow(27, 1.0/3.0); // 3.0

// Min and Max
int maximum = Math.Max(10, 20);       // 20
int minimum = Math.Min(10, 20);       // 10

// Trigonometric functions (angles in radians)
double sine = Math.Sin(Math.PI / 2);         // 1.0
double cosine = Math.Cos(0);                 // 1.0
double tangent = Math.Tan(Math.PI / 4);      // ~1.0
double arcSine = Math.Asin(1);               // PI/2 radians (90°)
double arcCosine = Math.Acos(0);             // PI/2 radians (90°)
double arcTangent = Math.Atan(1);            // PI/4 radians (45°)

// Converting between degrees and radians
double radians = degrees * Math.PI / 180.0;
double degrees = radians * 180.0 / Math.PI;

// Logarithmic functions
double naturalLog = Math.Log(Math.E);        // 1.0
double customBaseLog = Math.Log(100, 10);    // 2.0
double log10 = Math.Log10(100);              // 2.0
```

## Working with Complex Numbers

```csharp
using System.Numerics;

Complex c1 = new Complex(3, 4);  // 3 + 4i
Complex c2 = new Complex(1, 2);  // 1 + 2i

Complex sum = c1 + c2;           // 4 + 6i
Complex product = c1 * c2;       // -5 + 10i
Complex quotient = c1 / c2;      // 2.2 + 0.4i

double magnitude = Complex.Abs(c1);  // 5
Complex conjugate = Complex.Conjugate(c1);  // 3 - 4i
```

## Numeric Type Conversions

```csharp
int intValue = 42;
double doubleValue = intValue;  // Implicit conversion

double pi = 3.14159;
int intPi = (int)pi;  // Explicit cast: 3
int roundedPi = (int)Math.Round(pi);  // 3

// Safe conversions
long bigNumber = 2147483648;  // Too big for int
if (bigNumber <= int.MaxValue)
{
    int normal = (int)bigNumber;  // Won't execute - would overflow
}
```

## Random Number Generation

```csharp
Random rand = new Random();

// Random integer between 0 and 99
int randomInt = rand.Next(100);

// Random integer between 10 and 20
int randomRange = rand.Next(10, 21);

// Random double between 0.0 and 1.0
double randomDouble = rand.NextDouble();

// Random double between 0.0 and 10.0
double scaledDouble = rand.NextDouble() * 10.0;
```

## Numeric Formatting

```csharp
double value = 123.456789;

// Format as currency
string currency = value.ToString("C");  // $123.46

// Format with specific decimal places
string twoDecimals = value.ToString("F2");  // 123.46

// Scientific notation
string scientific = value.ToString("E");  // 1.234568E+002

// Percent
double percent = 0.1234;
string percentString = percent.ToString("P");  // 12.34%

// Custom format
string custom = value.ToString("#,##0.000");  // 123.457
```

# Conditions in C#

Conditions in C# allow your program to make decisions and execute different code paths based on specific criteria. Here's a concise overview of conditional statements and expressions in C#:

## If Statements

The most basic form of conditional logic:

```csharp
// Simple if statement
if (score >= 70)
{
    Console.WriteLine("You passed!");
}

// If-else statement
if (age >= 18)
{
    Console.WriteLine("You are an adult.");
}
else
{
    Console.WriteLine("You are a minor.");
}

// If-else if-else chain
if (grade >= 90)
{
    Console.WriteLine("You got an A!");
}
else if (grade >= 80)
{
    Console.WriteLine("You got a B!");
}
else if (grade >= 70)
{
    Console.WriteLine("You got a C!");
}
else
{
    Console.WriteLine("You need to improve your grade.");
}

// Nested if statements
if (isLoggedIn)
{
    if (isAdmin)
    {
        Console.WriteLine("Admin dashboard");
    }
    else
    {
        Console.WriteLine("User dashboard");
    }
}
```

## Logical Operators

Combine multiple conditions:

```csharp
// AND operator (&&) - both conditions must be true
if (age >= 18 && hasLicense)
{
    Console.WriteLine("You can drive.");
}

// OR operator (||) - at least one condition must be true
if (isHoliday || isWeekend)
{
    Console.WriteLine("No work today!");
}

// NOT operator (!) - inverts a condition
if (!isAvailable)
{
    Console.WriteLine("Item is out of stock.");
}

// Combined operators with parentheses for clarity
if ((age >= 18 && hasId) || hasParentalConsent)
{
    Console.WriteLine("Entry permitted.");
}
```

## Comparison Operators

Compare values in conditions:

```csharp
// Equal to (==)
if (answer == 42)
{
    Console.WriteLine("Correct answer!");
}

// Not equal to (!=)
if (status != "Complete")
{
    Console.WriteLine("Still processing...");
}

// Greater than (>)
if (temperature > 100)
{
    Console.WriteLine("Water is boiling!");
}

// Less than (<)
if (count < 10)
{
    Console.WriteLine("Need more items.");
}

// Greater than or equal to (>=)
if (score >= 60)
{
    Console.WriteLine("You passed.");
}

// Less than or equal to (<=)
if (discount <= 0.2)
{
    Console.WriteLine("Standard discount.");
}
```

## Conditional (Ternary) Operator

A compact way to write simple if-else statements:

```csharp
// Syntax: condition ? trueResult : falseResult

// Instead of:
string message;
if (age >= 18)
{
    message = "Adult";
}
else
{
    message = "Minor";
}

// You can write:
string message = age >= 18 ? "Adult" : "Minor";

// Can be used in assignments
int fee = isMember ? 10 : 20;

// Can be nested (but avoid excessive nesting for readability)
string category = age < 13 ? "Child" : (age < 20 ? "Teen" : "Adult");
```

## Switch Statements

For multiple branching based on a single value:

```csharp
switch (dayOfWeek)
{
    case "Monday":
        Console.WriteLine("Start of work week");
        break;
    case "Wednesday":
        Console.WriteLine("Midweek");
        break;
    case "Friday":
        Console.WriteLine("TGIF!");
        break;
    case "Saturday":
    case "Sunday":
        Console.WriteLine("Weekend!");
        break;
    default:
        Console.WriteLine("Regular day");
        break;
}

// Switch with expressions (C# 8.0+)
string message = dayOfWeek switch
{
    "Monday" => "Start of work week",
    "Wednesday" => "Midweek",
    "Friday" => "TGIF!",
    "Saturday" or "Sunday" => "Weekend!",
    _ => "Regular day"
};
```

## Null Conditional Operators

Safely access members of potentially null objects:

```csharp
// Null conditional operator (?.)
// Instead of:
string name = null;
if (user != null)
{
    name = user.Name;
}

// You can write:
string name = user?.Name;  // null if user is null

// Can be chained
string city = user?.Address?.City;  // null if user or Address is null

// Null coalescing operator (??)
string displayName = user?.Name ?? "Guest";  // "Guest" if user?.Name is null

```

# Functions in C#

In C#, functions (also called methods) are blocks of code designed to perform specific tasks. They help organize code into reusable units, improve readability, and follow the DRY (Don't Repeat Yourself) principle. Here's a concise overview of functions in C#:

## Basic Method Definition

```csharp
// Method that returns an integer
public int Add(int a, int b)
{
    return a + b;
}

// Method that returns nothing (void)
public void DisplayMessage(string message)
{
    Console.WriteLine(message);
}

// Calling methods
int sum = Add(5, 3);       // sum = 8
DisplayMessage("Hello!");  // Prints: Hello!
```

# Access Modifiers in C#

Access modifiers control the **visibility** and **accessibility** of classes, methods, and other members in your code. They define **who** can access certain parts of your program.

## Common Access Modifiers

1. **public**
   - Accessible from anywhere in the program.
   - No restrictions on access.

2. **private**
   - Accessible **only** within the class or struct where it is declared.
   - The most restrictive modifier.
   - Used to hide implementation details.

3. **protected**
   - Accessible within the class and by derived (child) classes.
   - Useful for inheritance scenarios.

4. **internal**
   - Accessible only within the **same assembly** (project).
   - Useful to limit access to code within the same compiled DLL or EXE.

5. **protected internal**
   - Accessible from derived classes **or** any code within the same assembly.
   - A combination of protected and internal.

6. **private protected** (introduced in C# 7.2)
   - Accessible only within the containing class or types derived from the containing class, but only within the same assembly.

## Why use access modifiers?

- To **encapsulate** data and implementation.
- To enforce **security** and **abstraction**.
- To reduce unintended **dependencies** between components.

```csharp
public int PublicMethod()      // Accessible from anywhere
private int PrivateMethod()    // Accessible only within the same class
protected int ProtectedMethod() // Accessible within the class and derived classes
internal int InternalMethod()  // Accessible within the same assembly
```

## Parameters:
```csharp
// Required parameters
public double CalculateArea(double length, double width)
{
    return length * width;
}
// Optional parameters with default values
public string Greet(string name, string greeting = "Hello")
{
    return $"{greeting}, {name}!";
}
// Usage: Greet("John") -> "Hello, John!"
// Usage: Greet("John", "Hi") -> "Hi, John!"

// Named parameters
CalculateArea(width: 5.0, length: 10.0);  // Order doesn't matter with named parameters

// Variable number of parameters (params)
public int Sum(params int[] numbers)
{
    int total = 0;
    foreach (int num in numbers)
    {
        total += num;
    }
    return total;
}
// Usage: Sum(1, 2, 3, 4) -> 10
```

## Return Values

```csharp
// Single return value
public double GetAverage(int[] numbers)
{
    double sum = 0;
    foreach (int num in numbers)
    {
        sum += num;
    }
    return sum / numbers.Length;
}

// Multiple return values using tuple (C# 7.0+)
public (int Min, int Max) GetRange(int[] numbers)
{
    return (numbers.Min(), numbers.Max());
}
// Usage:
var result = GetRange(new[] { 3, 1, 7, 9 });
Console.WriteLine($"Min: {result.Min}, Max: {result.Max}");  // Min: 1, Max: 9

// Using out parameters for multiple returns (older style)
public bool TryParse(string input, out int result)
{
    return int.TryParse(input, out result);
}
// Usage:
if (TryParse("123", out int number))
{
    Console.WriteLine($"Parsed: {number}");
}
```

## Method Overloading

Defining multiple methods with the same name but different parameters:

```csharp
public int Add(int a, int b)
{
    return a + b;
}

public double Add(double a, double b)
{
    return a + b;
}

public string Add(string a, string b)
{
    return a + b;
}

// Usage:
int sum1 = Add(5, 3);           // Calls the first method
double sum2 = Add(5.2, 3.8);    // Calls the second method
string combined = Add("Hello ", "World"); // Calls the third method
```

## Expression-Bodied Methods (C# 6.0+)

Concise syntax for simple methods:

```csharp
// Instead of:
public int Multiply(int a, int b)
{
    return a * b;
}

// You can write:
public int Multiply(int a, int b) => a * b;

// Works for void methods too:
public void Log(string message) => Console.WriteLine($"[LOG]: {message}");
```

## Extension Methods

Add methods to existing types without modifying them:

```csharp
// Must be in a static class
public static class StringExtensions
{
    // 'this' keyword before the first parameter identifies this as an extension method
    public static bool IsNullOrEmpty(this string text)
    {
        return string.IsNullOrEmpty(text);
    }

    public static string Truncate(this string text, int maxLength)
    {
        return text?.Length > maxLength ? text.Substring(0, maxLength) : text;
    }
}

// Usage:
string name = "Alexander";
bool isEmpty = name.IsNullOrEmpty();  // false
string shortened = name.Truncate(5);  // "Alexa"
```

## Lambda Expressions

Concise way to define unnamed functions:

```csharp
// Expression lambda (returns a value)
Func<int, int, int> add = (a, b) => a + b;
int sum = add(5, 3);  // 8

// Statement lambda (can have multiple statements)
Func<int, int> factorial = n =>
{
    int result = 1;
    for (int i = 1; i <= n; i++)
        result *= i;
    return result;
};
int fact5 = factorial(5);  // 120

// Action lambda (returns void)
Action<string> print = message => Console.WriteLine(message);
print("Hello World!");  // Prints: Hello World!
```

## Recursive Functions

Functions that call themselves:

```csharp
public int Factorial(int n)
{
    // Base case
    if (n <= 1)
        return 1;

    // Recursive case
    return n * Factorial(n - 1);
}

// Usage:
int result = Factorial(5);  // 5 * 4 * 3 * 2 * 1 = 120
```

## Async Methods

For asynchronous operations:

```csharp
public async Task<string> DownloadWebPageAsync(string url)
{
    using (HttpClient client = new HttpClient())
    {
        return await client.GetStringAsync(url);
    }
}

// Usage:
string content = await DownloadWebPageAsync("https://example.com");
```
---
# Object-Oriented Programming (OOP) in C#

Object-Oriented Programming is a programming paradigm built around the concept of "objects" that contain data and behavior. C# is a powerful OOP language that fully supports the four main pillars of OOP:

## 1. Abstraction

Abstraction focuses on hiding complex implementation details and showing only the necessary features of an object.

```csharp
// Abstract class example
public abstract class Vehicle
{
    public string Make { get; set; }
    public string Model { get; set; }
    
    // Abstract method (must be implemented by derived classes)
    public abstract void StartEngine();
    
    // Regular method with implementation
    public void StopEngine()
    {
        Console.WriteLine("Engine stopped");
    }
}

// Interface example
public interface IVehicle
{
    void Drive();
    int FuelLevel { get; }
}


