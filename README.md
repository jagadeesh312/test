# Secure AI-Protected Online MCQ Examination System

A Firebase-ready prototype for secure online MCQ exams with student and teacher workflows, question randomization, and anti-cheating controls.

## Features

- Role-based login for student and teacher users
- Student dashboard for available tests, marks, and attempt history
- Teacher dashboard for test creation, result review, and cheating logs
- Secure exam page with fullscreen mode, tab-switch warnings, blocked shortcuts, and inactivity detection
- Randomized question and option order per attempt
- Result page with score, time taken, and cheating summary
- Local storage persistence so the demo runs without backend setup

## Demo Accounts

- Student: `student@example.com` / `student123`
- Teacher: `teacher@example.com` / `teacher123`

## Project Structure

```text
secure-mcq-exam
+-- backend
¦   +-- controllers
¦   +-- routes
¦   +-- server.js
+-- css
¦   +-- style.css
+-- database
¦   +-- firebaseConfig.js
+-- js
¦   +-- app.js
¦   +-- auth.js
¦   +-- create-test.js
¦   +-- dashboard.js
¦   +-- data.js
¦   +-- exam.js
¦   +-- result.js
¦   +-- security.js
+-- create-test.html
+-- dashboard.html
+-- exam.html
+-- index.html
+-- login.html
+-- result.html
+-- README.md
```

## Run Frontend

Open `login.html` in a local web server. Example with VS Code Live Server or any static server. Some browser security protections, especially fullscreen flow, behave better over `http://localhost` than `file://`.

## Backend Notes

`backend/server.js` is a minimal Express stub to show how API routes can be organized. The current frontend uses local storage for immediate demo use. For production:

1. Wire login to Firebase Authentication.
2. Store users, tests, questions, results, and logs in Firestore.
3. Move scoring and anti-cheating log persistence to backend or Cloud Functions.
4. Add stricter proctoring such as webcam or screen recording only with consent and legal review.

## CSV Format

```csv
Question,OptionA,OptionB,OptionC,OptionD,CorrectAnswer
What is Cloud?,Internet,Hardware,Software,Network,A
```
