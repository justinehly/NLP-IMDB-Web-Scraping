# NLP-IMDB-Web-Scraping
 
Summary
IMDB Site Scrubbing
I started the homework assignment using Beautiful Soup to scrape the list of the top 50 comedies from imdb.com that included the comedy title, link to the movie's page, main talent in the movie (Directors and Actors) and permalinks to each individual review. Since the scope of this project was limited to 100 reviews, I only used the first 5 reviews of the top 20 movies and ensured there were at least 5 reviews for each movie. This was done using a combination of list comprehensions within functions within a class object.

NP-chunk
In this section I used the permalinks to grab the individual reviews for each of the top 20 movies (that had at least 5 reviews, note of the 50, only 1 comey did not have 5 reviews and that is because it has not been released it and stars Sandra Bullock).

I then used the NLTK sent_tokenizer, word_tokenizer and pos_tag functions to breakdown each movie review using a combination of list comprehensions within functions within a class. I then inspected the first sentence of the first review our of curiosity.

Next I checked to see if there were any missing chunks by using the Counter from the collections package to count how many of each POS existed in my corpus.to my surprise, there were 182 with a very strange label, that on further inspection returned a null list so it might've been some blank space lurking.

Next I just chunked for Noun Phrase chunks using the RegexpParser and a manual grammar setting of 
NP: {??<NN.*>}

Wrap it up
After about 3 days of trial and error, well just error, I could not figure out how to add anything to the lexicon nor manually update the talent name POS tags in order to re-chunk. But I did ensure that all the names I scraped from the IMDB website were represented in the POS tags; although, only 95 were correctly tagged as NNP, so there is a chance that quite a bit of information was lost in this process.
Below is the output of how the pos_tag thought they should be represented:
'NN': 264,
'NNP': 95,
'FW': 2,
'NNS': 21,
'VB': 4,
'VBG': 1,
'JJ': 9,
'VBN': 2,
'RB': 1,
'IN': 1,
'MD': 1})
