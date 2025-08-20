# 📘 Image-to-Text & LaTeX OCR Server

A Python **Flask-based API server** that converts images into **plain text** (via [Tesseract OCR](https://github.com/tesseract-ocr/tesseract)) and **LaTeX code** (via [pix2tex](https://github.com/lukas-blecher/LaTeX-OCR)).  
It supports image preprocessing with OpenCV to improve recognition quality.

---

## 🚀 Features
- 📝 Extract **plain text** from images using Tesseract OCR.  
- 🔢 Convert math expressions and equations from images to **LaTeX** using pix2tex.  
- 🎨 Includes **image preprocessing** (grayscale, blur, thresholding, noise removal) for better OCR accuracy.  
- 🌍 CORS-enabled API (easy to integrate with frontend apps).  

---

## 📂 Project Structure
├── app.py # Main Flask server
├── requirements.txt # Python dependencies
└── README.md # Documentation


---

## ⚙️ Installation

### 1. Clone the repo
```bash
git clone https://github.com/awais2723/image-to-text-latex-flask.git
cd image-to-text-latex-flask

2. Create a virtual environment
python -m venv venv
source venv/bin/activate   # For Linux / Mac
venv\Scripts\activate      # For Windows

3. Install dependencies
pip install -r requirements.txt

4. Install Tesseract OCR

Windows: Download from Tesseract OCR

Linux/macOS:  sudo apt-get install tesseract-ocr


Update the path in app.py if required:

pytesseract.pytesseract.tesseract_cmd = r'tesseract'


Run the Server
python app.py

By default, it runs on:
http://localhost:5000

✅ Health Check

GET /
Response: "Server is running!"

📝 Convert Image → Plain Text
POST /text
Request Body:
    {
  "uri": "data:image/png;base64,....",
  "type": "image/png",
  "name": "sample.png"
    }

Response:

    Edit
    {
        "text": "Extracted text here..."
    }


🔢 Convert Image → LaTeX

POST /latex
Request Body:

    {
        "uri": "data:image/png;base64,....",
        "type": "image/png",
        "name": "equation.png"
    }

Response:

    {
        "latex": "\\frac{a}{b}",
        "text": "a/b"
    }


🛠 Tech Stack

Flask – Web server

Tesseract OCR – Text recognition

pix2tex (LaTeX-OCR) – Equation recognition

OpenCV + Pillow – Image preprocessing

PyLaTeXenc – Convert LaTeX → plain text

🤝 Contributing

Pull requests are welcome! For major changes, please open an issue first to discuss your ideas.