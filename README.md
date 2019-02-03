# Which Role?

## Overview and Goals
The goal of this project is to create the best resumé matcher - identify what roles your resumé is most suited for.

*Project Value* It can help advise job-seekers on potential career paths, what skills they currenty have and what education, skills or experience they need.

## Project Design
This problem can be solved with supervised learning - a model can be trained with dependent variables (y) identified by current job titles (e.g. data analyst, data scientist or data engineer) on resumés. This would therefore only apply to resumés of job-seekers with work experience. 

The independent variables (X) will be identified by:
1. word vectors / embeddings from the work experience, skills and education (schools, certificates) in the resumés; and
2. other information passed from the resumés (e.g. number of years of work experience, whether the person has a masters or how many).

Further improvement to this can be made with supporting rules-based code.

## Tools


## Data
Scraped and parsed resumés from Indeed.com

## Algorithms

## Results
**Update Jan 2019**. Data-related roles: match resumés according to whether they are most suited to data analytics, data science or data engineering roles.
Check out my [Which-Data-Role Flask App](https://whichdatarole.herokuapp.com/)!

## WIP
+ Expand to include other roles.
+ NER - identify items in a resumé and see if they make sense.
