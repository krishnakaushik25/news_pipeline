# news_pipeline

**Objective:** To construct a data pipeline to retrieve the 100 most common keywords of the most popular articles on Hacker News!!

A ,simple and directed acyclic graph(DAG) based, data pipeline filtering, cleaning, aggregating, summarizing json data from Hacker News( a social news website focusing on computer science and entrepreneurship , it's a link aggregator website that users vote up stories that are interesting to the community. It is similar to Reddit, but the community only revolves around on CS topics.).

Building a pipeline on a  real world data pipeline project.
Dataset  comes from a Hacker News (HN) API that returns JSON data of the top stories in 2014.For making it easier, I  downloaded a list of JSON posts to a file called hn_stories_2014.json.

For the purpose of editing title names, we need to get rid of certain grammar words which are stored in stopwords.py. We can also import stopwords from NLTK library.

Specifically, the data pipeline retrieves the 100 most populars keywords in the titles of articles in Hacker News.

Each post has a set of keys. Here is a description of the most relevant keys:

* `created_at` - A timestamp of the story's creation time
* `created_at_i` - A unix epoch timestamp
* `url` - URL of the article's link
* `objectID` - Unique ID of the story
* `author` - The author's username on Hacker News
* `points` - The number of upvotes
* `title` - The title of the story
* `num_comments` - The number of comments for the article on Hacker News

**Techniques used:**
* Natural language processing
* JSON, datetime, data pipeline
* Function decorators

Functions implemented in pipeline are:
#### file_to_json: loads 'hn_stories_2014.json' file into a dictionary and return it
#### filter_stories: return a generator of filtering popular stories that have more than 50 points, more than 1 comment, and do not begin with 'Ask HN'
#### json_to_csv: build a virtual csv file and put the transformed json data onto the file
#### extract_titles: returns of every Hacer News story title
#### clean_titles : get rid of punctuation and transform each title into lower case and then return it
#### build_keyword_dictionary: return a dictionary of the word frequency in a title
#### top_keywords : sort the result from build_keyword_dictionary decreasing order then return first 100 results.

## Support 

If you like this repo and find it useful, please consider (★) starring it (on top right of the page) so that it can reach a broader audience.
