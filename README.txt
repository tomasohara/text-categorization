Wed 04 Jul 18

This is an adhoc project for text categorizaton over wikipedia, developed using Skikit-Learn. It can be adpapers for other languages by creating a mapping from user categoried into Simple English Wikipedia user categiries. It can also serve as a sample for running different classifiers over the same data. Currenly, it supports SVM's and Stochastic Gradient Descent.

Data on the project can be found as follows
     http://www.scrappycito.com:9330/static/info/customizations/simple-english-wikipedia-text-categorization.zipData on the project can be found as follows:
That uses a more restrictive license thah LGPLv3, Namedly based on Creative Commons, so it is not included in this distribution of the code proper.

For an example customization. one can create a mapping from Spanish Wikipedia pages into a set of about five dozen user categories. Second, you would create a text categorizer by taking a random sample of articles for each category and running the data through a text categorization system to come up with a model for classfying unseen text (i.e., not used during training). Lastly, you would prepare test cases that will help to ensure that the model is representative of Spanish in general (e.g., countries in the New World as well as Spain).

Using Simple English wikipedia, here's a few examples for the mappings:

    Article           category
    andy_dick         people
    richard_wright    people
    julian_galilea_martinez_de_pinillos    people
    amy_heckerling    movie
    barnett_newman    people

This is derived by analyzing the category information in Wikipedia to find a representative set, based on intuition and the number of articles tagged with it. See below for how the categories are specified. Simple Regex patterns are used to extract the categories. These might need to be adjusted as each Wikipedia tends to use different conventions. (Although Wikipedia has a special data file with the categories, extracting then from the Wikipedia article source seemed to produce better results.)

Once the mapping has been created, there are Python scripts that do the following: simple text preprocessing; model training for the text categorizer; and testing over different data. One script will extract the article text and select the most representative category. (This might need to be modified for the language.) Another script will create the training data for the Sklearn package, and it will also support testing over a separate test set (e.g., based on random split). Some experimentation with the parameter for the machine learning algorithm will be necessary to obtain optimal results. I tried Support Vector Machines, but Stochastic Gradient Descent worked better.

Tom O'Hara
Decmeber 2018
