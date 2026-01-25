# us-civics-exam-2008-spa

-index.html -A Single Webpage Application for the US Citizenship Civics Exam (2008 Edition)



# us-civis-exam-2025-spa
- 2025.html - A Single Webpage Application for the US Citizenship Civics Exam (2025 Edition)
- https://www.uscis.gov/sites/default/files/document/questions-and-answers/2025-Civics-Test-128-Questions-and-Answers.pdf




# notes
```
curl https://www.house.gov/representatives | htmlq -p --text 'div.view-housegov-reps-by-name > div.view-content > table.table > tbody > tr > td:nth-of-type(1)' > reps
curl https://www.house.gov/representatives | htmlq -p --text 'div.view-housegov-reps-by-name > div.view-content > table.table > tbody > tr > td:nth-of-type(2)' > districts
paste -d "\t" reps districts  | sort -t $'\t' -k 2 | column -t -s $'\t' > sorted



curl https://www.senate.gov/senators/ | htmlq -p --text ' table> tbody > tr > td:nth-of-type(1)' > senators

curl https://www.senate.gov/senators/ | htmlq -p --text ' table> tbody > tr > td:nth-of-type(2)' > states
paste -d $'\t' states senators | sort | column -t -s $'\t' > sensorted

curl https://www.nga.org/governors/ | htmlq --text '.current-governors__item__link'
```
