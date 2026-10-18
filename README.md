# Emotion Detector Application

An AI-based web application built with Python, Flask, and the Watson NLP Emotion Detection service. The application analyzes user-provided text to evaluate emotional tone across five categories—anger, disgust, fear, joy, and sadness—and determines the dominant emotion.

This repository represents the final capstone project for the **IBM AI Developer Professional Certificate**.

---

## Project Structure

```text
oefjy-final-project-emb-ai/
│
├── EmotionDetection/
│   ├── __init__.py
│   └── emotion_detection.py
│
├── templates/
│   └── index.html
│
├── static/
│   └── mywebscript.js
│
├── server.py
├── test_emotion_detection.py
└── README.md
```

---

## Features

- **Emotion Detection Engine:** Custom `EmotionDetection` package utilizing the Watson NLP Emotion Predict service.
- **Formatted Output:** Returns exact confidence scores for individual emotions alongside the identified dominant emotion.
- **Robust Error Handling:** Detects blank or invalid user input (HTTP status code 400) and provides clear system feedback (`Invalid text! Please try again!`).
- **Web Interface:** Interactive web deployment built using the Flask framework, HTML5, Bootstrap 5, and JavaScript (AJAX).
- **Unit Testing:** Full test suite implemented using Python's native `unittest` framework.
- **Static Code Analysis:** Clean code compliant with PEP8 guidelines, achieving a **10.00/10** score on `pylint`.

---

## Installation & Setup

1. **Clone the repository:**

   ```bash
   git clone https://github.com/talha-moazzam/oefjy-final-project-emb-ai.git
   cd oefjy-final-project-emb-ai
   ```

2. **Install required dependencies:**
   ```bash
   pip install flask requests pylint
   ```

---

## Execution Instructions

### 1. Run Package Unit Tests

Verify the emotion prediction logic across all target emotions:

```bash
python3 test_emotion_detection.py
```

### 2. Run Static Code Analysis

Ensure full compliance with Python styling standards:

```bash
pylint server.py
```

### 3. Launch the Web Application

Start the local Flask development server:

```bash
python3 server.py
```

Open your browser and navigate to `http://localhost:5000` or `http://127.0.0.1:5000` to interact with the application.

---

## API & Response Structure

### Endpoint: `/emotionDetector`

- **Method:** `GET`
- **Query Parameter:** `textToAnalyze` (string)

#### Valid Response Example:

> _"For the given statement, the system response is 'anger': 0.003, 'disgust': 0.002, 'fear': 0.003, 'joy': 0.968 and 'sadness': 0.005. The dominant emotion is joy."_

#### Error Response Example (Blank / Empty Input):

> _"Invalid text! Please try again!"_
