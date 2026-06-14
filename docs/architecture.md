# Architecture

1. Apify scrapes 150 LinkedIn jobs across 3 search URLs daily at 08:30
2. Each job is scored 1-10 by Claude API using the prompt in /prompts
3. Jobs scoring below 6 are filtered out
4. Remaining jobs are checked against Make Data Store for deduplication
5. New jobs create Trello cards with score, verdict, reason, location, and link

## Deduplication
Uses an idempotent check-before-write pattern. The data store acts as a 
persistent key-value index. Running the pipeline twice on the same data 
produces identical output.