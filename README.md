# CAD Practice Exam

Interactive ServiceNow CAD (Certified Application Developer) practice exam with 219 real-style questions.

## 🎯 Features

- **219 questions** from SecExams CAD dump
- **Two modes**: Practice (instant feedback) and Exam (scored at end)
- **Question types**: Single-answer (172) and multi-answer (47)
- **Filtering**: Include/exclude question types, shuffle questions and options
- **Tracking**: Session resume, attempt history, score tracking via localStorage
- **Keyboard shortcuts**: A–J select option, Arrow keys navigate, F to flag, etc.
- **Dark/Light theme** toggle

## 🚀 Getting Started

### Build from source

Requires `pdftotext` from [Poppler](https://poppler.freedesktop.org/):

```bash
brew install poppler          # macOS
# or: apt-get install poppler-utils  # Linux
python3 build-questions.py    # regenerate site/questions.json
```

### Run locally

```bash
cd site
python3 -m http.server 8765
# Open http://localhost:8765 in your browser
```

## 📊 Question Stats

| Type | Count |
|---|---|
| Single-answer | 172 |
| Multi-answer (choose 2/3/…) | 47 |
| **Total** | **219** |

## 📝 Data Format

All questions are stored in `site/questions.json`:

```json
{
  "id": 1,
  "type": "single",
  "text": "Question text here",
  "options": [
    { "letter": "A", "text": "Option A" },
    { "letter": "B", "text": "Option B" }
  ],
  "correct": ["A"]
}
```

Multi-answer questions have `"correct": ["A", "D"]` etc.

## 🔧 Tech Stack

- Vanilla HTML/CSS/JavaScript (no build step, no dependencies)
- `pdftotext` for PDF extraction → regex parser → JSON
- GitHub Pages for hosting
- localStorage for session persistence

## 📄 License

MIT (educational use)

---

**Note:** This content is exam preparation material from SecExams. See individual questions for accuracy; use for study purposes.
