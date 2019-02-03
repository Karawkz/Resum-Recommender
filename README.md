# Which Role?

## Overview and Goals
The goal of this project is to create the best resumé matcher - identify what roles your resumé is most suited for.

*Project Value*. It can help advise job-seekers on potential career paths, what skills they currenty have and what education, skills or experience they need.

## Project Design
This problem can be solved with supervised learning - a model can be trained with dependent variables (y) identified by current job titles (e.g. data analyst, data scientist or data engineer) on resumés. This would therefore only apply to resumés of job-seekers with work experience. 

The independent variables (X) will be identified by:
1. word vectors / embeddings from the work experience, skills and education (schools, certificates) in the resumés; and
2. other information passed from the resumés (e.g. number of years of work experience, whether the person has a masters or how many).

Further improvement to this can be made with supporting rules-based code.

## Tools
+ SKLearn and Pandas, of course.
+ Google Gensim's W2V model.
+ FuzzyWuzzy to identify similar terms in text - classify job titles (e.g. 'data scientist' or 'data science' are both data scientist resumés).
+ MongoDB to store resumés and parsed data.
+ AWS to run grid search to identify the best models.
+ Flask WebApp

## Data
Scraped and parsed resumés from Indeed.com.
Parsed fields include: 
+ Hyperlink
+ Job Title
+ Education: school name, course, certifications, level of education (Bachelors, Masters, PhDs, how many?)
+ Work Experience: number of years, text (for vectors)
+ Skills: text (for vectors)
+ Additional Information: text (for vectors)

## Algorithms

## Results
**Update Jan 2019**. Data-related roles: match resumés according to whether they are most suited to data analytics, data science or data engineering roles.
Check out my [Which-Data-Role Flask App](https://whichdatarole.herokuapp.com/)!

## WIP
+ Expand to include other roles.
+ NER - identify items in a resumé and see if they make sense.
