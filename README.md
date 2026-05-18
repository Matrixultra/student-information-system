# 📚 Student Information System — Java

A menu-driven console application to manage student records with full CRUD
operations, input validation, and formatted output.

---

## 🗂 Project Structure

```
StudentInfoSystem/
├── src/
│   ├── Student.java                  # Student entity class
│   ├── StudentManager.java           # Business logic (CRUD + search)
│   ├── ValidationUtils.java          # Input validation helpers
│   └── StudentInformationSystem.java # Main program (menu interface)
├── docs/
│   └── USER_GUIDE.md
├── test_data/
│   └── sample_students.txt
└── README.md
```

---

## ⚙️ Setup & Run

### Prerequisites
- JDK 17 or later  
- Any IDE (VS Code, IntelliJ IDEA, Eclipse) **or** a terminal

### Compile & Run (Terminal)

```bash
# From the project root
mkdir -p out
javac src/*.java -d out/
java -cp out StudentInformationSystem
```

### Run in IntelliJ IDEA
1. Open the `src/` folder as a project
2. Right-click `StudentInformationSystem.java` → **Run**

---

## 🧩 Features

| Feature           | Description                                      |
|-------------------|--------------------------------------------------|
| Add Student       | Collects and validates all fields before saving  |
| View All          | Formatted table listing every student            |
| Search by ID      | Exact match lookup — returns full details        |
| Search by Name    | Partial / case-insensitive name search           |
| Update Record     | Edit any individual field of an existing student |
| Delete Student    | Confirmation prompt before removal              |
| Auto-ID           | IDs assigned automatically (STU001, STU002, …)  |
| Sample Data       | 5 students loaded on first launch                |

---

## ✅ Validation Rules

| Field   | Rule                                                              |
|---------|-------------------------------------------------------------------|
| Name    | Letters, spaces, hyphens, apostrophes only                        |
| Age     | Integer between 3 and 25                                          |
| Grade   | K, 1–12, or 1A–12B (e.g. "10A")                                  |
| Email   | Standard format (user@domain.tld)                                 |
| Phone   | 10 digits, optional `+countrycode` prefix                         |

---

## 📖 Class Diagram

```
StudentInformationSystem (main)
        │
        ├──uses──► StudentManager
        │               │
        │               └──stores──► ArrayList<Student>
        │
        ├──uses──► ValidationUtils
        │
        └──uses──► Student
```

---

## 🛣 Extension Ideas (Advanced)

1. **File Persistence** — save ArrayList to a `.csv` or `.dat` file using `FileWriter` / `ObjectOutputStream`
2. **Sort & Filter** — sort by name, grade, or age; filter by grade
3. **Statistics** — average age, students per grade
4. **GUI** — wrap the logic in a Java Swing or JavaFX front-end
