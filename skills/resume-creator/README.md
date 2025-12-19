# Resume Creator Skill

Create professional, ATS-friendly resumes that stand out to hiring managers.

## What It Does

- Analyzes your existing resume and LinkedIn
- Researches target company culture and requirements
- Applies first-principles thinking to tailor content
- Creates clean LaTeX Harvard-style formatting
- Iteratively refines through visual PDF review

## Requirements

### LaTeX

Install a LaTeX distribution with XeLaTeX:

**macOS:**
```bash
brew install --cask mactex
```

**Ubuntu/Debian:**
```bash
sudo apt-get install texlive-xetex texlive-fonts-recommended
```

**Windows:**
Download and install [MiKTeX](https://miktex.org/download)

### PDF Tools

For PDF to image conversion:

**macOS:**
```bash
brew install poppler
```

**Ubuntu/Debian:**
```bash
sudo apt-get install poppler-utils
```

### Fonts

The template uses **Helvetica Neue**. If not available, modify the template to use:
- Arial
- Inter
- Roboto

## Usage

Best results when you provide:

1. **Current resume** (PDF or text)
2. **LinkedIn screenshots** (profile, experience, posts) — Claude can't directly access LinkedIn URLs
3. **Target job posting** or company/role
4. **Recent achievements** not on your resume

### Example Prompts

```
Create a resume for the Senior Engineer role at Stripe.
Here's my current resume: [attach PDF]
LinkedIn: [attach screenshots]
```

```
Update my resume for YC startups in Berlin.
Focus on my AI/ML experience and startup background.
```

```
Help me tailor my CV for product engineer roles.
I want to emphasize my full-stack and customer-facing work.
```

## Output

- `Resume_[Name]_[Role]_[Year].pdf` - Final resume
- `resume.tex` - LaTeX source for future edits
