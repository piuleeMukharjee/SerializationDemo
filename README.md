Practical 5 – Java Programs
📌 Overview

This submission contains three Java programs that demonstrate key concepts in Java programming:

Autoboxing and Unboxing → Conversion between primitive types and wrapper classes.

File Handling with Employee Management System → Reading/writing employee records using text files.

Serialization and Deserialization → Saving and restoring Java objects using the Serializable interface.

1️⃣ AutoboxingSum
📄 Description

This program demonstrates autoboxing (primitive to wrapper conversion) and unboxing (wrapper to primitive conversion) while calculating the sum of integers parsed from strings.

🖥️ Code Snippet
String[] stringInputs = { "10", "25", "42", "100", "5" };
List<Integer> integerList = new ArrayList<>();

for (String str : stringInputs) {
    int primitiveInt = Integer.parseInt(str);
    integerList.add(primitiveInt); // autoboxing
}

int totalSum = 0;
for (Integer wrapperInt : integerList) {
    totalSum += wrapperInt; // unboxing
}

System.out.println("Final Sum of all integers is: " + totalSum);

✅ Sample Output
Final Sum of all integers is: 182

2️⃣ EmployeeManagementSystem
📄 Description

A simple console-based Employee Management System that uses file handling to:

Add new employee records

Display all employee records

Exit the application

🖥️ Features

Uses FileWriter and BufferedWriter for writing data.

Uses FileReader and BufferedReader for reading data.

Displays records in a formatted table.

Handles invalid inputs and missing files.

✅ Sample Run

Adding an Employee

--- Add New Employee ---
Enter Employee ID: 101
Enter Employee Name: Alice Johnson
Enter Designation: Software Engineer
Enter Salary: 55000
Employee record added successfully!


Displaying Employees

--- All Employee Records ---
ID         | Name                 | Designation         | Salary    
-------------------------------------------------------------------
101        | Alice Johnson        | Software Engineer   | 55000.00

3️⃣ SerializationDemo
📄 Description

This program demonstrates serialization (saving an object to a file) and deserialization (retrieving it back).

🖥️ Code Snippet
Student studentToWrite = new Student(101, "Ayush", 'A');

// Serialization
try (ObjectOutputStream objOut = new ObjectOutputStream(new FileOutputStream("student.ser"))) {
    objOut.writeObject(studentToWrite);
    System.out.println("Student object has been serialized successfully.");
}

// Deserialization
try (ObjectInputStream objIn = new ObjectInputStream(new FileInputStream("student.ser"))) {
    Student studentToRead = (Student) objIn.readObject();
    System.out.println("Retrieved Data: " + studentToRead);
}

✅ Sample Output
Student object has been serialized successfully.
Student object has been deserialized successfully.
Retrieved Data: Student [ID=101, Name=Ayush, Grade=A]

📂 Project Structure
Practical5/
│
├── AutoboxingSum.java            # Program 1 - Autoboxing & Unboxing
├── EmployeeManagementSystem.java # Program 2 - File Handling
├── SerializationDemo.java        # Program 3 - Serialization & Deserialization
├── employees.txt                 # Data file for EMS (auto-created)
├── student.ser                   # Serialized student file (auto-created)
└── README.md                     # Documentation

🔑 Key Learning Outcomes

Autoboxing & Unboxing → Simplifies primitive-wrapper conversions.

File Handling in Java → Reading/writing structured text data.

Serialization & Deserialization → Persisting and restoring Java objects.

Exception Handling → Handling invalid inputs, missing files, and I/O errors.
