# 🐍 Python for Data Engineering: The Complete ETL Framework

This repository contains a modular ETL (Extract, Transform, Load) pipeline built to master Python fundamentals through practical Data Engineering concepts.

Each file represents a specific learning block from the Python for Data Engineering Masterclass, progressing from scripting basics to enterprise-level architecture and performance optimization.

---

# 🏗 Project Architecture & Detailed Phases

## 🔹 Phase 1: Environment & File System Discovery

**Technical Focus:**  
os module, Variables, F-Strings

### 🎯 Core Concept

In Data Engineering, we avoid hardcoding.

Instead of:

```
data.csv
```

We dynamically generate file paths using:

- Variables
- F-Strings
- Current date logic

### 🛠 Key Tools

- `os.path.exists()` → Check if landing zone exists
- `os.makedirs()` → Create missing directories
- `os.path.join()` → Cross-platform safe path building (Windows/Linux compatible)

💡 **DE Pro-Tip:**  
Always use `os.path.join()` instead of string concatenation to ensure cloud compatibility.

---

## 🔹 Phase 2: Data Ingestion & Stream Logic

**Technical Focus:**  
Lists, Sets, Dictionaries, List Comprehension, Iterables, Infinite Loops

### 🎯 Core Concept

Real-world data behaves like a stream.

We simulate this using:

```python
while True:
```

### 🔍 Key Techniques

**Filtering:**  
Use List Comprehensions for memory-efficient filtering.

**Deduplication:**  
Convert lists to Sets to remove duplicates instantly.

**Structured Storage:**  
Use Dictionaries for key-value record storage:

```python
{"sensor_id": 101, "temp": 32}
```

---

## 🔹 Phase 3: The Logic Transformer

**Technical Focus:**  
Conditionals, Dynamic Functions (\*args), Lambda Functions

### 🎯 Core Concept

Data is unpredictable. Transformers must be flexible.

### ⚙ Implementation Details

**Dynamic Functions (\*args)**  
Accept variable column structures.

**Conditionals (if-elif-else)**  
Handle data quality checks:

- Null handling
- Default tagging
- Validation logic

**Lambda Functions**  
Used for quick one-line transformations:

```python
fahrenheit_to_celsius = lambda f: (f - 32) * 5/9
```

---

## 🔹 Phase 4: Object-Oriented Pipeline Architecture

**Technical Focus:**  
Classes, Objects, Static Methods, Inheritance, Getters/Setters

### 🎯 Core Concept

Transition from scripting → enterprise-grade architecture.

### 🧱 Inheritance Models

**Single-Level:**  
Processor → JSONProcessor

**Multi-Level:**  
Base → Database → Postgres

**Multiple Inheritance:**  
DataStager + S3Uploader

### 🔧 Method Types

- Instance Methods → Data processing logic
- `@staticmethod` → Utility functions (e.g., filename validation)

### 🔐 Security

`@property` decorators protect sensitive attributes:

- API Keys
- Database Ports
- Credentials

Validation ensures safe modification.

---

## 🔹 Phase 5: Resilience & External Ingestion

**Technical Focus:**  
requests module, Exception Handling

### 🎯 Core Concept

Data Engineers design for failure.

### 🌐 API Handling

Fetch external data using `requests`.

Wrap every call inside:

```python
try:
    pass
except ConnectionError:
    pass
except Timeout:
    pass
finally:
    pass
```

### 🔁 finally Block Usage

Ensures:

- Logging occurs
- Connections close
- Cleanup always runs

---

## 🔹 Phase 6: Performance Optimization

**Technical Focus:**  
Parallel Processing, Multi-threading

### 🎯 Core Concept

Sequential execution is slow for large-scale I/O tasks.

### ⚡ Multi-threading

Use Python's `threading` module to:

- Run multiple API calls simultaneously
- Improve I/O-bound performance

### 📊 Performance Metric

We calculate speed improvement using:

```
Speedup = Time taken by Sequential Execution
          -----------------------------------
          Time taken by Threaded Execution
```

Or mathematically:

\[
Speedup = \frac{Time\ taken\ by\ Sequential\ Execution}{Time\ taken\ by\ Threaded\ Execution}
\]
