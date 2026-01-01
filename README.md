<a id="readme-top"></a>

[![Contributors][contributors-shield]][contributors-url]
[![Forks][forks-shield]][forks-url]
[![Stargazers][stars-shield]][stars-url]
[![Issues][issues-shield]][issues-url]
[![License][license-shield]][license-url]

<br />
<div align="center">
  <h3 align="center">Library Management System</h3>

  <p align="center">
    A comprehensive library management system built in x86 Assembly Language
    <br />
    <strong>Property of FAST-NUCES</strong>
    <br />
    <br />
    <a href="https://github.com/sidhartsami/Library-Management-System"><strong>Explore the docs »</strong></a>
    <br />
    <br />
    <a href="https://github.com/sidhartsami/Library-Management-System">View Demo</a>
    ·
    <a href="https://github.com/sidhartsami/Library-Management-System/issues/new?labels=bug&template=bug-report---.md">Report Bug</a>
    ·
    <a href="https://github.com/sidhartsami/Library-Management-System/issues/new?labels=enhancement&template=feature-request---.md">Request Feature</a>
  </p>
</div>

<details>
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#about-the-project">About The Project</a>
      <ul>
        <li><a href="#built-with">Built With</a></li>
        <li><a href="#key-features">Key Features</a></li>
      </ul>
    </li>
    <li>
      <a href="#getting-started">Getting Started</a>
      <ul>
        <li><a href="#prerequisites">Prerequisites</a></li>
        <li><a href="#installation">Installation</a></li>
      </ul>
    </li>
    <li><a href="#usage">Usage</a></li>
    <li><a href="#system-architecture">System Architecture</a></li>
    <li><a href="#contributing">Contributing</a></li>
    <li><a href="#license">License</a></li>
    <li><a href="#contact">Contact</a></li>
    <li><a href="#acknowledgments">Acknowledgments</a></li>
  </ol>
</details>

## About The Project

The Library Management System is a sophisticated application built entirely in x86 Assembly Language using the Irvine32 library. This system demonstrates low-level programming concepts while providing a full-featured library management solution with separate interfaces for librarians and customers.

The system manages up to 50 books and 50 students, providing comprehensive functionality for book rental, inventory management, and student registration. With an engaging ASCII art interface and color-coded terminal output, the application showcases the power of assembly language in creating user-friendly applications.

### Key Features

**Librarian Functions:**
- **Book Management**: Add new books with title, author, ISBN, and quantity
- **Update Operations**: Modify book titles, author names, and available quantities
- **Inventory Tracking**: View complete library information and individual book details
- **Student Registration**: Register new students with unique IDs and names
- **Duplicate Prevention**: Automatic detection of duplicate student IDs

**Customer Functions:**
- **Secure Login**: ID-based authentication system
- **Book Rental**: Rent available books with automatic inventory updates
- **Return System**: Return rented books with quantity restoration
- **Rental Limits**: One-book-per-student policy enforcement
- **Real-time Availability**: Dynamic checking of book copies

**Technical Features:**
- Array-based data structures for efficient memory management
- String comparison algorithms for book searching
- Dynamic memory offset calculations
- Animated welcome screen with ASCII art
- Color-coded terminal interface
- Input validation and error handling

<p align="right">(<a href="#readme-top">back to top</a>)</p>

### Built With

* [![Assembly][Assembly-badge]][Assembly-url]
* **Irvine32 Library** - For I/O operations and utilities
* **MASM (Microsoft Macro Assembler)** - Assembly compiler
* **x86 Architecture** - 32-bit instruction set

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Getting Started

### Prerequisites

To run this assembly program, you need:

* **MASM32** - Microsoft Macro Assembler
  ```
  Download from: http://www.masm32.com/
  ```
* **Irvine32 Library** - Required for I/O procedures
  ```
  Included with most assembly development environments
  ```
* **Visual Studio** (Optional) - For integrated development
* **Windows Operating System** - Required for Irvine32 library

### Installation

1. Clone the repository
   ```sh
   git clone https://github.com/sidhartsami/Library-Management-System.git
   ```

2. Navigate to the project directory
   ```sh
   cd Library-Management-System
   ```

3. Ensure Irvine32 library is in your include path
   ```
   Place Irvine32.inc and Irvine32.lib in your MASM directory
   ```

4. Assemble and link the program
   ```sh
   ml /c /coff library.asm
   link /subsystem:console library.obj Irvine32.lib kernel32.lib
   ```

5. Run the executable
   ```sh
   library.exe
   ```

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Usage

### Starting the System

When you launch the program, you'll see an animated ASCII art welcome screen displaying:
- Animated countdown (3, 2, 1)
- Welcome message with FAST-NUCES branding
- User type selection prompt

### User Selection

**Option 1: Librarian Mode**
```
Enter: 1
Access to all administrative functions
```

**Option 2: Customer Mode**
```
Enter: 2
Access to student login and book rental/return
```

### Librarian Operations

**Menu Options:**
1. **Add Book** - Add a new book to the library
   - Enter book title (up to 50 characters)
   - Enter author name (up to 50 characters)
   - Enter ISBN (numeric)
   - Enter initial quantity

2. **Update Book Info** - Modify existing book details
   - Option 1: Update book title
   - Option 2: Update author name
   - Option 3: Update quantity
   - Search by ISBN

3. **Display Library Track Info** - View all books in the system
   - Shows title, author, and available quantity for each book

4. **Display Book Info** - View specific book details
   - Search by ISBN
   - Displays complete book information

5. **Register Student** - Add a new student
   - Enter unique student ID
   - Enter student name
   - Automatic duplicate ID prevention

6. **Close Library** - Exit the application

### Customer Operations

**Login Process:**
```
Enter your Student ID when prompted
System verifies ID against registered students
Upon success, access rental functions
```

**Menu Options:**
1. **Return Book** - Return a rented book
   - Automatically identifies your rented book
   - Updates inventory quantity
   - Displays confirmation

2. **Rent Book** - Rent an available book
   - Enter exact book title
   - System checks availability
   - Enforces one-book-per-student limit
   - Updates inventory automatically

3. **Log Out** - Return to main menu

### Example Workflow

```assembly
# Launch Program
./library.exe

# Librarian adds books
Select: 1 (Librarian)
Choose: 1 (Add Book)
Title: "Introduction to Assembly"
Author: "Kip Irvine"
ISBN: 12345
Quantity: 5

# Register students
Choose: 5 (Register Student)
ID: 1001
Name: "Alice Johnson"

# Student rents book
Select: 2 (Customer)
Enter ID: 1001
Choose: 2 (Rent Book)
Enter Title: "Introduction to Assembly"
[Book rented successfully!]

# Student returns book
Choose: 1 (Return Book)
[Book Returned Successfully]
```

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## System Architecture

### Data Structures

**Book Management:**
```assembly
MAX_BOOKS = 50
BookTitles: Array of 50 strings (50 bytes each)
BookAuthors: Array of 50 strings (50 bytes each)
BookISBNs: Array of 50 DWORDs
Quantity: Array of 50 DWORDs
BookUsedStatus: Array tracking availability
```

**Student Management:**
```assembly
MAX_STUDENTS = 50
StudentIDs: Array of 50 DWORDs
StudentNames: Array of 50 strings (50 bytes each)
Alotted: Array tracking rentals per student
```

### Core Algorithms

**String Comparison:**
- Uses `repe cmpsb` instruction for efficient byte-by-byte comparison
- Compares book titles for rental/return operations
- Case-sensitive matching

**Array Indexing:**
- Dynamic offset calculation: `index * element_size`
- Efficient memory access using base + offset addressing
- Separate arrays for parallel data storage

**Search Operations:**
- Linear search through ISBN array
- O(n) complexity with early termination
- Index preservation for related array access

**Inventory Management:**
- Decrement quantity on rental
- Increment quantity on return
- Zero-check for availability validation

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Contributing

Contributions are what make the open source community such an amazing place to learn, inspire, and create. Any contributions you make are **greatly appreciated**.

If you have a suggestion that would make this better, please fork the repo and create a pull request. You can also simply open an issue with the tag "enhancement".

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

### Contributors

- **Sidhart Sami** - *Project Lead & Core Implementation*
- **Aliyan Munawwar** - *Book Management System*
- **Zubair Ahmed** - *Customer Interface & Rental Logic*

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## License

Distributed under the MIT License. See `LICENSE.txt` for more information.

**Property of FAST-NUCES**

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Contact

Sidhart Sami - [@sidhartsami](https://github.com/sidhartsami)

Project Link: [https://github.com/sidhartsami/Library-Management-System](https://github.com/sidhartsami/Library-Management-System)

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Acknowledgments

- [Irvine32 Library](http://asmirvine.com/) - Essential I/O procedures for assembly
- [MASM32 SDK](http://www.masm32.com/) - Development environment
- [x86 Assembly Guide](https://www.cs.virginia.edu/~evans/cs216/guides/x86.html) - Reference documentation
- [Intel Developer Manual](https://www.intel.com/content/www/us/en/developer/articles/technical/intel-sdm.html) - Instruction set reference
- [FAST-NUCES](https://www.nu.edu.pk/) - Academic institution

<p align="right">(<a href="#readme-top">back to top</a>)</p>

[contributors-shield]: https://img.shields.io/github/contributors/sidhartsami/Library-Management-System.svg?style=for-the-badge
[contributors-url]: https://github.com/sidhartsami/Library-Management-System/graphs/contributors
[forks-shield]: https://img.shields.io/github/forks/sidhartsami/Library-Management-System.svg?style=for-the-badge
[forks-url]: https://github.com/sidhartsami/Library-Management-System/network/members
[stars-shield]: https://img.shields.io/github/stars/sidhartsami/Library-Management-System.svg?style=for-the-badge
[stars-url]: https://github.com/sidhartsami/Library-Management-System/stargazers
[issues-shield]: https://img.shields.io/github/issues/sidhartsami/Library-Management-System.svg?style=for-the-badge
[issues-url]: https://github.com/sidhartsami/Library-Management-System/issues
[license-shield]: https://img.shields.io/github/license/sidhartsami/Library-Management-System.svg?style=for-the-badge
[license-url]: https://github.com/sidhartsami/Library-Management-System/blob/master/LICENSE.txt
[Assembly-badge]: https://img.shields.io/badge/Assembly-654FF0?style=for-the-badge&logo=assembly&logoColor=white
[Assembly-url]: https://en.wikipedia.org/wiki/Assembly_language
