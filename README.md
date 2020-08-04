[//]: # (Image References)

[image1]: ./image/Annotation%202020-08-04%20200209.png "Review 6"
[image2]: ./image/Annotation%202020-08-04%20200235.png "Review 1"
[image3]: ./image/Annotation%202020-08-04%20200238.png "Review 2"
[image4]: ./image/Annotation%202020-08-04%20200241.png "Review 3"
[image5]: ./image/Annotation%202020-08-04%20200244.png "Review 4"
[image6]: ./image/Annotation%202020-08-04%20200246.png "Review 5"

# SageMaker Deployment Project

The notebook and Python files provided here, once completed, result in a simple web app which interacts with a deployed recurrent neural network performing sentiment analysis on movie reviews. This project assumes some familiarity with SageMaker and Sentiment Analysis using XGBoost, should provide enough background.

Please see the [README](https://github.com/udacity/sagemaker-deployment/tree/master/README.md) in the root directory for instructions on setting up a SageMaker notebook and downloading the project files (as well as the other notebooks).

## Installation
The deployment project which we will be working on is intended to be done using Amazon's SageMaker platform. In particular, it is assumed that you have a working notebook instance in which you can clone the deployment repository.
1. First, start by logging in to the AWS console, opening the SageMaker dashboard and clicking on Create notebook instance. You may choose any name you would like for your notebook. A ml.t2.medium is used to launch the notebook and is available by default. Inside the notebook ml.p2.xlarge is used for training a model and ml.m4.xlarge is used for deployment. These instance may not be available to all users by default. If you haven't requested ml.p2.xlarge so far please follow the instructions on the next page to request it now.
2. Next, under IAM role select Create a new role. You should get a pop-up window that looks like the one below. The only change that needs to be made is to select None under S3 buckets you specify. 
3. Next, scroll down to the section labelled Git repositories. Here you will clone the `https://github.com/satriowputra/SageMaker-LSTM-RNN-Deployment.git` repository.
4. You're done! Click on Create notebook instance. Your notebook instance is now set up and ready to be used! You can access your notebook using the Action "Open Jupyter".

__NOTE:__ Make sure you have increased ml.p2.xlarge instance limit prior using the notebook.

## File Description
There are some files I uploaded in this repository:
1. /image: contains image resulted from the notebook
2. /serve: script to do prediction using deployed model
3. /train: contains script to train LSTM model inside SageMaker Instances
4. /website: created webapp

## Result
- Review 1
![Review 1][image2]<br>
- Review 2
![Review 2][image3]<br>
- Review 3
![Review 3][image4]<br>
- Review 4
![Review 4][image5]<br>
- Review 5
![Review 5][image6]<br>
- Review 6
![Review 6][image1]<br>
Examples above show us that the model prediction is almost perfect. If the review has positive word like 'good' or 'best' it returns the positive prediction. That is also true when the review has negative word inside such as 'bad' and 'boring'. But the model has failed to return the correct prediction if the review has sentences that is little bit unclear such in review 3. We human will say that review 3 is negative but the model returned positive.
