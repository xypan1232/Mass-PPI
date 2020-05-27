#  Investigation and prediction of human interactome based on quantitative features 

## Package dependencies
  * <a href=https://waikato.github.io/weka-wiki/downloading_weka/>Weka</a> <br>


# Required data
In the uploaded data data.zip: <br>
1. train_166.arff and test_166.arff are the training and test set with 168 features. <br>
2. train_90.arff and test_90.arff are the training and test sets with 90 features. <br>

# Run the analysis
To run the analysis, please use Weka command as below (Take the training data train_90.arff and test data test_90.arff as examples) <br>
For 10-fold cross-validation training on the training data: <br>
java -Xmx16g -classpath /sibcb/program/install/weka-3.8/weka.jar weka.classifiers.trees.RandomForest -P 100 -I 100 -num-slots 1 -K 0 -M 1.0 -V 0.001 -S 1 -t train_90.arff -x 10 -p 0  > result_train.arff <br>
For making prediciton on the test data: <br>  
java -Xmx16g -classpath /sibcb/program/install/weka-3.8/weka.jar weka.classifiers.trees.RandomForest -P 100 -I 100 -num-slots 1 -K 0 -M 1.0 -V 0.001 -S 1 -t train_90.arff -T test_90.arff -x 10 -p 0 > result_test.arff
<br>

