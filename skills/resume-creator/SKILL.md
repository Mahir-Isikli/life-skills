---
name: resume-creator
description: Create professional resumes using first-principles thinking, company research, LaTeX Harvard-style formatting, and iterative visual refinement. Use when the user wants to create, update, or optimize a resume/CV for a specific job, company, or career goal.
---

# Resume Creator

A comprehensive resume creation skill that uses first-principles thinking, web research, and iterative visual refinement to craft tailored, professional resumes.

## When to Use This Skill

- User wants to create a new resume
- User wants to update/optimize an existing resume
- User mentions a job application, job posting, or target company
- User asks about resume formatting or CV creation
- User wants to tailor their resume for a specific role

## Process Overview

### Phase 1: Information Gathering

1. **Read existing materials** (if available):
   - Existing resume (PDF, Word, or text)
   - LinkedIn profile screenshots (Claude cannot directly access LinkedIn URLs)
   - Portfolio or personal website

2. **Understand the target**:
   - Job description (if provided)
   - Target company and role
   - Industry/role type
   - Career goals

3. **Research the target company** using web search:
   - Company culture and values
   - Tech stack and engineering practices
   - Recent news, funding, products
   - What they look for in candidates
   - Example searches:
     - "{company} engineering blog hiring"
     - "{company} careers culture values"
     - "{role} at {company} interview what they look for"

4. **Gather missing information** by asking the user:
   - Recent experience not on resume
   - Specific achievements with metrics
   - Skills and technologies used
   - Projects and speaking engagements

### Phase 2: First-Principles Analysis

Before writing, analyze from first principles:

1. **Research what hiring managers look for**:
   - Web search: "{role} resume what hiring managers look for 2024"
   - Web search: "Paul Graham hiring engineers startups" (for startup roles)
   - Understand the <8 second resume scan reality

2. **Alignment analysis**:
   Create a table mapping:
   | Job Requirement | User's Experience | Gap/Strength |

3. **Paul Graham / YC style considerations** (for startup roles):
   - Lead with what you BUILT, not job titles
   - Show speed of execution ("shipped in X weeks")
   - Quantify everything (%, numbers, scale)
   - Builder tone: "Built", "Shipped", "Won" not "Responsible for"
   - Remove corporate buzzwords

### Phase 3: LaTeX Resume Creation

Use the Harvard-style LaTeX template with:
- Clean header (name, location, contact, links)
- No colored header bars - clean white background
- Section order: Experience → Projects & Speaking → Skills → Education → Leadership
- € symbol for currencies
- 1 page maximum

Key formatting:
- Font: Helvetica Neue (or similar sans-serif)
- Colors: Navy blue (#14-2D-4B) for sections
- Margins: ~0.5 inches
- Line spacing: 1.05

### Phase 4: Iterative Visual Refinement

**Critical**: After creating the LaTeX file, iterate visually:

1. **Compile to PDF**:
   ```bash
   xelatex -interaction=nonstopmode resume.tex
   ```

2. **Convert to high-resolution image**:
   ```bash
   pdftoppm -png -r 300 resume.pdf resume_preview
   ```

3. **Read the image** using the Read tool to visually inspect

4. **Check for issues**:
   - Does it fit on 1 page?
   - Is spacing balanced?
   - Are there overflow issues?
   - Is typography clean?

5. **Iterate** until perfect

### Phase 5: Final Delivery

1. Save final PDF: `Resume_[Name]_[Role]_[Year].pdf`
2. Keep .tex source file
3. Clean up temp files
4. Open PDF for user

## Content Guidelines

### Experience Bullets

**Good** (action + metric + result):
- Built real-time fraud detection pipeline processing 50M+ transactions/day, reducing chargebacks by 23%
- Shipped MVP in 4 weeks, reduced costs 50% for pilot customers

**Bad** (vague/passive):
- Responsible for platform development
- Worked on various projects

### Skills Organization

- **AI/ML**: LangChain, LangGraph, DSPy, RAG, Vector DBs
- **Full-Stack**: Next.js, React, TypeScript, Node.js, Python
- **Data & Infra**: Postgres, Redis, Docker, GCP, Azure
- **Languages**: German (native), English (fluent)

## How Users Should Use This Skill

For best results, provide:
1. Your current resume (PDF or text)
2. LinkedIn screenshots (profile, experience, posts) — Claude cannot directly access LinkedIn URLs
3. The job posting or target company/role
4. Any recent achievements not on your resume

Example:
```
Help me update my resume for the Product Engineer role at Langdock.
Here's my current resume: [attach PDF]
LinkedIn: [attach screenshots of profile and experience]
```
