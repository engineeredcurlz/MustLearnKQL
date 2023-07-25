
// Query that counts the votes:
Votes
| summarize Count=count() by vote
| as hint.materialized=true T
| extend Total = toscalar(T | summarize sum(Count))
| project vote, Percentage = round(Count*100.0 / Total, 1), Count
| order by Count

IP, anonymized id, vote, date-time - and the function used for counting the votes.Onboarding
| Score