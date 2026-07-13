# Job Application Assistant for Sergio Bonillo

<!-- SETUP: This file is populated by running /setup -->
<!-- After running /setup, all [PLACEHOLDER] tokens will be replaced with your actual information -->

## Role
This repo is a job application workspace. Claude acts as a career advisor and application assistant for Sergio Bonillo, helping with:
1. **Job fit evaluation** - Assess job postings against your profile (skills, experience, behavioral traits)
2. **CV tailoring** - Adapt existing CV templates (LaTeX/moderncv) to target specific roles
3. **Cover letter writing** - Draft targeted cover letters using existing templates (LaTeX)
4. **Interview preparation** - Prepare answers, questions, and talking points for interviews
5. **Career strategy** - Advise on positioning and personal branding

## Candidate Profile

<!-- This section is auto-populated by /setup. You can also fill it in manually. -->

### Identity
- **Name:** Sergio Bonillo
- **Location:** Gandia, Valencia, Spain (prefers on-site/hybrid in Gandia/Valencia region; open to fully remote roles anywhere in Spain; not open to relocation abroad)
- **Languages:** Spanish (Native), Valencian (C1/Native), English (B2)
- **Status:** Open to work
- **LinkedIn headline:** "Full Stack Developer"

### Education
<!-- List your degrees, most recent first -->
- **Técnico Superior en Desarrollo de Aplicaciones Web (DAW)** (completed 2026, final grade 7.75) - IES María Enríquez, Gandia
  - Topics: Web development in client and server environments, databases, systems, web deployment, interface design
- **Bachillerato** (completed 2023) - IES Tirant lo Blanc, Gandia

### Professional Experience
<!-- List your roles, most recent first -->
- **Full Stack Developer (Internship)** (2025 - 2026, 6 months) - **ADW Solutions** (Valencia)
  - Collaborated on custom web application development using Angular (frontend) and Java Spring Boot (backend), following MVC architecture and OOP principles
  - Managed and optimised WordPress + Elementor sites focused on SEO on-page and Web Performance Optimisation (WPO) to improve organic ranking
  - Version control with Git/GitHub, collaborated with cross-functional teams; basic application deployments on AWS

### Technical Skills
- **Backend:** Java (Spring Boot), PHP (Laravel), RESTful API development, Authentication and Authorization, MVC, OOP
- **Frontend:** Angular, JavaScript, HTML5, CSS3, Responsive Web Design, Vite, WordPress, Elementor
- **Databases:** MySQL, database design
- **DevOps:** Docker, Linux (Ubuntu/WSL), Nginx, deployment and server configuration, Basic AWS (EC2, RDS)
- **Tools:** Git, GitHub, Composer, Agile
- **Domain:** Full-stack web application development, SEO on-page, Web Performance Optimisation (WPO)

### Certifications
<!-- List relevant certifications with dates -->
- None beyond the DAW degree and B2 English certification

### Publications
<!-- List peer-reviewed publications, if any -->
- None

### Awards
<!-- List relevant awards, hackathons, competitions -->
- None yet

### Behavioral Profile
<!-- Your behavioral assessment results (PI, DISC, Myers-Briggs, or self-assessment) -->
- **Adaptable** - No fixed preference between structured and autonomous work; matches the mode to what the task requires
- **Risk-calibrated decision-maker** - Moves fast on low-stakes/reversible decisions, slows down to research for high-stakes ones
- **Strengths:** Direct, context-rich communication (comfortable both live in meetings and in written documentation); versatility shown by handling two parallel technical tracks (Angular/Spring Boot dev + WordPress SEO/WPO) during the internship
- **Growth areas:** Still building independent judgment on ambiguous, high-stakes technical calls; actively seeks mentorship to accelerate this
- **Thrives in:** Environments with reasonably clear (if evolving) priorities, regular feedback loops, and a mix of new feature work plus enough maintenance to stay grounded in the product

### What Excites You
<!-- What motivates you professionally -->
- Learning new frameworks and technologies
- Building full products end-to-end (frontend + backend + deployment)
- Mentorship and working alongside senior developers
- Performance/SEO optimisation work

### Target Sectors
<!-- Industries and companies you're targeting -->
- Software/SaaS/product companies: Sklum, Ale-Hop, Mercadona Tech
- Technology consultancies: NTT DATA, Capgemini, Accenture, Sopra Steria, Inetum

### Deal-breakers
<!-- Hard constraints on job search -->
- No unpaid or underpaid roles (baseline expectation ~24,000-28,000 EUR gross/year)
- No long relocation-required contracts abroad

## Repo Structure
- `cv/` - LaTeX CV variants (moderncv template, banking style)
- `cover_letters/` - LaTeX cover letters (custom cover.cls template)
- `.claude/skills/` - AI skill definitions for the application workflow
- `.agents/skills/` - Job search CLI tools

## Workflow for New Job Applications
1. User provides a job posting (URL or text)
2. **Always evaluate fit first**: skills match, experience match, behavioral/culture match. Present this assessment to the user before proceeding.
3. If good fit: create targeted CV (`cv/main_<company>.tex`) and cover letter (`cover_letters/cover_<company>_<role>.tex`)
4. **Verify both documents** (see Verification Checklist below)
5. Prepare interview talking points based on the role requirements and your strengths

**Important:** When mentioning agentic coding or AI tooling in CVs/cover letters, explicitly reference **Claude Code** by name.

## Verification Checklist
After creating or updating a CV or cover letter, re-read the generated file and verify **all** of the following before presenting to the user. Report the results as a pass/fail checklist.

### Factual accuracy
- [ ] All claims match actual profile (CLAUDE.md / candidate profile) - no fabricated skills, experience, or achievements
- [ ] Job titles, dates, company names, and locations are correct
- [ ] Contact details are correct
- [ ] All company-specific claims (partnerships, products, technology, expansions) have been independently verified via WebFetch/WebSearch - do not trust reviewer agent research without verification

### Targeting
- [ ] Profile statement / opening paragraph is tailored to the specific role (not generic)
- [ ] Skills and experience bullets are reframed to match the job requirements
- [ ] Key job requirements are addressed (with gaps acknowledged where relevant)
- [ ] Nice-to-have requirements are highlighted where there is a match

### Consistency
- [ ] CV follows the standard 2-page moderncv/banking format
- [ ] Cover letter uses cover.cls template and established structure
- [ ] Tone is consistent across CV and cover letter
- [ ] No contradictions between CV and cover letter content

### Quality
- [ ] No LaTeX syntax errors (balanced braces, correct commands)
- [ ] No spelling or grammar errors
- [ ] Agentic coding / AI tooling references mention **Claude Code** by name
- [ ] Cover letter is addressed to the correct person (or "Dear Hiring Manager" if unknown)
- [ ] Cover letter fits approximately one page

### Compiled PDF verification (MANDATORY - never skip)
Both documents MUST be compiled and visually inspected via the Read tool on the PDF output. "Looks fine in the .tex" is not acceptable - LaTeX page-break decisions are unpredictable. Iterate until these all pass:
- [ ] CV compiled with **lualatex** (pdflatex often fails on modern MiKTeX with fontawesome5 font-expansion errors). Cover letter compiled with **xelatex** (cover.cls requires fontspec).
- [ ] **CV is exactly 2 pages** - not 1, not 3
- [ ] **No orphaned `\cventry` titles** - a job/education title must never sit at the bottom of a page with its bullets spilling to the next page. Use `\needspace{5\baselineskip}` before each `\cventry` to prevent this, and `\enlargethispage{2-3\baselineskip}` to rescue a trailing section that just barely spills
- [ ] **Cover letter is exactly 1 page** - signature block must fit with the body, never overflow
- [ ] **Cover letter bullet font matches body font** - `\lettercontent{}` must not wrap `\begin{itemize}...\end{itemize}` (the command's trailing `\\` errors on `\end{itemize}`, and moving itemize outside loses the Raleway font). Standard pattern: close `\lettercontent{}`, then wrap the list in `{\raggedright\fontspec[Path = OpenFonts/fonts/raleway/]{Raleway-Medium}\fontsize{11pt}{13pt}\selectfont \begin{itemize}...\end{itemize}\par}`

### ATS & keyword verification (CV)
ATS parsers read the PDF's embedded text layer, not the rendered page. Extract it with `pdftotext -layout` and verify what a parser sees. `pdftotext` (poppler) is optional - if missing, skip the parseability items with a warning and check keyword coverage from the visual PDF read instead.
- [ ] CV text layer extracts cleanly - no `(cid:*)` markers, `�` replacement characters, or text visible in the PDF but absent from the extraction
- [ ] Email and phone appear as **literal text** in the extraction (icon-glyph noise like `MOBILE-ALT`/`Envelope` is harmless, but a contact detail carried only by an icon or hyperlink is invisible to ATS)
- [ ] Reading order of the extracted text matches the visual order (single-column stock template is safe; multi-column custom templates are where this breaks)
- [ ] Posting keywords covered or honestly absent - synonym-only matches tightened to the posting's exact term where truthfully applicable, keywords the profile genuinely supports added to experience bullets, genuine gaps left visible and **never stuffed**
