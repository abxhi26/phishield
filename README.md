# 🛡️ Phishield – Intelligent Phishing Detection System

## 🚀 Overview

**Phishield** is an advanced phishing detection system designed to analyze emails using a combination of **machine learning, deep learning, and rule-based techniques**.

It evaluates multiple aspects of an email — including headers, content, links, and domain reputation — to provide a **comprehensive risk score and verdict**.

---

## 🎯 Key Features

* 📧 Email phishing detection (Safe / Suspicious / Phishing)
* 🧠 Multi-model analysis (ML + BERT + feedback learning)
* 🔗 Malicious link detection
* 🌐 Domain reputation analysis
* 📊 Real-time dashboard for monitoring scans
* 🔁 Continuous learning using user feedback
* 📈 Weighted scoring system for accurate classification

---

## 🧠 System Architecture

The system combines multiple independent analyzers:

### 1. Header Analysis

* Detects spoofed senders and suspicious subjects
* Generates risk score based on patterns

### 2. Body Analysis (ML)

* Uses NLP techniques to detect phishing keywords
* TF-IDF + traditional ML model

### 3. BERT-Based Analysis

* Deep learning model for semantic understanding
* Detects intent, sentiment, and phishing probability

### 4. Link Analysis

* Checks embedded URLs for malicious patterns

### 5. Domain Reputation

* Evaluates sender domain trustworthiness

### 6. Feedback Learning System

* Learns from user feedback
* Retrains model periodically

---

## ⚙️ Tech Stack

### Backend

* Python
* Flask

### Machine Learning

* Scikit-learn
* TF-IDF Vectorization

### Deep Learning

* BERT (Natural Language Understanding)

### Other Tools

* JSON-based storage
* Custom analytics dashboard

---

## 📊 Scoring Mechanism

The final phishing score is calculated using weighted components:

* Header Score → 20%
* Body Score → 25%
* BERT Score → 20%
* Feedback Model → 15%
* Link Analysis → 20%

### 📌 Verdict Logic

* **0.8 – 1.0** → Phishing
* **0.5 – 0.8** → Suspicious
* **0.0 – 0.5** → Safe

---

## 📡 API Endpoints

### 🔍 Analyze Email

```http
POST /analyze
```

**Input:**

```json
{
  "sender": "example@mail.com",
  "subject": "Urgent action required",
  "body": "Click here to verify your account",
  "links": ["http://suspicious-link.com"]
}
```

**Output:**

* Risk scores (header, body, BERT, links)
* Domain analysis
* Final score
* Verdict (Safe / Suspicious / Phishing)

---

### 📝 Submit Feedback

```http
POST /feedback
```

Allows the system to learn from user corrections.

---

### 📊 Dashboard

```http
GET /dashboard
```

* Visualizes scan data
* Shows trends and statistics

---

### 🔁 Retrain Model

```http
POST /feedback/retrain
```

Manually retrains the feedback model.

---

## 📁 Project Structure

```bash
phishield/
│── backend/
│── chrome_extension/
│── model/
│── utils/
│── dashboard/
│── templates/
│── feedback.json
│── app.py
│── README.md
```

---

## ▶️ How to Run

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/phishield.git
cd phishield
```

---

### 2. Install Dependencies

```bash
pip install -r requirements.txt
```

---

### 3. Run the Application

```bash
python app.py
```

---

### 4. Open in Browser

```
http://127.0.0.1:5000/dashboard
```

---

## 🔁 Feedback Learning Mechanism

* Stores user feedback in `feedback.json`
* Retrains model after:

  * Minimum 10 feedback entries
  * Every 5 new entries thereafter

---

## 📈 Use Cases

* Email security systems
* Enterprise phishing detection
* Browser extensions (Chrome integration included)
* Personal cybersecurity tools

---

## 🚀 Future Enhancements

* Deploy as a cloud-based API
* Add real-time email integration (Gmail/Outlook)
* Improve BERT model accuracy
* Add mobile application
* Integrate threat intelligence APIs

---

## 👨‍💻 Author

**Abhiram Aravind**

---

## ⭐ Support

If you found this project useful, consider giving it a ⭐ on GitHub!

---
