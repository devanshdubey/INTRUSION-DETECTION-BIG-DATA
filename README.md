# INTRUSION-DETECTION-BIG-DATA


##Dataset preprocessing
Two datasets are used in theis work, USNW-NB15 and CICIDS2017 datasets.To provide a more suitable data for the neural network classifier, the dataset is passed through a group of preprocessing operations. These operations are summarized below:

1.Remove socket information: As the original dataset includes the IP address and Port numbers of the source and destination hosts in the network, it is important to remove such information to provide unbiased detection, where using such information may results in overfitted training toward this socket information. However, it is more important to let the classifier learn from the characteristics of the packet itself, so that, any host with similar packet information is filtered out regardless to its socket information.

2.Remove white spaces: Some of the multi-class labels in the dataset include white spaces. Such white spaces result in different classes as the actual value is different from the labels of other tuples in the same class. 
3.Label encoding: The multi-class labels in the dataset are provided with the attack’s names, which are strings values. Thus, it is important to encode these values into numerical values, so that, the classifier can learn the class number that each tuple belongs to. This operation is executed using the multi-class labels only, as the binary labels are already in zero-one formation.

4.Data normalization: The numerical data in the dataset are of different ranges, which poses some challenges to the classifier during training to compensate these differences. Thus, it is important to normalize the values in each attribute, so that, the minimum value in each attribute is zero, while the maximum is one. This provides more homogeneous values to the classifier while maintaining the relativity among the values of each attribute.

5- Remove / replace massing and infinity values: CICIDS2017 contain 2,867 tuples as missing and infinity values, this has been addressed in two ways: first, to delete the missing and infinite values, and the second to replace the infinite values with the maximum value and the missing values with the average values.

6- for multiclass classification, Information packets that represent normal network traffic from both data sets are deleted and only the attack information packets are kept. 
