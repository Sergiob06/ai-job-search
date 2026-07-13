# Job Evaluation Framework

<!-- SETUP: Skill match areas and career goals are personalized by running /setup -->

## Scoring Dimensions

Evaluate each job posting against these five dimensions:

### 1. Technical Skills Match (0-100)
How well do the required/preferred skills align with the candidate's capabilities?

| Score | Meaning |
|-------|---------|
| 80-100 | Core requirements are primary skills |
| 60-79 | Most requirements match, 1-2 gaps that are learnable |
| 40-59 | Partial match, significant upskilling needed |
| 0-39 | Fundamental mismatch |

**Strong match areas:** Angular, Java/Spring Boot, PHP/Laravel, JavaScript, HTML5/CSS3, MySQL, database design, RESTful API development, Authentication/Authorization, MVC/OOP, Git/GitHub, WordPress/Elementor, SEO on-page, Web Performance Optimisation (WPO), Docker, Linux (Ubuntu/WSL), Nginx, deployment and server configuration, Responsive Web Design, Composer, Vite
**Moderate match areas:** Basic AWS (EC2, RDS), Agile ways of working (internship-level exposure, not deep process ownership)
**Weak match areas:** Automated testing/QA frameworks, CI/CD pipelines (beyond basic Docker/Nginx deployment), advanced cloud architecture, mobile development

### 2. Experience Match (0-100)
Does work history align with what they're looking for?

| Score | Meaning |
|-------|---------|
| 80-100 | Direct experience in the same domain and role type |
| 60-79 | Related experience, transferable skills clear |
| 40-59 | Adjacent experience, would need to make the case |
| 0-39 | Unrelated experience |

**Strong:** Junior full-stack web developer roles (Angular + Spring Boot); junior PHP/Laravel developer roles
**Moderate:** Junior backend/Java developer roles; junior frontend developer roles; WordPress/SEO specialist roles
**Entry-level:** Broader "Junior Software Engineer" roles at consultancies (NTT DATA, Capgemini, Accenture, Sopra Steria, Inetum) where the stack may differ from direct experience but the level is right

### 3. Behavioral/Culture Fit (0-100)
Does the role and company culture match the behavioral profile?

| Score | Meaning |
|-------|---------|
| 80-100 | Culture strongly matches behavioral preferences |
| 60-79 | Mixed signals but mostly compatible |
| 40-59 | Some friction areas |
| 0-39 | Significant culture mismatch |

**Red flags to research:** Department disorganization, work dominated by maintenance over development, poor chemistry with leadership, culture mismatches. Check reviews, media coverage, LinkedIn connections, and network contacts for insider perspective.

### 4. Location & Logistics (Pass/Fail + Notes)
- Within commute range: PASS
- Remote with occasional office: PASS
- Requires relocation: FAIL (deal-breaker)
- Frequent international travel: FLAG (discuss with user)

### 5. Career Alignment & Motivation (0-100)
Does this role advance career goals and contain tasks that energize?

| Score | Meaning |
|-------|---------|
| 80-100 | Strongly aligned with career direction, clear growth path |
| 60-79 | Good role but only partially aligned with long-term goals |
| 40-59 | Decent job but doesn't build toward career goals |
| 0-39 | Dead end or backwards step |

**Career goals:**
- Build a career as a full-stack or backend-leaning software developer
- Gain mentorship early on to build calibrated technical judgment quickly
- Broaden from Angular/Spring Boot and PHP/Laravel toward stronger software engineering practices (testing, CI/CD, cloud)

**Motivation filter:** Evaluate not just whether you *can* do the tasks, but whether the tasks will *energize* you. Consider:
- Tasks that energize: Learning new frameworks/tech, building full products end-to-end, mentorship from senior developers, feature development, performance/SEO optimisation work
- Tasks that drain: Purely repetitive maintenance-only work with no new development, rigid bureaucracy with slow approvals, isolated solo work with no feedback, requirements that shift constantly with no anchor at all
- Non-task factors: availability of mentorship, feedback culture, reasonably clear (if evolving) priorities

**Life situation alignment:** Consider personal constraints:
- **Security**: Recent graduate (DAW, 2026) entering the job market; targets a paid junior role at market rate, baseline ~24,000-28,000 EUR gross/year; no unpaid or underpaid roles
- **Flexibility**: Based in Gandía (Valencia). Prefers on-site or hybrid roles in Gandía/Valencia region; open to fully remote roles anywhere in Spain; not open to relocation-required contracts abroad
- **Professional development**: Early career - prioritizes mentorship and growth opportunities over role prestige

**Target sectors/companies to watch:** Software companies, SaaS, technology consultancies, and product-based companies in Valencia/Gandía and remote across Spain, including Sklum, Ale-Hop, Mercadona Tech, NTT DATA, Capgemini, Accenture, Sopra Steria, and Inetum.

### 6. Salary Benchmark (Optional)

If the salary lookup tool is configured (`salary_data.json` exists), look up the company:
```
python salary_lookup.py "<Company Name>" --json
```

If a city is known from the posting, add `--city "<City>"` to narrow results.

Present findings as:
```
### Salary Benchmark
| Metric | Value |
|--------|-------|
| [Category] index | XX.X (+/-X.X% vs baseline) |
| Overall index | XX.X (+/-X.X% vs baseline) |
```

Interpret results relative to the baseline defined in the data file's metadata. For index-based data, higher typically means above-market compensation.

If the salary tool is not configured, skip this section.

## Output Format

Present the evaluation as:

```
## Job Fit Evaluation: [Role] at [Company]

| Dimension | Score | Notes |
|-----------|-------|-------|
| Technical Skills | XX/100 | [brief note] |
| Experience Match | XX/100 | [brief note] |
| Behavioral Fit | XX/100 | [brief note] |
| Location | PASS/FAIL | [brief note] |
| Career Alignment | XX/100 | [brief note] |

**Overall Score: XX/100** (weighted average of scored dimensions)

### Verdict: [Strong Fit / Good Fit / Moderate Fit / Weak Fit / Poor Fit]

### Key Strengths for This Role
- [bullet points]

### Gaps to Address
- [bullet points]

### Recommendation
[1-2 sentences: apply/skip/apply with caveats]

### Company Research Checklist
- [ ] Checked company website (mission, values, recent news)
- [ ] Checked review sites (Glassdoor, Jobindex, etc.)
- [ ] Checked LinkedIn for team size, recent hires, connections
- [ ] Checked media for restructuring, growth, or workplace issues
- [ ] Identified network contacts who may know the team/manager
```

## Weighting
- Technical Skills: 30%
- Experience Match: 25%
- Behavioral Fit: 15%
- Career Alignment: 30%

(Location is pass/fail, not weighted)

## Thresholds
- **Strong Fit** (75+): Definitely apply, tailor everything
- **Good Fit** (60-74): Apply, address gaps in cover letter
- **Moderate Fit** (45-59): Consider carefully, discuss with user
- **Weak Fit** (30-44): Probably skip unless strategic reasons
- **Poor Fit** (<30): Skip

## Pre-Application: Call the Employer (Best Practice)

Before writing the application, consider whether the candidate should call the contact person listed in the posting. **Only call if there are substantive questions** - never call just to "be remembered."

### When to Suggest Calling
- The posting has unclear or ambiguous requirements
- It's unclear which competencies are essential vs. nice-to-have
- The role description is vague about day-to-day tasks
- There's a named contact person who invites questions

### Good Questions to Ask
- "What are the primary challenges in this role?"
- "How is time typically divided across the listed responsibilities?"
- "Which competencies are most critical for success in this position?"
- "What does success look like in the first 6-12 months?"

### Rules for the Call
- Prepare a 30-second "elevator pitch" about your background in case they ask
- The call's purpose is **gathering information**, not delivering a pitch
- Take notes - use what you learn to tailor the application
- Reference the conversation naturally in the cover letter ("After speaking with [name], I was especially drawn to...")
