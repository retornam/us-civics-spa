# us-civics-exam-2008-spa
A Single Webpage Application for the US Citizenship Civics Exam (2008 Edition)


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
