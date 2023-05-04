# Job-Title-Normalization
ACS56000 Software Engineering. Team 4 (AI project, skill recommendations/feedback from resume 1.0)

**Project Objective :** To provide students with the opportunity to gain hands-on experience in creating AI/ML applications that can be used for education and research studies. 


**Abstract :** In today's world human resources are changing everyday. There is always a new challenge and new requirement that needs to be addressed and a new technology that needs to be acquired. This brings a new position to the hiring market that needs to be filled. Since, there are no standards on how a job title should be portrayed both by the employer in job description and by the employee in their resume paraphrasing the same title in a fancy/formal/in way they think is apt. This brings the noise and variations in the Job titles that are present in the hiring market. For example, Software Developer in Company X is equivalent to Software Engineer in company Y, Software Developer 2/II in company A is equivalent to Senior Software Developer in company B where both of them would probably be equivalent to senior software engineer. 
 

Aim of the project is to use the resume data and job description, features like skills, work experience, work description etc., and normalize a job title. For example, given a resume data like skillsets, description the model should predict the apt job title, another example is given a job description the model should predict the apt job title. 

## Model creation:

- Used UpdatedResumeDataSet.csv for model training and evaluation.
- A simple neural network architecture for text classification task (here, classifying research articles into predifined tags)
- The model architecture consists of the following layers:
    - Embedding Layer: Converts the input text into dense vector representation
    - Bidirectional LSTM Layer: Capture sequential nature of text data and extract features from it. The model also learns the context from the text in both forward and backward directions as we are using a bidirectional LSTM.
    - Dense Layer: Enables the model to learn non-linear transformations of the input data
    - Output Dense Layer: Produces a probability distribution over the classes using softmax activation function.

- The above model is trained on the UpdatedResumeDataSet.csv and the resultant model is saved as model.h5

- To load the saved model use the code below:
    ```python 
    model = tf.keras.models.load_model("model.h5")
    ```

## Model re-training and usage

- The JobTitleNormalization.ipynb contains the code to train and evaluate the model on the UpdatedResumeDataSet.csv training data. 
- One can re-train the model on any other data by changing the path to training data and ensuring that the training data follows the same schema as the UpdatedResumeDataSet.csv
- To re-train the model you would need a Jupyter notebook or any online notebook such as Google Colab or Kaggle Notebook. 
- To install the Jupyter notebook using pip, use the following command.
    ```python 
    pip install jupyter notebook
    ```
- To launch the Jupyter notebook run the following command in the terminal
    ```python
    jupyter notebook
    ```
- Once launched, open the JobTitleNormalization.ipynb file in sequence with any changes as required. 

- There are several dependencies that need to be installed. One can install the dependent libraries by running the below command.
    ```python 
    pip install -r requirements.txt
    ```
- The above command installs all the libraries mentioned in the requirements.txt file