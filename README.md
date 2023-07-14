
# NLP Project: Classification of real/fake translator CVs

I came up with the idea for this NLP project while browsing a bunch of e-mail messages with appended CVs in pdf-format from individuals offering translation services. The faulty syntax of their contents made me suspicious, because being a linguist you should put all your efforts into writing correct English even if you are not a native speaker.

Later, I found out that there are actually scammers out there who send e-mail messages with fake resumes. If you order a translation from them, after having made an advance payment you actually get a Google-translated text. This is obviously annoying for the customers and poses a legitimacy problem for the translation industry. 

A translator fed-up with this situation even tried to address it compiling a list of e-mail addresses from fake translators. He publicized this information in his own website [Translator Scammers](http://www.translator-scammers.com/) and asked fellow translators to resend him e-mail messages from these supposed translators they thought to be actually fake. Eventually the list of translator scammers grew to be several thousand entries long.

I thought that it would be nice to be able to automatically detect these fraudulent messages.

So I have tried to develop a classification model for translator resumes. My data corpus consists in legitimate resumes automatically downloaded from one of the biggest virtual communities for translators/interpreters in the world: proz.com, on the one hand, and the fake resumes obtained from the several thousand e-mails identified as scam with the aid of master table from translator-scammers.com.

## The Bad Translator project

The project comprises several stages:

1. [Creation of the data corpus](dataset-prep/):

    a) legitimate resumes downloaded from proz.com

    b) fake resumes obtained by cross-referencing a master table from http://www.translator-scammers.com/ and about 10,000 e-mails messages received by an LSP.

    c) The resumes are available in pdf-format and had to be converted to text-only. Storage of the labelled resumes in a no-SQL database (MongoDB). Details here.


2. [Preprocessing of data corpus](analysis/):

    a) Analysis of the data corpus: segmentation, lemmatization, stemming, normalization, NER (Named Entity Recognition). Main tool: Spacy


3. [Testing of different classification models](models/):
