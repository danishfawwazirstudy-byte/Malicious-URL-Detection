# ThreatGuard: Malicious URL & Scam Detector

A simple Flask web app that uses Google's Gemini API to check whether a URL is safe and whether a document looks like a scam.

## Features

- **URL threat detection**: classifies a URL as `benign`, `phishing`, `malware`, or `defacement`.
- **Scam file detection**: upload a PDF or TXT file and get a verdict on whether the content looks legitimate or fraudulent, with a short explanation.
- **Dark purple UI** with loading spinners and color-coded results.

## Tech Stack

- Python 3, Flask
- Google Gemini API (`google-generativeai`)
- PyPDF2 for reading PDF text
- HTML and CSS (Jinja2 templates)

## Project Structure

```
.
├── main.py               # Flask app and Gemini prompts
├── requirements.txt      # Python dependencies
├── .gitignore
└── templates/
    └── index.html        # Frontend
```

## Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/<your-username>/<your-repo>.git
cd <your-repo>
```

### 2. Create a virtual environment (recommended)

```bash
python -m venv venv
venv\Scripts\activate        # Windows
source venv/bin/activate     # macOS / Linux
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Add your API key

Get a free key from [Google AI Studio](https://aistudio.google.com/), then create a file named `.env` in the project root:

```
GOOGLE_API_KEY=your_api_key_here
```

Never commit this file. It is already listed in `.gitignore`.

### 5. Run the app

```bash
python main.py
```

Open http://127.0.0.1:5000 in your browser.

## Usage

1. **Check a URL**: type a full URL (starting with `http://` or `https://`) and click **Classify**.
2. **Check a file**: choose a `.pdf` or `.txt` file and click **Analyze**.

## Limitations

- Results come from a large language model, not a security database, so they can be wrong. Do not use this as your only protection against malicious links or files.
- Only PDF files with extractable text and plain TXT files are supported. Scanned PDFs (images) will not work.
- The app does not visit the URL. It classifies based on the URL text only.

## License

MIT
