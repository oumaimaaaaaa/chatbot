# Chatbot Cool Moody
It can be difficult for some people to express their feelings or they might not be very aware of their own feelings. This project aims to create a chatbot that can be used to administer a self-reported assessment for psychological,and help you by suggesting tips and technologies.
# Install Packages
 Before starting to work on our chatbot we need to download a few python packages. We will simply use pip to install the following:
  <ul><li>numpy</li>
    <li>nltk</li>
  <li>pytorch</li>
</ul>

# Training Data
Now it's time to understand what kind of data we will need to provide our chatbot with. Since this is a simple chatbot we don't need to download any massive datasets. We will just use data that we write ourselves.we will need to create a .JSON file that contains the same format as the one seen below. I've called my file "pairs.json".
 <img src=pairs_img.png>
 
 What we are doing with the JSON file is creating a bunch of messages that the user is likely to type in and mapping them to a group of appropriate responses. The tag on each dictionary in the file indicates the group that each message belongs too. With this data we will train a neural network to take a sentence of words and classify it as one of the tags in our file. Then we can simply take a response from those groups and display that to the user. The more tags, responses, and patterns you provide to the chatbot the better and more complex it will be.
# NLP Basics
 We can't just pass the input sentence as it is to our neural net. We somehow have to convert the pattern strings to numbers that the network can understand. For this we convert each sentence to a so called bag of words (bow). To do this we need to collect training words, i. e., all the words that our bot can have a look at in the training data. Based on all these words, we can then calculate the bag of word for each new sentence. A bag of words has the same size as the all words array, and each position contains a 1 if the word is avaliable in the incoming sentence, or 0 otherwise. Here's a visual example:
    <img src=nlp_basic1.png>
    
  Before we can calculate the bow, we apply two more NLP techniques: Tokenization and Stemming: -Tokenization: Splitting a string into meaningful units (e.g. words, punctuation characters, numbers) -Stemming Generate the root form of the words. It's a crude heuristic that chops of the ends off of words For our labels, we sort them alphabetically and then use the index as class label. Our whole preprocessing pipeline looks like this: 
   <img src=nlp_basic2.png>
  
  # Implement The NLP Utils
   For this we use the nltk module. NLTK (Natural Language Toolkit) is a leading platform for building Python programs to work with human language data. It provides a       lot of helpful methods that we can use.
  <ul><li>file:nltk_utils1.ipynb</li></ul> 
  
  # Implement The Neural Network
   <ul><li>file:modele.ipynb</li></ul> 
   <img src=model_pic.png>
    
   # Implement The Training Pipeline
   <ul><li>file:train.ipynb</li></ul> 
   
   # Implement The Chat
   Load the trained model and make predictions for new sentences
   <ul><li>file:chat.ipynb</li></ul> 
   
   # Watch the Presentation video
   <a href="https://www.youtube.com/watch?v=Gl96mdOO9Zs">https://www.youtube.com/watch?v=Gl96mdOO9Zs</a>
   
