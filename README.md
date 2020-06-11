#  Investigation and prediction of human interactome based on quantitative features 
## Abstract
Protein is one of the most significant components of all living creatures. All significant and essential biological structures and functions relies on proteins and their respective biological functions. However, proteins cannot perform their unique biological significance independently. They have to interact with each other to realize the complicated biological processes in all living creatures including human beings. In other words, proteins depend on interactions (protein-protein interactions) to realize their significant effects. Thus, the significance comparison and quantitative contribution of candidate PPI features must be determined urgently. According to previous studies, 258 physical and chemical characteristics of proteins have been reported and confirmed to definitively affect the interaction efficiency of the related proteins. Among such features, essential physiochemical features of proteins like stoichiometric balance, protein abundance, molecular weight and charge distribution have been validated to be quite significant and irreplaceable for protein-protein interactions (PPIs). Therefore, in this study, we, on one hand, presented a novel computational framework to identify the key factors affecting PPIs with Boruta feature selection (BFS), Monte Carlo feature selection (MCFS), incremental feature selection (IFS) and on the other hand, built a quantitative decision-rule system to evaluate the potential PPIs under real conditions with random forest (RF) and RIPPER algorithms, thereby supplying several new insights into the detailed biological mechanisms of complicated PPIs. <br>
<br>

## Package dependencies
  * <a href=https://waikato.github.io/weka-wiki/downloading_weka/>Weka</a> <br>


# Required data
The uploaded data data.zip in this respository contains: <br>
1. train_166.arff and test_166.arff are the training and test set with 166 features. <br>
2. train_90.arff and test_90.arff are the training and test sets with 90 features. <br>

# Run the analysis
To run the analysis, please use Weka command as below (Take the training data train_90.arff and test data test_90.arff as examples) <br><br>
1. For 10-fold cross-validation training on the training data: <br>
java -Xmx16g -classpath /sibcb/program/install/weka-3.8/weka.jar weka.classifiers.trees.RandomForest -P 100 -I 100 -num-slots 1 -K 0 -M 1.0 -V 0.001 -S 1 -t train_90.arff -x 10 -p 0  > result_train.arff <br>
2. For making prediciton on the test data:  
java -Xmx16g -classpath /sibcb/program/install/weka-3.8/weka.jar weka.classifiers.trees.RandomForest -P 100 -I 100 -num-slots 1 -K 0 -M 1.0 -V 0.001 -S 1 -t train_90.arff -T test_90.arff -x 10 -p 0 > result_test.arff
<br>

