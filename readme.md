# Financial Sentiment Analyzer (Streamlit)

This is a Streamlit web app that analyzes the sentiment of financial text using a pre-trained scikit-learn model.

You can do two things:
- Upload a PDF or image and the app will extract text using OCR, then predict sentiment
- Paste text manually and the app will predict sentiment immediately

---

## What’s inside

- `app.py`
  - Streamlit UI (tabs, buttons, styled result card)
  - OCR for PDFs/images
  - Loads the pre-trained model and predicts sentiment

- `data/pkls/`
  - `svm.pkl` (baseline word-level TF-IDF model)
  - `svm_char.pkl` (higher accuracy character-level TF-IDF model)

- `process_data/`
  - Jupyter notebooks used to train models

---

## Supported input

### 1) Upload Document (OCR)
Accepted file types:
- PDF
- PNG
- JPG
- JPEG

How OCR works:
- Images: OCR using Tesseract
- PDF: converts PDF pages into images using Poppler, then OCR using Tesseract

### 2) Manual Input
- A large text box where you can paste financial news / statements

---

## Sentiment output

The app shows:
- Sentiment label: Positive / Neutral / Negative
- Confidence score (based on the model scores)
- A short explanation for each sentiment

---

## Important Windows OCR requirements

### A) Tesseract OCR (required)
Your app uses:
- `pytesseract` (Python wrapper)
- `tesseract.exe` (the actual OCR engine)

Check it:
```powershell
where tesseract
tesseract --version