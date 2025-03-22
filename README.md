# 🤖 SkillSight: AI-Powered Employee Performance Feedback Generator

Welcome to the AI-Powered Performance Feedback Generator, a cutting-edge solution that automates employee evaluations with precision, fairness, and actionable insights. This project leverages state-of-the-art NLP techniques, particularly **KeyBERT**, to analyze employee skillsets and generate tailored feedback narratives based on performance ratings. It is designed for HR professionals, engineering managers, and team leads looking to streamline performance review cycles and strengthen workforce development.

---

## 🚀 Project Objectives

- Automatically generate **personalized feedback** for employees using AI.
- Extract relevant **key skills** using keyword extraction from textual data.
- Vary feedback suggestions based on **performance rating tiers**.
- Ensure unbiased, consistent, and constructive performance evaluations.
- Enable easy **integration with HR data sources** (Excel, databases, APIs).

---

## 🧠 Technologies Used

- **Python 3.11+**
- **KeyBERT** – for keyword extraction
- **SentenceTransformers** – for semantic embeddings
- **Pandas** – for data manipulation
- **OpenPyXL** – for Excel integration

---

## 💼 Business Use Cases

| Scenario                    | Description                                                                 |
|-----------------------------|-----------------------------------------------------------------------------|
| ✅ Annual/Quarterly Reviews | Generate structured, readable feedback automatically for all employees.     |
| 🌟 Goal Setting & Coaching | Provide employees with clear improvement paths tailored to their roles.     |
| 📊 People Analytics         | Track team-wide strengths and identify gaps across departments.             |
| 🚀 HRMS Integration         | Integrate with platforms like SAP, Zoho, or BambooHR via CSV/API/DB sync.  |

---

## 🔧 Installation & Setup

### 1. Clone the Repository
```bash
git clone https://github.com/your-username/ai-feedback-generator.git
cd ai-feedback-generator
```

### 2. Install Dependencies
```bash
pip install -r requirements.txt
# or manually
pip install keybert sentence-transformers pandas openpyxl
```

### 3. Mount Drive (if using Google Colab)
```python
from google.colab import drive
drive.mount('/content/drive')
```

---

## 📊 How It Works

1. Load employee skill data from an Excel file:
```python
path = "/content/drive/MyDrive/HR_Jobpositions_req/IT_Max_Job_Combinations.xlsx"
df = pd.read_excel(path)
```

2. Provide `row_index`, static `employee_id`, `employee_name`, and `rating`.

3. The script:
   - Extracts top N keywords from the "Key Skills" column using **KeyBERT**.
   - Generates customized feedback using AI-driven phrase banks.
   - Adapts the tone based on the employee's **rating**.
   - Personalizes phrasing using the employee's **name** as a seed for randomization.

---

## 🎯 Example
```python
feedback = generate_feedback(
    df,
    row_index=0,
    employee_id=1980,
    employee_name="Kishor Ravikumar",
    rating=4.0
)
print(feedback)
```

### Output Sample
```
🔹 Performance Review for Kishor Ravikumar (Job ID: 1980)
Rating: ⭐️ 4.0/5

- Skilled in automation
- Skilled in scripting
- Skilled in prism

🟡 Performing well. To elevate further:
- Consider deepening expertise in automation
- Collaborate on scripting
- Stay current on prism
```

---

## 🚀 Integration Options

### Excel-Based HRMS
- Export employee data with columns: `Employee Name`, `Key Skills`, `Department`
- Use `pandas.read_excel()` to load data

### Database Integration
```python
import sqlalchemy
engine = sqlalchemy.create_engine("mysql+pymysql://user:pass@host/db")
df = pd.read_sql("SELECT * FROM employee_table", engine)
```

### REST API Integration
- Use `requests` to pull employee profiles from your HR API
- Convert JSON to `DataFrame`

---

## 💡 Customization Tips

| Parameter        | Description                                      |
|------------------|--------------------------------------------------|
| `top_n`          | Number of keywords to extract (default = 3)      |
| `rating`         | Performance score (e.g., 3.7, 4.0, 4.8)           |
| `employee_name`  | Used for randomizing phrasing for personalization |
| `output_format`  | Customize print output or save to file           |

---

## 🎓 Future Improvements

- 🔹 PDF/Word report export
- 📊 Streamlit-based feedback dashboard
- 🌐 REST API with feedback-as-a-service

---

## 👤 Author

**Kishor Ravikumar**  
Engineer | Researcher | AI & HR Tech Enthusiast

---

## 🚫 License

MIT License

> Feel free to fork, star, and contribute! PRs are welcome.

