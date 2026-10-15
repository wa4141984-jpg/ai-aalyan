# 📄 ATS Resume Checker

Upload your resume (PDF, DOCX or TXT) and get an ATS score, a score breakdown, missing keywords, improvement suggestions and bullet rewrites. Built with **Streamlit** and **Google Gemini Flash**.

## Features
- ATS score out of 100 with breakdown (formatting, keywords, content, structure, impact)
- Optional job description for keyword matching
- Strengths, weaknesses and section-by-section improvements
- Before/after bullet rewrite examples

## Run locally
```bash
git clone https://github.com/<your-username>/ats-resume-checker.git
cd ats-resume-checker
python -m venv venv
source venv/bin/activate        # Windows: venv\Scripts\activate
pip install -r requirements.txt
```
Get a free API key at https://aistudio.google.com, then either:

- set it as an environment variable: `export GEMINI_API_KEY="your_key"` (Windows: `set GEMINI_API_KEY=your_key`), or
- create `.streamlit/secrets.toml` containing `GEMINI_API_KEY = "your_key"`, or
- paste it into the sidebar when the app opens.

```bash
streamlit run app.py
```

Optional: change the model with `GEMINI_MODEL` (default `gemini-3.8-flash`, with automatic fallback to 3.7 and 3.6 Flash).

## Deploy on Streamlit Community Cloud
1. Push this repo to GitHub (never commit your API key).
2. Go to https://share.streamlit.io and sign in with GitHub.
3. Click **Create app**, pick the repo, branch `main`, main file `app.py`.
4. Open **Advanced settings → Secrets** and add: `GEMINI_API_KEY = "your_key"`
5. Click **Deploy**.

## Notes
- Scanned/image-only PDFs can't be read; use a text-based PDF.
- The score is an AI estimate, not the output of a real ATS.
