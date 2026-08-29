# 📚 Library Management System

A **console-based Library Management System developed using C programming**. This project provides separate interfaces for **Librarians** and **Students**, allowing users to efficiently manage and search books through a simple menu-driven console application.

The project is designed to demonstrate important **C programming fundamentals**, including structures, arrays, functions, string handling, searching, updating, deletion, loops, conditional statements, and modular programming.

---

## 📌 Project Overview

The Library Management System allows a librarian to manage the library's book collection, while students can view and search for available books.

The system contains two types of users:

* 👨‍💼 **Librarian**
* 🎓 **Student**

Each user has a separate login and menu with appropriate functionalities.

---

## ✨ Features

### 👨‍💼 Librarian Features

The librarian has complete control over the library records.

* 🔐 Librarian Login
* ➕ Add a new book
* 📖 View all books
* 🔍 Search books by ID
* 🔍 Search books by title
* ✏️ Update book title
* ✏️ Update book author
* 🗑️ Delete a book
* 🚪 Logout

### 🎓 Student Features

Students have limited access to the library records.

* 🔐 Student Login
* 📖 View all available books
* 🔍 Search books by ID
* 🔍 Search books by title
* 🚪 Logout

---

## 🏗️ Project Structure

The program is organized into different functional modules:

```text
Library Management System
│
├── Book Structure
│   ├── Book ID
│   ├── Book Title
│   └── Book Author
│
├── Student Module
│   ├── Display Module
│   ├── View Module
│   ├── Search Module
│   ├── Login Module
│   └── Menu Module
│
├── Librarian Module
│   ├── Display Module
│   ├── Add Book Module
│   ├── Search Module
│   ├── Delete Module
│   ├── Update Module
│   └── Login & Menu Module
│
└── Main Program
```

---

## 🧩 Modules

### 1. Book Structure

The project uses a C `struct` to represent a book.

```c
struct Book {
    int id;
    char title[50];
    char author[50];
};
```

Each book contains:

* **ID** – Unique identifier for the book
* **Title** – Name of the book
* **Author** – Author of the book

The library can store up to **100 books**.

---

### 2. Student Display Module

Responsible for displaying book information in a formatted manner.

Functions:

* `printLine()`
* `printHeader()`
* `printBook()`

---

### 3. Student View Module

Allows students to view all books available in the library.

Functions:

* `isLibraryEmpty()`
* `displayAllBooks()`
* `viewBooksModule()`

If there are no books, the system displays:

```text
No books available.
```

---

### 4. Student Search Module

Students can search for books using:

* Book ID
* Book Title

Functions:

* `searchBookById()`
* `searchBookByTitle()`
* `searchBookModule()`

---

### 5. Student Login Module

Provides authentication for students.

Default credentials:

```text
Username: student
Password: 111
```

Functions:

* `getUsername()`
* `getPassword()`
* `studentLogin()`

---

### 6. Student Menu Module

Provides the student with the following options:

```text
===== STUDENT MENU =====
1. View Books
2. Search Book
3. Logout
```

Functions:

* `showStudentMenuOptions()`
* `processStudentChoice()`
* `studentMenu()`

---

### 7. Librarian Display Module

Provides formatted output for librarian operations.

Functions:

* `libPrintLine()`
* `libPrintHeader()`
* `libPrintBook()`

---

### 8. Librarian Add Book Module

Allows the librarian to add new books to the library.

The system checks whether the entered Book ID is already present before adding the book.

Functions:

* `getBookDetails()`
* `isUniqueId()`
* `addBookModule()`

---

### 9. Librarian Search Module

The librarian can search for books using:

* Book ID
* Book Title

Functions:

* `libSearchById()`
* `libSearchByTitle()`
* `searchBookModuleAdmin()`

---

### 10. Librarian Delete Module

Allows the librarian to delete a book using its ID.

Functions:

* `getBookIndex()`
* `shiftLeft()`
* `deleteBookModule()`

When a book is deleted, the remaining books are shifted to fill the empty position in the array.

---

### 11. Librarian Update Module

Allows the librarian to modify book information.

The librarian can update:

* Book Title
* Book Author

Functions:

* `updateBookTitle()`
* `updateBookAuthor()`
* `updateBookModule()`

---

### 12. Librarian Login & Menu Module

Provides authentication and menu functionality for librarians.

Default credentials:

```text
Username: admin
Password: 123
```

Librarian menu:

```text
===== LIBRARIAN MENU =====
1. Add Book
2. View Books
3. Search Book
4. Delete Book
5. Update Book
6. Logout
```

---

## 🔐 Login Credentials

For demonstration purposes, the application contains predefined login credentials.

| User Type | Username  | Password |
| --------- | --------- | -------- |
| Librarian | `admin`   | `123`    |
| Student   | `student` | `111`    |

> ⚠️ These credentials are hardcoded for educational purposes and should not be used for a production system.

---

## 🖥️ Main Menu

When the application starts, the following menu is displayed:

```text
====== MAIN MENU ======
1. Librarian Login
2. Student Login
3. Exit

Enter your choice:
```

### Option 1 – Librarian Login

Allows the librarian to log in and access management features.

### Option 2 – Student Login

Allows students to log in and access viewing and searching features.

### Option 3 – Exit

Terminates the application.

---

## 🔄 Application Flow

```text
                 ┌─────────────────┐
                 │   Start Program  │
                 └────────┬────────┘
                          │
                          ▼
                 ┌─────────────────┐
                 │    Main Menu    │
                 └────────┬────────┘
                          │
             ┌────────────┼────────────┐
             │            │            │
             ▼            ▼            ▼
       Librarian       Student        Exit
         Login          Login
             │            │
             ▼            ▼
      Librarian Menu  Student Menu
             │            │
       ┌─────┼─────┐    ┌─┴─────────┐
       │     │     │    │           │
       ▼     ▼     ▼    ▼           ▼
      Add   View  Search View      Search
      │      │     │     │           │
      ▼      ▼     ▼     ▼           ▼
    Delete Update  ...  Logout      Logout
```

---

## 💻 Technologies Used

| Technology             | Purpose                           |
| ---------------------- | --------------------------------- |
| C                      | Core programming language         |
| Structures             | Represent book information        |
| Arrays                 | Store multiple books              |
| Functions              | Modular program design            |
| `strcmp()`             | Compare strings                   |
| Loops                  | Iterate through book records      |
| Conditional Statements | Decision making                   |
| Pointers               | Pass book structures to functions |
| Console I/O            | User interaction                  |

---

## 🧠 C Concepts Demonstrated

This project covers several fundamental C programming concepts:

### Structures

Used to create a custom data type for storing book details.

```c
struct Book
```

### Arrays

Books are stored in an array:

```c
struct Book library[100];
```

### Global Variables

The program maintains the current number of books using:

```c
int count = 0;
```

### Functions

The application is divided into multiple functions to improve readability and maintainability.

### Pointers

Pointers are used when entering book details:

```c
void getBookDetails(struct Book *b)
```

### String Handling

The program uses:

```c
strcmp()
```

to compare usernames, passwords, and book titles.

### Searching

The program performs linear searching through the book array.

### Updating

Book information can be modified directly using its array index.

### Deletion

When a book is deleted, subsequent elements are shifted left.

---

## ⚙️ Requirements

To run this project, you need:

* A C compiler
* GCC / MinGW / Clang
* Windows, Linux, or macOS
* A terminal or command prompt

Recommended:

```text
GCC
```

---

## 🚀 How to Run

### 1. Clone the Repository

```bash
git clone https://github.com/Dheveshwar-K/Library-Management-System.git
```

### 2. Navigate to the Project Directory

```bash
cd Library-Management-System
```

### 3. Compile the Program

If the source file is named `library.c`:

```bash
gcc library.c -o library
```

### 4. Run the Program

#### Windows

```bash
library.exe
```

or:

```bash
.\library.exe
```

#### Linux/macOS

```bash
./library
```

---

## 📖 Example Usage

### Main Menu

```text
====== MAIN MENU ======
1. Librarian Login
2. Student Login
3. Exit

Enter your choice: 1
```

### Librarian Login

```text
--- Librarian Login ---
Username: admin
Password: 123
```

After successful login:

```text
===== LIBRARIAN MENU =====
1. Add Book
2. View Books
3. Search Book
4. Delete Book
5. Update Book
6. Logout
```

### Adding a Book

```text
Enter Book ID: 101
Enter Book Title: C Programming
Enter Author Name: Dennis Ritchie

Book added successfully!
```

### Viewing Books

```text
-------------------------------------------------
 ID              Title           Author
-------------------------------------------------
 101             C Programming   Dennis Ritchie
```

### Searching a Book

```text
Search by:
1. ID
2. Title

Enter choice: 1

Enter Book ID: 101
```

If found:

```text
-------------------------------------------------
 ID              Title           Author
-------------------------------------------------
 101             C Programming   Dennis Ritchie
```

### Deleting a Book

```text
Enter Book ID to delete: 101

Book deleted successfully!
```

---

## 📊 Data Storage

Currently, book information is stored in an **in-memory array**:

```c
struct Book library[100];
```

This means:

* Maximum capacity: **100 books**
* Data is available only while the program is running
* Data is lost when the program terminates
* No external database or file storage is currently used

---

## ⚠️ Current Limitations

This project is intended for learning and demonstration purposes.

Current limitations include:

1. Book data is not permanently stored.
2. Maximum of 100 books can be stored.
3. Login credentials are hardcoded.
4. Password input is visible in the console.
5. There is no database integration.
6. There is no graphical user interface.
7. Input validation can be improved.
8. Book titles and author names have a fixed maximum length.

---

## 🔮 Future Improvements

The project can be extended with:

* 💾 File handling for permanent data storage
* 🗄️ Database integration
* 🔐 Secure password handling
* 👥 Multiple student accounts
* 👨‍💼 Multiple librarian accounts
* 📅 Book issue and return functionality
* ⏰ Due-date tracking
* 💰 Fine calculation
* 📊 Library statistics
* 🔎 Advanced search and filtering
* 🖥️ Graphical user interface
* 🌐 Web-based library management system
* 🔌 REST API integration

---

## 🎯 Learning Objectives

The main objectives of this project are:

* Understand C structures
* Practice functions and modular programming
* Work with arrays of structures
* Implement searching algorithms
* Implement insertion and deletion operations
* Practice string manipulation
* Understand pointers
* Build menu-driven console applications
* Implement basic authentication
* Organize a larger C program into logical modules

---

## 👨‍💻 Author

**Dheveshwar K**

GitHub:

**Dheveshwar-K**

---

## 📜 License

This project is created for **educational and learning purposes**.

You are free to modify and extend the project for your own learning and academic projects.

---

## ⭐ Support

If you find this project useful, consider giving the repository a ⭐ on GitHub.
