# Job Search Agent

Automated LinkedIn job search pipeline built with Make, Apify, Claude API, and Trello.

Scrapes 150 LinkedIn roles daily, scores each against a candidate profile using 
Claude, deduplicates via Make Data Store, and routes matches to Trello automatically.

## Prompt versioning
The Claude scoring prompt lives in `prompts/scoring_prompt.txt` and is validated 
on every push via GitHub Actions.

## Stack
- Make (automation)
- Apify (LinkedIn scraping)
- Claude API (scoring)
- Trello (job tracking)
- GitHub Actions (CI/CD)