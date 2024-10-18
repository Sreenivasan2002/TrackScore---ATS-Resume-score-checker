# ATS Resume Scanner

A Streamlit application that analyzes resumes against job descriptions using Google's Gemini AI API. The application converts PDF resumes to text and provides matching scores, missing keywords, and profile summaries to help improve resume optimization for ATS (Applicant Tracking Systems).

## Features

- PDF to text conversion
- Resume analysis using Google Gemini AI
- ATS compatibility checking
- Job description matching score
- Missing keywords identification
- Profile summary generation

## Installation

1. Clone the repository:
```bash
git clone <repository-url>
cd ats-resume-scanner
```

2. Create a virtual environment (recommended):
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

3. Install required dependencies:
```bash
pip install -r requirements.txt
```

## Environment Setup

1. Create a `.env` file in the project root directory
2. Add your Google Gemini API key:
```
GOOGLE_API_KEY=your_api_key_here
```

## Requirements

- Python 3.7+
- streamlit
- PyPDF2
- google.generativeai
- python-dotenv

## Usage

1. Run the Streamlit application:
```bash
streamlit run app.py
```

2. Access the application in your web browser (typically http://localhost:8501)

3. Use the application:
   - Paste the job description in the text area
   - Upload your resume in PDF format
   - Click "Submit" to get the analysis

## Project Structure

```
ats-resume-scanner/
├── app.py              # Main application file
├── .env               # Environment variables (create this)
├── requirements.txt   # Project dependencies
└── README.md         # Project documentation
```

## How It Works

1. **PDF Processing**: The application uses PyPDF2 to convert uploaded PDF resumes into text format.

2. **AI Analysis**: The extracted text and job description are processed using Google's Gemini AI API with a specialized prompt that:
   - Acts as an experienced ATS system
   - Evaluates the resume against the job description
   - Considers tech field requirements
   - Provides matching percentage
   - Identifies missing keywords
   - Generates a profile summary

3. **Response Format**: The analysis is returned in a structured JSON format:
```json
{
    "JD Match": "percentage",
    "MissingKeywords": ["keyword1", "keyword2", ...],
    "Profile Summary": "detailed summary"
}
```

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.


## Acknowledgments

- Google Gemini AI for providing the AI capabilities
- Streamlit for the web application framework
- PyPDF2 for PDF processing capabilities
