<h1>Executive Summary</h1>

Text Analytics is gaining importance with each passing day and individuals and organizations are exploring ways to use this to their own advantage. We too attempt to leverage the benefits of text analytics and implement it in the area of human resources to gain some meaningful insights useful for both the organizations and candidates looking for jobs. Social media data has been exploited to understand the pulse of general populace for a product or service, but we try to look at the employees view of employers. We extract employee reviews from Glassdoor for textual analysis to understand the employer brand and employee’s satisfaction with their employers.

The organizations we analyze in this study are Microsoft, Amazon, Google and IBM. The reviews are anonymous, and we extract all the reviews from 2008 to 2020. We applied well researched text analytical methods like sentiment analysis and similarity score analysis in this study. We also experiment with different ways of doing the analysis to ensure we use what is suitable for the corpus and task we have at hand.  

We found that the employee satisfaction with all the companies have declined from 2008 and Google and Microsoft are doing better on employee satisfaction metric compared to Amazon and IBM. We also identify the characteristics which are fetching highly positive and highly negative reviews for each of these companies. The results of this study are aggregated into a dashboard for easy reference.

<h1>Problem Definition and Significance</h1>

Every organization has a reputation, which includes thoughts attached to its products and services, history and people involved. People, over time develop this reputation and associate certain characteristics with an organization. This becomes the brand of a company. In a similar way, every organization has a secondary brand called Employer brand, which is the emotional reaction people have to the idea of working for an employer. This brand lives in the minds of employees - former, current and future. 

Companies with positive employer brands stand to gain in more than one way. The most significant impact a positive employer brand has on a company is in the area of recruitment. It is noted that companies with positive employer brands can get up to twice as many applicants as companies with negative brands and the costs drop by almost 43%. We don’t have to stress further how important this is, especially in the era when it is getting difficult to hire the right talent. Also, to gauge the significance of employer brand, one can look no further than the costs incurred by companies who fail to invest in their reputation as an employer, which is on an average $5,000 per employee.

In addition, 78% of candidates look at the company’s employer brand before applying for a job and 88% of millennials2 believe that being part of the right company is of at most importance. We all know how important salary is for job applicants, but a CareerBuilder report found that 67% of candidates are willing accept lower pay to be part of a company that has positive reviews online. It is becoming increasingly important for companies to build a positive employer brand on social media platforms as 79% of candidate pool are likely to use of social media in their job search.

Keeping these details in mind, we set out to explore employer brand and employee satisfaction of four major employers in the U.S. We intend to find the key characteristics of these companies which are fetching high positive and negative reviews and chart out the employee satisfaction from the reviews provided on social media platform Glassdoor. A collective dashboard with these findings will help employers make decisions to either improve or alter employer brand and potential job candidates to identify a preferred employer.

<h1>Prior Literature</h1>

The areas of employer branding and employee satisfaction have always dominated analytics domain in Human Resources function and are looked at extensively by many people and organizations. Although there has been lot of research on these topics, there was limited work which looked at Text mining employee reviews on social media to obtain employer brand characteristics and employee satisfaction. 
Employee Satisfaction and Corporate Performance3 looked at mining employee reviews from Glassdoor to understand the relation between employee satisfaction and organizational performance across industries. The study found that there is a positive correlation between general employee satisfaction and corporate performance along with the categories which correlated positively and negatively with performance. Improving Employee Satisfaction Through Text Analytics4 explored the employee satisfaction of six technology companies using predictive rule-based model on text portions of the reviews from Glassdoor. The study found the words from text which make the review positive or negative using classification techniques. Text Mining Company Reviews5 tried to find what employees write the most about their workplace experience and if they viewed the organization positively, negatively or neutrally. The study looked the frequency of single words and two words together to look at what was most talked about and ran sentiment analysis on the reviews to understand the variation of sentiment across the time range of reviews. 

However, these studies did not go on to make a comprehensive analysis on employer brand and were limited to sentiment analysis and extracting the most frequent words. Thus, we try to take inspiration from these works and use them as foundation to provide both organizations and employees a comprehensive analysis on employer characteristics that are viewed favorably and unfavorably along with the variation in employee satisfaction over the years.  

<h1>Data Source and Preparation</h1>

Social media has had large impact on multiple areas including in the domain of Analytics. The abundant of social media data made the data gathering easier for all types of analysis. One such social media platform is the Glassdoor website. Glassdoor.com was founded by Robert Hohman, Rich Barton and Tim Besse in 2007 (Glassdoor: About Us 2016). It is a website where current and former employees anonymously provide review for their respective companies. Glassdoor covers a diverse user population where users’ profiles are fairly distributed across different sectors such as age, income, education6. Glassdoor contains 475,000+ companies with more than 8 million company reviews, company ratings along with salary reports from worldwide locations. 

We used Web crawling technique to get the data from Glassdoor.com. We scraped the
reviews for four major employers in US – Microsoft, Google, Amazon and IBM and crawl a total of 100,000+ reviews from 2008 to Mar 2020. Figure 1 below shows the final generated corpus.

 
Figure 1: Sample of the data scraped from Glassdoor

The text data under Pros and Cons was then cleaned and preprocessed for analysis. As the analysis is only as good as data we provide, we spent some considerable time in preprocessing the data. The process involved replacing null values, fixing contractions, removing special characters and numbers, removing stop words, tokenization using word ninja and lemmatization using NLTK.

<h1>Text Analytics Workflow</h1>

Once the data from Glassdoor is extracted, we must consider (or construct) a systematic methodology for analyzing the text. In figure 2 below, we provide the framework that we follow for this analysis. Armed with this framework, we perform text processing for data cleaning as described in previous section, which is in turn used as source for subsequent analysis. Once the basic exploration is done on the prepared corpus, sentiment analysis will be performed to assign the polarity of each review. 

Later, n-grams are extracted from text (both pros and cons) along with its corresponding sentiment score. Top bi-grams and tri-grams are identified by the frequency of occurrence in the corpus for each company as these are the most talked in the reviews. Next, we perform Similarity score analysis to identify unique n-grams and zero in top 5 positive and negative n-grams by average sentiment score. The results are then aggregated on a comprehensive dashboard.

 
Figure 2: Flow chart depicting the process flow for the study

<h1>Exploratory Data Analysis</h1>

We tried to explore the data we have gathered to gain more insights into the data before doing any textual analysis. In this process, we tried to get answers for below questions;
•	Number of reviews per company
•	Rating distribution by company
•	Word count in reviews
•	Polarity score by company

<h3>1. Number of reviews per company</h3>

The figure 3 below shows the total number of reviews by company along with the distribution between Current, former and employees with no status. We can observe that Amazon has a lot more reviews compared to other firms followed by IBM, Microsoft and Google. Also, among those categorized as current and former employees, current employees have more reviews for all the companies.  
 
Figure 3: Distribution of reviews by company

<h3>2. Rating distribution in the companies</h3>

Looking at the rating distribution by company on a scale of 1-5 (5 being the best) in figure 4 below, we can conclude that all the companies were predominantly rated either 4 or 5. Interestingly, Microsoft is the only firm with more 4 ratings than 5 ratings.   
 
Figure 4: Rating distribution by company

<h3>3. Word count in reviews</h3>

We wanted to see how long (in words) the reviews were typically to understand if we can infer some meaning from the text. A review with just few words would not have helped the analysis as most of the words would be stop words or words with no real meaning. But much to our comfort, the reviews were not too short with most falling under the range of 5-15 words for both pros and cons. Figure 5 and 6 show the distribution of words in pros and cons respectively.

 
Figure 5: Word count in pros text

 
Figure 6: Word count in cons text

<h3>4. Polarity score distribution by company</h3>

Another important analysis we wanted to explore was the distribution of sentiment score for each company. Consistent to the ratings, the sentiment score was predominantly on the positive side (Figure 7). Although, there were some anomalies, the ratings were consistent with the polarity distribution. In other words, reviews which had good ratings (4 or 5) had high positive polarity score. Figure 8 shows the distribution of polarity score for reviews that were rated 3 or below. Ideally, we would have liked to see a lower polarity score for these but almost 19,000+ reviews show high polarity score of >0.6.

   
   
Figure 7: Polarity score distribution for each review by company

 
Figure 8: Polarity score of reviews that were rated 3 or below.

