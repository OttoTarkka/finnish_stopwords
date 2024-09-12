# finnish_stopwords
Basic list of Finnish stopwords for your NLP/corpus linguistics project.

I couldn't find a decent list of Finnish stopwords online, so I made my own. Feel free to use this list in your projects.
The list mainly includes Finnish pronouns and frequent adverbs as well as common punctuation. Some frequent verbs are included, too.
I've kept the list purposefully consise. Make sure the list suits your needs and modify accordingly before using it.


NB! You should make sure your data are tokenized and lemmatized! Use for instance Trankit: https://trankit.readthedocs.io/en/latest/index.html

Example usage:

```python
def remove_stopwords(data):
    with open('finnish_stopwords.txt', 'r') as f:
        stopwords = f.readlines()
        stopwords = [word.strip('\n') for word in stopwords] # Remove trailing newline character.
    data = [[token for token in sentence if token not in stopwords] for sentence in data]
    return data

data = [['tämä', 'olla', 'esimerkki#lause', ',', 'joka', 'mahtua', 'paljon', 'sana', '.'], ['tässä', 'olla', 'toinen', 'lause', '!']]
data = remove_stopwords(data)

#returns [['esimerkki#lause', ',' 'mahtua', 'paljon', 'sana', '.'], ['tässä', 'toinen', 'lause', '!']]
```
