ATS RESUME CHECKER
==================

A Streamlit app that scores a resume for ATS (Applicant Tracking System)
compatibility and suggests improvements, powered by Google Gemini.

FEATURES
--------
- Upload a resume as PDF or DOCX
- Optionally paste a job description for better keyword matching
- ATS score out of 100 with a 5-category breakdown
- Strengths, problems found, and prioritised improvements
- Missing keywords and suggested bullet rewrites

FILES
-----
app.py            The Streamlit application
requirements.txt  Python dependencies
README.txt        This file

RUN LOCALLY
-----------
1. Install Python 3.10 or newer.
2. (Recommended) create a virtual environment:
       python -m venv venv
       venv\Scripts\activate          (Windows)
       source venv/bin/activate       (Mac / Linux)
3. Install dependencies:
       pip install -r requirements.txt
4. Get a free Gemini API key: https://aistudio.google.com/apikey
5. Provide the key in ONE of these ways:
   a) Create the file .streamlit/secrets.toml containing:
          GEMINI_API_KEY = "your-key-here"
   b) Or set an environment variable GEMINI_API_KEY
   c) Or just paste it into the sidebar when the app opens
6. Start the app:
       streamlit run app.py

CHANGING THE MODEL
------------------
The app uses "gemini-flash-latest" (always the newest Flash model).
To pin a specific model, add this to secrets.toml (or the sidebar):
       GEMINI_MODEL = "model-name-here"

DEPLOY ON STREAMLIT COMMUNITY CLOUD
-----------------------------------
1. Push this project to a GitHub repository (do NOT commit secrets.toml).
2. Go to https://share.streamlit.io and sign in with GitHub.
3. Click "Create app", choose your repo, branch "main", main file "app.py".
4. Open "Advanced settings" -> "Secrets" and paste:
       GEMINI_API_KEY = "your-key-here"
5. Click "Deploy".

NOTES
-----
- Scanned (image-only) PDFs cannot be read; use a text-based PDF or DOCX.
- Resume text is sent to Google's Gemini API for analysis.
- The score is an AI estimate, not the output of a real employer ATS.
