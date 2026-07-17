# 🤖 AI Resume Analyzer

An AI-powered Resume Analyzer built using **Spring Boot**, **Spring AI**, **OpenAI GPT**, and **Apache Tika**. This application extracts text from resumes (PDF/DOCX), analyzes resume quality, identifies key skills, provides improvement suggestions, and performs ATS (Applicant Tracking System) compatibility checks against a Job Description.

---

# 📌 Features

### 📄 Resume Analysis
- Upload Resume (PDF/DOC/DOCX)
- Extract resume text using Apache Tika
- Identify key technical skills
- Analyze overall resume quality
- Generate AI-powered summary
- Suggest exactly 3 improvements

### 🎯 ATS Resume Checker
- Compare resume with Job Description
- Calculate ATS Match Score (0–100)
- Find matched keywords
- Identify missing keywords
- Generate ATS compatibility summary

### 🤖 AI Integration
- Uses Spring AI
- Powered by OpenAI GPT Model
- Generates structured JSON responses

---

# 🛠️ Tech Stack

| Technology | Purpose |
|------------|----------|
| Java 21 | Programming Language |
| Spring Boot | Backend Framework |
| Spring AI | AI Integration |
| OpenAI GPT | Resume Analysis |
| Apache Tika | Resume Text Extraction |
| Maven | Dependency Management |
| REST API | Backend Communication |
| JSON | Response Format |

---

# 📂 Project Structure

```
ResumeAnalyser
│
├── controller
│     └── ResumeController.java
│
├── resources
│     └── application.properties
│
├── pom.xml
│
└── README.md
```

---

# ⚙️ How It Works

```
                Resume Upload
                      │
                      ▼
             Apache Tika Extracts Text
                      │
                      ▼
              Spring AI Prompt Creation
                      │
                      ▼
               OpenAI GPT Analysis
                      │
          ┌───────────┴────────────┐
          ▼                        ▼
 Resume Quality Analysis      ATS Analysis
          ▼                        ▼
        JSON Response        JSON Response
```

---

# 🚀 API Endpoints

## 1️⃣ Resume Analysis

### POST

```
/api/resume/analyze
```

### Form Data

| Parameter | Type |
|-----------|------|
| file | MultipartFile |

### Sample Request

```
POST /api/resume/analyze
```

Upload a resume file.

---

### Sample Response

```json
{
  "analysis": {
    "keySkills": [
      "Java",
      "Spring Boot",
      "REST API",
      "MySQL"
    ],
    "resumeQuality": 8,
    "improvements": [
      "Add measurable achievements",
      "Improve project descriptions",
      "Include certifications"
    ],
    "summary": "Strong backend developer profile with good Java and Spring Boot knowledge."
  }
}
```

---

# 2️⃣ ATS Resume Check

### POST

```
/api/resume/ats-check
```

### Form Data

| Parameter | Type |
|-----------|------|
| file | MultipartFile |
| jd | String |

---

### Sample Response

```json
{
  "atsReport": {
    "atsScore": 82,
    "matchedKeywords": [
      "Java",
      "Spring Boot",
      "REST API",
      "Hibernate"
    ],
    "missingKeywords": [
      "Docker",
      "Kubernetes",
      "AWS"
    ],
    "summary": "Resume matches most backend development requirements but lacks cloud and containerization technologies."
  }
}
```

---

# 📋 Prompt Engineering

The project uses carefully designed prompts to ensure:

- Strict JSON responses
- No Markdown formatting
- AI-generated skill extraction
- Resume quality scoring
- ATS keyword matching
- Improvement recommendations

---

# 🔧 Installation

## Clone Repository

```bash
git clone https://github.com/yourusername/ResumeAnalyser.git
```

---

## Navigate

```bash
cd ResumeAnalyser
```

---

## Build Project

```bash
mvn clean install
```

---

## Run Application

```bash
mvn spring-boot:run
```

Application starts at

```
http://localhost:8080
```

---

# 🔑 Configuration

Configure your OpenAI API key in `application.properties`.

```properties
spring.ai.openai.api-key=YOUR_OPENAI_API_KEY
```

Example:

```properties
spring.ai.openai.chat.options.model=gpt-4o-mini
```

---

# 📦 Dependencies

- Spring Boot Starter Web
- Spring AI OpenAI
- Apache Tika
- Spring Boot Starter Validation
- Maven

---

# 📊 JSON Output Format

## Resume Analysis

```json
{
  "keySkills": [],
  "resumeQuality": 0,
  "improvements": [],
  "summary": ""
}
```

---

## ATS Report

```json
{
  "atsScore": 0,
  "matchedKeywords": [],
  "missingKeywords": [],
  "summary": ""
}
```

---

# 🔥 Future Enhancements

- Resume PDF report generation
- Resume ranking system
- Multiple resume comparison
- Grammar and spelling analysis
- AI resume rewriting
- AI cover letter generation
- Skill gap analysis
- Interview question recommendations
- Resume templates
- User authentication
- Resume history tracking
- Dashboard analytics
- Multi-language support

---

# 💡 Learning Outcomes

This project demonstrates practical implementation of:

- Spring Boot REST APIs
- Spring AI integration
- Prompt Engineering
- OpenAI GPT API usage
- Apache Tika document parsing
- Multipart file handling
- JSON response generation
- ATS resume analysis concepts

---

# 👨‍💻 Author

**Nilmani Kumar**

Backend Developer | Java | Spring Boot | REST APIs | Spring AI

GitHub: https://github.com/yourusername

LinkedIn: https://linkedin.com/in/yourprofile

---

# ⭐ If you found this project helpful

Give it a ⭐ on GitHub and feel free to contribute!

---

## License

This project is licensed under the MIT License.
