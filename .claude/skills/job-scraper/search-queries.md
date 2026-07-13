# Search Queries for Job Scraper

<!-- SETUP: Customize these queries based on your skills, target roles, and location -->

## Search Sites

Primary (no Spain-specific portal skill is installed yet - scaffold one with `/add-portal`, e.g. for InfoJobs or Tecnoempleo):
- **linkedin.com/jobs** - LinkedIn job listings (filter: Spain / Valencia / Gandia, and remote)
- **Google site-search** - `site:infojobs.net`, `site:tecnoempleo.com`, `site:indeed.com` etc. until a dedicated portal skill exists

Secondary (company career pages via Google):
- Direct Google searches with `site:` filters for known target companies (Sklum, Ale-Hop, Mercadona Tech, NTT DATA, Capgemini, Accenture, Sopra Steria, Inetum)

## Query Categories

Queries are grouped by priority. Each query should be combined with your location terms (e.g. your city, region, or metro area) where the site supports it.

### Priority 1: Junior Full Stack Developer

These match your strongest and most desired career direction.

```
site:linkedin.com/jobs "junior full stack developer" Valencia
site:linkedin.com/jobs "desarrollador full stack junior" España
site:infojobs.net "full stack junior" Angular Spring Boot
```

### Priority 2: Junior Backend Developer (Java / PHP)

These match your domain expertise.

```
site:linkedin.com/jobs "junior java developer" Spring Boot Valencia
site:linkedin.com/jobs "junior PHP developer" Laravel España
site:tecnoempleo.com "desarrollador junior" Laravel OR "Spring Boot"
```

### Priority 3: Junior Software Engineer (Adjacent)

Adjacent roles you could pivot into, including at larger consultancies.

```
site:linkedin.com/jobs "junior software engineer" España Angular OR Java OR PHP
site:linkedin.com/jobs "graduate developer" NTT DATA OR Capgemini OR Accenture OR "Sopra Steria" OR Inetum
```

### Priority 4: Broader Technical / WordPress-SEO

Wider net, including the WordPress/SEO track from the internship.

```
site:linkedin.com/jobs "wordpress developer" junior Valencia
site:linkedin.com/jobs "web developer" junior remoto España
site:infojobs.net "desarrollador web" junior WordPress OR SEO
```

## Location Filter

When evaluating results, verify the job location is within reasonable commute distance from home, or is fully remote. Define acceptable areas:
- Gandia and surrounding areas (ideal)
- Valencia city and Valencia region (acceptable - on-site or hybrid)
- Fully remote anywhere in Spain (acceptable)
- Other Spanish cities requiring relocation (borderline - discuss with user before applying)
- Roles requiring relocation outside Spain (too far - deal-breaker)

## Date Filter

Only include jobs posted within the last 14 days, or with an application deadline that has not yet passed. If a posting date cannot be determined, include it but flag as "date unknown".

## Adapting Queries

If the user specifies a focus area, select queries from the matching category and also generate 2-3 custom queries for that focus. For example:
- "/scrape [focus_area]" -> relevant category queries + custom focus-specific queries
