# Which Role?

## Overview and Goals
The goal of this project is to create the best resumé matcher - identify what roles your resumé is most suited for.

*Project Value*. It can help advise job-seekers on potential career paths, what skills they currenty have and what education, skills or experience they need.

## Project Design
This problem can be solved with supervised learning - a model can be trained with dependent variables (y) identified by current job titles (e.g. data analyst, data scientist or data engineer) on resumés. Training the model would therefore only rely on resumés of job-seekers with work experience. 

The independent variables (X) will be a combination of:
1. word vectors / embeddings from the work experience, skills and education (schools, certificates) in the resumés; and
2. other information passed from the resumés (e.g. number of years of work experience, whether the person has a masters or how many).

Further improvement to this can be made with supporting rules-based code.

## Tools
+ SKLearn and Pandas, of course.
+ FuzzyWuzzy to identify similar terms in text - classify job titles (e.g. 'data scientist' or 'data science' are both data scientist resumés).
+ MongoDB to store resumés and parsed data.
+ AWS to run grid search to identify the best models.
+ Flask WebApp

## Data
Scraped and parsed around 80,000 resumés from Indeed.com.
Parsed fields include: 
+ Hyperlink
+ Job Title
+ Education: school name, course, certifications, level of education (Bachelors, Masters, PhDs, how many?)
+ Work Experience: number of years, text (for vectors)
+ Skills: text (for vectors)
+ Additional Information: text (for vectors)

Example resumé parsed according to these fields:
![my resumé](https://github.com/Karawkz/which_role/blob/master/Kara_Bethany_Liu_resum%C3%A9.png "my resumé")

## Algorithms / Modeling
**Vectorization**. I trained my own W2V model and vectorized the relevant texts. I decided against using Google Gensim's trained W2V model because I figured that many of the technical skills would not appear in there. However, I'd like to test this theory out some time in the future. I also used a TFIDF vectorizer.

**Dimension Reduction**. I also used 'truncated SVD' within Latent Semantic Analysis to get a smaller set of vectors, specifically I tried out dimensions of between 50 to 300 with my model.

**Oversampling**. The number resumé types were imbalanced - 3/5 of resumés were data analyst ones, 1/5 were data scientist ones and the remaining 1/5 were data engineering ones. I used ADASYN to oversample the data to balance these classes.

![imbalanced](https://github.com/Karawkz/which_role/blob/master/imbalance.png "too many analysts")

**Models**. I tried out a variety of classification models - Random Forest, Support Vector Classifier, Logistic Classifier, Multinomial Naïve Bayes, Gradient Boosting Classifier.

I tried a variety of vectorization methods and models using GridSearchCV to find the best model.

## Results
See slides summary: [Which Data Role](https://github.com/Karawkz/which_role/blob/master/which%20data%20role.pdf). The final model, which is my best model, did alright with ~85% accuracy on the test set and ~95% accuracy on the train set. This likely signals overfitting because the results were pretty similar across all models / vectors. I basically need more data and therefore need to scrape more resumés for this project in order to improve the results.

Data-related roles: match resumés according to whether they are most suited to data analytics, data science or data engineering roles.
Check it out - [Which-Data-Role Flask App](https://whichdatarole.herokuapp.com/)!

## WIP
+ Expand to include other roles.
+ Scrape more resumés.
+ Try modeling with Google Gensim's pre-trained model, LDA, NMF, etc.
+ Use a customized Named Entity Recognition model (perhaps with Spacy) to identify items within education, work experience, skills in a resumé and see how they contribute to how a resumé is classified.
