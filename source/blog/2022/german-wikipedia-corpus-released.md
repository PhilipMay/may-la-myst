# Clean German Wikipedia Text Corpus released

:::{post} 2022-02-22
:::

Today I published a new Wikipedia-based German text corpus. It is to be used for NLP machine learning tasks.

:::{figure} /\_static/img/wikipedia.png
:width: 550px

Wikipedia
:::

The corpus is based on a database dump.
This was unpacked with [WikiExtractor](https://github.com/attardi/wikiextractor).
Then a script is provided to split the texts into sentences.
This is done by using [SoMaJo](https://github.com/tsproisl/SoMaJo).
Each line of the text corpus contains one single sentence.
Between each Wikipedia article is a blank line.

For splitting sentences we have tested SoMaJo extensively and
it produces better results than other much more popular classic NLP tools like [spaCy](https://spacy.io/).

Both the code for preprocessing and the corpus itself can be downloaded from GitHub here:
<https://github.com/GermanT5/wikipedia2corpus>
