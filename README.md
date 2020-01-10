# Negation-Conflict-Detection-in-User-Story
This reposotory includes a code that provides negation conflict detection in agile user story requirements. An example of a negation conflict is the pair of user stories "As a user, I want to be able to have multiple accounts" and "As a developer, users should not have multiple accounts". 

The approach is to deploy a paragraph vectors model<sup>1</sup> to encode user story requirements as vectors. Paragraph vectors model is developed using Gensim<sup>2</sup>. The vectors are used as input features to a Support Vector Machine (SVM) classifier. Each input consists of two vectors corresponding to two different user stories. In addition to the vectors, two other features are used. The features are Negation and Jaccard Coefficient. Negation is a binary feature, and it is set to 1 if a sentence includes a negation, and it is set to 0 otherwise. Jaccard Coefficient is the ratio of common words in two sentences to the total number of words. 

A problem with this approach is the lack of annotated user story dataset. So, transfer learning is utilized to overcome this issue. Stanford’s Recognizing Textual Entailment (RTE) dataset<sup>3</sup> was used to train and test models. Then, the models are validated on a small manually annotated user story dataset. 

More details could be found in the attached report.

<sup>1 https://cs.stanford.edu/~quocle/paragraph_vector.pdf</sup>  
<sup>2 https://radimrehurek.com/gensim/index.html</sup>  
<sup>3 https://nlp.stanford.edu/projects/contradiction/</sup>  
