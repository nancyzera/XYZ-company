---

# 📘 XYZ School Management System

##  Overview

**XYZ School Management System** is a digital solution designed to help schools **manage students, professors, classrooms, and subjects efficiently**.
This system provides a structured interaction between students and professors through subjects and class assignments — allowing smooth academic organization.

---

## 🏫 System Purpose

The objective of this system is to:

* Maintain student information
* Manage professor information
* Track subjects assigned to professors
* Maintain class data and the subjects taught in each class
* Improve organization between students, classes, and academic staff

---

##  Core Entities & Attributes

Below are the main database entities used in the system:

---

### 1️ **Class**

Represents a class or academic group.

| Attribute   | Description                                        |
| ----------- | -------------------------------------------------- |
| classID     | Unique identifier for the class                    |
| classCode   | Class name/code e.g., S6-MPC, L3NIT                |
| beginDate   | Starting date of the class                         |
| endDate     | Ending date of that academic period                |
| subjectID   | Foreign key mapping subject assigned to that class |
| professorID | Foreign key mapping professor handling the class   |

---

### 2️ **Student**

| Attribute    | Description                    |
| ------------ | ------------------------------ |
| studentID    | Unique identifier of a student |
| studentName  | Full name of student           |
| studentEmail | Email address of student       |
| studentPhone | Contact number                 |
| birthDate    | Student's date of birth        |

---

### 3️ **Professor**

| Attribute      | Description                      |
| -------------- | -------------------------------- |
| professorID    | Unique identifier of a professor |
| professorName  | Professor full name              |
| professorEmail | Email address                    |
| professorPhone | Contact number                   |

---

### 4️ **ProfessorSubject**

Represents subject allocation to professors.

| Attribute          | Description                   |
| ------------------ | ----------------------------- |
| professorSubjectID | Record identifier             |
| professorID        | FK referencing professor      |
| subjectID          | FK referencing subject taught |

---

### 5️ **Subject**

| Attribute   | Description                                     |
| ----------- | ----------------------------------------------- |
| subjectID   | Unique ID of the subject                        |
| subjectName | Name of the subject (e.g. Mathematics, English) |

---

##  System Architecture (Basic)

```mermaid
erDiagram
    CLASS ||--o{ STUDENT : "belongs to"
    CLASS ||--o{ SUBJECT : "teaches"
    PROFESSOR ||--o{ PROFESSORSUBJECT : "teaches"
    SUBJECT ||--o{ PROFESSORSUBJECT : "assigned"
    
    CLASS {
        int classID
        string classCode
        date beginDate
        date endDate
        int subjectID
        int professorID
    }

    STUDENT {
        int studentID
        string studentName
        string studentEmail
        string studentPhone
        date birthDate
    }

    PROFESSOR {
        int professorID
        string professorName
        string professorEmail
        string professorPhone
    }

    PROFESSORSUBJECT {
        int professorSubjectID
        int professorID
        int subjectID
    }

    SUBJECT {
        int subjectID
        string subjectName
    }
```

---

##  Features (current & planned)

| Feature                           | Status |
| --------------------------------- | ------ |
| Student registration & management | ✔      |
| Professor information handling    | ✔      |
| Subject assignment to professors  | ✔      |
| Class creation & scheduling       | ✔      |
| Reporting system (future)         | ⏳      |
| Timetable automation (future)     | ⏳      |
| Attendance & grading (future)     | ⏳      |

---

##  Technology Suggestions 

You can build this using:

| Layer    | Technology Example                                 |
| -------- | -------------------------------------------------- |
| Backend  | Python Flask / Node.js / PHP Laravel / Java Spring |
| Frontend | HTML/CSS/JS / React / Vue / Angular                |
| Database | MySQL / PostgreSQL / SQLite                        |

---

##  Suggested Folder Structure

```
XYZ-School-Management-System/
 ├── backend/
 ├── frontend/
 ├── docs/
 │    ├── ERD.md
 │    ├── API_DOCS.md
 ├── README.md
```

---


