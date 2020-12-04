# Toxic_Spans_Detection

Running the application is very straightforward.  Upload the file to Google colab and upload the dataset of toxic spans to your google drive.  
Set the variable 'data_source' to the location of the csv file in your Google drive (see mine as an example).

The code will run as-is, but feel free to adjust the variables in General options.  The following can be adjusted:

# These variables you probably shouldn't change, but can if you want.
use_lemmas - True if you want to use word lemmas rather than the word themselves.
remove_extra_whitespace - True if you want to remove remove unnecessary and redundant whitespace that can mess things up
remove_punctuation - True if you want to remove all punctuation except apostrophes
remove_pronouns - True if you want to remove pronouns. I don't see how pronounons can be toxic and by using lemmas they'll be set to -PRON- anyways
remove_stopwords - True if you want to remove stopwords.  
make_lowercase - True to make the entire sentence lowercase.  Good for processing, although caps can indicate keyboard-rage.

# These variables can and should be played with
max_span_length - (int) this is for pre-processing.  Some spans are ridiculously long and that's generally a sign of bad annotating.
min_span_length - (int) this is for results.  how toxic can 2 characters really be?
W2V_window - (int) the window size in Word2Vec.
W2V_size - (int) the number of values in the vector.  Higher increases processing time.

# And my personal favorite
classifier: (knn, sgd, random_forest) You can choose between 1 of 3 classifiers.  SGD doesn't work well at all, but knn gets nice results.  random_forest takes a long time to process.  My suggestion is KNN.
