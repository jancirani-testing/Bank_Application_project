<div align="center">


<img src="https://capsule-render.vercel.app/api?type=venom&height=300&color=0:0f2027,50:203a43,100:00b09b&text=Parabank%20Automation&fontSize=50&fontColor=ffffff&fontAlignY=40&desc=Data-driven%20banking%20tests%20with%20Selenium%20and%20TestNG&descAlignY=60&descSize=16" width="100%" alt="Parabank Automation banner" />


<img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=700&size=22&duration=3000&pause=900&color=00B09B&center=true&vCenter=true&width=760&height=60&lines=%F0%9F%8F%A6+Automating+the+Parabank+web+app;%F0%9F%93%8A+Test+data+lives+in+Excel%2C+not+in+code;%F0%9F%A7%AA+Selenium+WebDriver+%2B+TestNG+%2B+Maven;%E2%9E%95+New+data+set+%3D+new+row%2C+no+code+change" alt="Typing animation" />

<br/>

![Java](https://img.shields.io/badge/Java-8%2B-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white)
![Selenium](https://img.shields.io/badge/Selenium-WebDriver-43B02A?style=for-the-badge&logo=selenium&logoColor=white)
![TestNG](https://img.shields.io/badge/TestNG-Framework-FF7043?style=for-the-badge&logo=testng&logoColor=white)
![Maven](https://img.shields.io/badge/Maven-Build_Tool-C71A36?style=for-the-badge&logo=apachemaven&logoColor=white)
![Apache POI](https://img.shields.io/badge/Apache_POI-Excel_DDT-D22128?style=for-the-badge&logo=apache&logoColor=white)
![Eclipse](https://img.shields.io/badge/Eclipse-IDE-2C2255?style=for-the-badge&logo=eclipseide&logoColor=white)

![Chrome](https://img.shields.io/badge/Chrome-Supported-4285F4?style=flat-square&logo=googlechrome&logoColor=white)
![Firefox](https://img.shields.io/badge/Firefox-Supported-FF7139?style=flat-square&logo=firefoxbrowser&logoColor=white)
![Testing](https://img.shields.io/badge/Testing-Data_Driven-00b09b?style=flat-square)
![Status](https://img.shields.io/badge/Status-Active-brightgreen?style=flat-square)

<br/>

**[📌 Overview](#-project-overview)** •
**[✨ Features](#-key-features)** •
**[🧰 Tech Stack](#-technology-stack)** •
**[📊 Data-Driven](#-how-data-driven-testing-works)** •
**[🏗️ Structure](#%EF%B8%8F-project-structure)** •
**[🚀 Setup](#-getting-started)** •
**[▶️ Run](#%EF%B8%8F-running-the-tests)** •
**[📈 Reports](#-test-reports)**

</div>

<img src="https://capsule-render.vercel.app/api?type=rect&height=3&color=gradient&customColorList=12,20,6" width="100%" alt="divider" />

## 📌 Project Overview

**Parabank Automation** is a Selenium-based test automation framework for the **Parabank** web application, built with **Java, TestNG and Maven**.

Its main strength is **data-driven testing**: test inputs are stored in **Excel files** and read at run time with **Apache POI**, so the same test logic can run against many data sets without touching the code.

> 🎯 **Goal:** Keep test logic and test data separate, so tests stay clean, reusable and easy to extend.

```mermaid
flowchart LR
    X[("📊 Excel file<br/>TestScriptData.xlsx")] -->|Apache POI| D["🧪 DDT_From_Excel_File.java"]
    D -->|rows become inputs| W["🌐 Selenium WebDriver"]
    W --> P["🏦 Parabank web app"]
    P --> R["📈 TestNG reports<br/>test-output/"]

    style X fill:#43B02A,stroke:#2f7d1e,color:#fff
    style D fill:#7c4dff,stroke:#5530c9,color:#fff
    style W fill:#2c5364,stroke:#203a43,color:#fff
    style P fill:#FF7043,stroke:#c4491f,color:#fff
    style R fill:#00b09b,stroke:#007f6e,color:#fff
```

---

## ✨ Key Features

<table>
<tr>
<td width="50%" valign="top">

### 📊 Data-Driven Testing
- 📁 Test data kept in Excel files
- 🔌 Read using Apache POI
- ➕ Add rows, not code
- ♻️ One test, many data sets

</td>
<td width="50%" valign="top">

### ⚙️ Automation Framework
- 🌐 Selenium WebDriver browser automation
- 🧪 TestNG test execution
- 📦 Maven dependency management
- 🗂️ Clear separation of pages, utilities and tests

</td>
</tr>
<tr>
<td width="50%" valign="top">

### 🧱 Organized Structure
- 📄 Page objects, utilities and base classes in `src/main/java`
- 🧪 Test classes in `src/test/java`
- 🗃️ Test data in `src/test/resources`
- 🧪 Suite controlled via `testng.xml`

</td>
<td width="50%" valign="top">

### 📈 Reporting
- 🌐 TestNG HTML reports
- 📄 XML execution results
- ✅ Pass / ❌ fail / ⏭️ skip tracking
- 📂 Generated in `test-output/`

</td>
</tr>
</table>

---

## 🧰 Technology Stack

| Technology | Purpose |
|:--|:--|
| ☕ **Java** | Programming language |
| 🧪 **TestNG** | Test framework and execution |
| 📦 **Maven** | Build tool and dependency management |
| 🌐 **Selenium WebDriver** | Browser automation |
| 📊 **Apache POI** | Reading Excel test data |
| 💻 **Eclipse IDE** | Development environment |

<details>
<summary><b>📚 Technology Resources (click to expand)</b></summary>
<br/>

- ☕ [Java Documentation](https://docs.oracle.com/en/java/)
- 🌐 [Selenium Documentation](https://www.selenium.dev/documentation/)
- 🧪 [TestNG Documentation](https://testng.org/doc/)
- 📦 [Apache Maven Guide](https://maven.apache.org/guides/)
- 📊 [Apache POI](https://poi.apache.org/)

</details>

---

## 📊 How Data-Driven Testing Works

Test data is read from Excel files in `src/test/resources/` by `DDT_From_Excel_File.java` using Apache POI.

```mermaid
sequenceDiagram
    autonumber
    actor QA as 👩‍💻 Tester
    participant XL as 📊 Excel File
    participant T as 🧪 DDT_From_Excel_File
    participant WD as 🌐 WebDriver
    participant APP as 🏦 Parabank

    QA->>XL: Add a new row of test data
    QA->>T: Run the suite (mvn test)
    T->>XL: Read rows with Apache POI
    loop For every data row
        T->>WD: Launch browser
        WD->>APP: Perform actions using row values
        APP-->>WD: Page response
        WD-->>T: Assertions
    end
    T-->>QA: Reports in test-output/
```

**Adding a new scenario**

1. 📝 Open the Excel file in `src/test/resources/`
2. ➕ Add a new row with your data
3. ▶️ Run the suite, and the new row is picked up automatically

> 💡 No code changes are needed for new data sets.

---

## 🏗️ Project Structure

```text
parabank-automation/
│
├── 📂 src/
│   ├── 📂 main/java/                # Page objects, utilities, base classes
│   └── 📂 test/
│       ├── 📂 java/                 # Test classes (TestNG)
│       │   └── 📂 dataDrivenTesting/
│       │       └── 📊 DDT_From_Excel_File.java
│       └── 📂 resources/            # Test data files (e.g. TestScriptData.xlsx)
│
├── 📈 test-output/                  # TestNG execution reports
├── 🎯 target/                       # Compiled build output (ignored in Git)
├── 📦 pom.xml                       # Maven dependencies and build config
└── 🧪 testng.xml                    # TestNG suite configuration
```

| Folder / File | Responsibility |
|:--|:--|
| 📂 `src/main/java` | Page objects, utilities and base classes |
| 📂 `src/test/java` | TestNG test classes |
| 📊 `DDT_From_Excel_File.java` | Reads Excel data and drives the tests |
| 🗃️ `src/test/resources` | Excel test data files |
| 📦 `pom.xml` | Maven dependencies and build configuration |
| 🧪 `testng.xml` | TestNG suite configuration |
| 📈 `test-output/` | Generated execution reports |

---

## 🚀 Getting Started

### 📋 Prerequisites

| Requirement | Version |
|:--|:--|
| ☕ Java JDK | 8 or higher |
| 📦 Apache Maven | Installed and on your PATH |
| 💻 Eclipse IDE | With TestNG and EGit plugins |
| 🌍 Browser | Chrome or Firefox, plus matching WebDriver |

### ⚡ Setup

**1️⃣ Clone the repository**
```bash
git clone https://github.com/jancirani-testing/parabank-automation.git
cd parabank-automation
```

**2️⃣ Import into Eclipse**

1. **File → Import → Existing Maven Projects**
2. Select the cloned folder and click **Finish**

**3️⃣ Download dependencies**

Right-click the project → **Maven → Update Project**

**4️⃣ Update configuration**

Change values such as the base URL, credentials and file paths as needed.

---

## ▶️ Running the Tests

<table>
<tr>
<td width="50%" valign="top">

### 💻 Option 1: Eclipse

1. Open the project in Eclipse
2. Right-click `testng.xml`
3. Select **Run As → TestNG Suite**
4. Watch results in the TestNG console

</td>
<td width="50%" valign="top">

### ⌨️ Option 2: Maven

```bash
# Run the configured suite
mvn test

# Clean build, then test
mvn clean test
```

</td>
</tr>
</table>

> ⚠️ **Note:** Results depend on browser setup, application availability and configuration. Make sure the WebDriver matches your browser version.

---

## 📈 Test Reports

Reports are generated in the `test-output/` folder after each run.

```text
📁 test-output/
│
├── 🌐 index.html
├── 📧 emailable-report.html
├── 📄 testng-results.xml
└── 🗂️ other generated report files
```

| Report | Description |
|:--|:--|
| 🌐 `index.html` | TestNG execution summary |
| 📧 `emailable-report.html` | Email-friendly report |
| 📄 `testng-results.xml` | Structured XML results |

**👀 View results:** run the suite → open `test-output/` → open `index.html` in a browser → review ✅ passed, ❌ failed and ⏭️ skipped tests.

---

## 🔮 Future Enhancements

| Enhancement | Description | Status |
|:--|:--|:-:|
| 🧱 Page Object Model | Strengthen separation of page interactions and test logic | ![Planned](https://img.shields.io/badge/-Planned-orange?style=flat-square) |
| 📈 Extent Reports / Allure | Richer execution reports | ![Planned](https://img.shields.io/badge/-Planned-orange?style=flat-square) |
| 📸 Screenshot Capture | Capture screenshots for failed tests | ![Planned](https://img.shields.io/badge/-Planned-orange?style=flat-square) |
| 📝 Logging Framework | Better debugging and traceability | ![Planned](https://img.shields.io/badge/-Planned-orange?style=flat-square) |
| ⚡ Parallel Execution | Reduce execution time | ![Planned](https://img.shields.io/badge/-Planned-orange?style=flat-square) |
| 🤖 GitHub Actions | CI/CD pipeline for automatic runs | ![Planned](https://img.shields.io/badge/-Planned-orange?style=flat-square) |

---

## 🤝 Contributing

Contributions and suggestions are welcome! 💚

```bash
git checkout -b feature/your-feature-name
git commit -m "Add: your feature description"
git push origin feature/your-feature-name
```

Then open a **Pull Request** describing your changes.

---

## 👨‍💻 Author

<div align="center">

**Jancirani**

*QA Automation Tester* &nbsp;|&nbsp; ☕ Java &nbsp;|&nbsp; 🌐 Selenium WebDriver &nbsp;|&nbsp; 🧪 TestNG &nbsp;|&nbsp; 📊 Apache POI

<a href="https://github.com/jancirani-testing">
  <img src="https://img.shields.io/badge/GitHub-jancirani--testing-181717?style=for-the-badge&logo=github&logoColor=white" alt="GitHub profile" />
</a>

<br/><br/>

**⭐ If this project helped you, consider giving it a star!**

<img src="https://capsule-render.vercel.app/api?type=waving&height=160&section=footer&color=0:00b09b,50:2c5364,100:0f2027&animation=fadeIn" width="100%" alt="footer" />

**Made with ☕ Java, 🧪 Selenium & ❤️ for Quality Assurance**

</div>
