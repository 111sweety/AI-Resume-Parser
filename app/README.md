# Resume Parser and Job Matcher

An AI-powered candidate screening and resume parsing tool that uses LLMs (via Groq API) to extract structured data from job descriptions and resumes (PDF and Word documents), evaluate candidate-job fit, and rank applicants.

## Features

- **Automated Job Description Analysis**: Extracts structured requirements including role, required skills, preferred skills, minimum experience, education requirements, and key responsibilities using Pydantic schemas.
- **Multi-Format Resume Support**: Reads `.pdf` (using `pypdf`) and `.docx` (using `python-docx`) files.
- **Semantic Resume Parsing**: Extracts candidate name, contact info, total experience, skills, structured work history, projects, and education regardless of arbitrary heading styles.
- **AI Matching & Scoring**: Compares candidate qualifications against the job description, computing a 0–100% match score, matching skills, missing skills, and a final hiring verdict.
- **Candidate Ranking**: Sorts and ranks applicants from highest to lowest match score.

## Installation

This project is managed with [uv](https://github.com/astral-sh/uv).

```bash
# Clone or open the repository
cd app

# Install dependencies
uv sync
```

Alternatively, with standard `pip`:

```bash
pip install -r <(uv pip compile pyproject.toml)
# Or manually:
pip install groq pydantic pypdf python-docx python-dotenv
```

## Configuration

Create a `.env` file in the root or `app/` directory with your Groq API key:

```env
GROQ_API_KEY="your-groq-api-key-here"
```

## Usage

1. Place your PDF (`.pdf`) or Word (`.docx`) resumes in the `app/resumes/` folder.
2. Run the main script:

```bash
uv run python main.py
```
