# musicnn
Pronounced as "musician", `musicnn` is a set of pre-trained deep convolutional neural networks for music audio tagging.

Check the [documentation](https://github.com/jordipons/musicnn/blob/master/DOCUMENTATION.md) and some [basic](https://github.com/jordipons/musicnn/blob/master/basic%20example.ipynb) / [advanced](https://github.com/jordipons/musicnn/blob/master/advanced%20example.ipynb) examples for additional ideas on how to use `musicnn`.

Do you have questions? Check the [FAQs](https://github.com/jordipons/musicnn/blob/master/FAQs.md).

## Installation
``` git clone https://github.com/jordipons/musicnn.git```

``` pip install numpy librosa```

```pip install tensorflow``` or ```pip install tensorflow-gpu``` (if you have a GPU)

## Run

From within **python**, you can estimate the **topN** tags:
~~~~python
from musicnn.tagger import top_tags
top_tags('./audio/joram-moments_of_clarity-08-solipsism-59-88.mp3', model='MTT', topN=10)
~~~~
>['techno', 'electronic', 'synth', 'fast', 'beat', 'drums', 'no vocals', 'no vocal', 'dance', 'ambient']

Let's try another song!

~~~~python
top_tags('./audio/TRWJAZW128F42760DD_test.mp3', model='MTT', topN=3)
~~~~
>['guitar', 'piano', 'fast']

----------------------------

Alternatively, from the **command-line**, print to the **topN** tags on the screen:

~~~~python

~~~~python
python -m musicnn.tagger ./audio/joram-moments_of_clarity-08-solipsism-59-88.mp3 --topN 10 --print_tags
python -m musicnn.tagger ./audio/TRWJAZW128F42760DD_test.mp3 --topN 3 --print_tags
~~~~~~~~

or save to a file:

~~~~python
python -m musicnn.tagger ./audio/joram-moments_of_clarity-08-solipsism-59-88.mp3 --output out.tags --topN 10
python -m musicnn.tagger ./audio/TRWJAZW128F42760DD_test.mp3 --output out.tags --topN 3
~~~~

----------------------------

You can also compute the **taggram** from python (see our [basic](https://github.com/jordipons/musicnn/blob/master/basic%20example.ipynb) example for more details on how to depict it):

~~~~python
from musicnn.extractor import extractor
taggram, tags = extractor('./audio/joram-moments_of_clarity-08-solipsism-59-88.mp3', model='MTT')
~~~~
![Taggram](./images/taggram.png "Taggram")

The analyzed music clips are included in the `./audio/` folder of this repository. 

You can listen to those and evaluate `musicnn` yourself!
