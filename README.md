# Decision-Tree
Decision Tree implementation using ID3 algorithm(using entropy function to calculate information gain by each attribute).

The code structure follows the order :

 1) Reading data from csv file and splitting into training(70%) and testing data(30%)
 
   - Training data is used to train or to feed to make our deceion tree classifier
   - Testing data is to check the accuracy of our classifier
 
 2) Various utility functions to read and arrange the data to the requirement
     
   - unique_vals  : to find the unique values for a column ina dataset
   - class_counts : to count the number of each type of examples in the dataset
   - is_numeric   : to test if the value is numeric
   
 3) Question Class 
 
    - to generate a question based on attribute
    
 4) Partition
 
    - to partition the data based on the question generated
      - true values
      - false values
 
 5) Entropy Function
 
    - To calculate the randomness of the partition
    
         - H(attribute) = -(plog(p) + (1-p)log(1-p))
         
 6) Information Gain
 
    - IG = entropy(parent) - average entropy of children
    
 7) Best_Split
 
    - Based on the information gain from each attribute we select the decision attribute which has the maximum information gain
    
 8) Process to build our Decision tree
 
    - Leaf definetion : stores row, leaf id, and depth;  (stores class)
    
    - Decision Node defination : stores the question, truebranch, falsebrabch, id, depth, pruning
    
    - buid tree function
         - here we build our tree based on the decision attribute select based on maximum information gain
         - if the information gain is zero, make it a leaf node  (base case for the recurion call)
         - otherwise recursively builld the true brach and false branch
         
  9) Classify
  
     - This is predictor function which will traverse the tree and reach one of the leaf node to return one of the defined class
     
  10) Various print functions
  
     - To print the Decision tree
     - To print the leaf nodes ( defined classes )
     - To print the inner nodes ( Decision attributes )
   
  11) Accuracy function
  
      - To calculate the accuracy of the classifier
           - we keep a count of the number of times a classifier predicted correctly.
           
  12) Finally the Post Pruning
  
      Decision tree tend to overfit the data, so to tackle this we use 2 methods 
      
      - restrict the tree to grow during the build phase based on certain conditions
      
      - We let the tree grow completely and then do post pruning
      
      Here we have used the post pruning to handle the overfitting.
      
       > to remove nodes we are selecting nodes in to different ways 
             1) Randomly selecting from  innernodes (execpt the root node)
             2) delecting the parent node of all the leaf nodes
      
    
         
   
  
