# CourseProject

Text Classification Competition: Twitter Sarcasm Detection
Model Used: LSTM

All the details about the project has been documented in the "CS410 Project Documentation.PDF" file out here. https://github.com/mkhanal2/CourseProject/blob/main/CS410%20Project%20Documentation.pdf

# Documents
- Project Proposal : https://github.com/mkhanal2/CourseProject/blob/main/CS410%20Project%20Proposal.pdf
- Project Progress Report : https://github.com/mkhanal2/CourseProject/blob/main/CS410%20Project%20-%20Progress%20Report.pdf
- Project Final Document: https://github.com/mkhanal2/CourseProject/blob/main/CS410%20Project%20Documentation.pdf

# Source Code
- Python Juputer Notebook Code:
- https://github.com/mkhanal2/CourseProject/blob/main/source_code/Project%20Source%20Code.ipynb
# Video Presentation
- Link --> https://mediaspace.illinois.edu/media/1_3i2g9ehq
# How to use/run the code
The code is developed using python 3 (Jupiter notebook). There is folder called source_code on the GitHub (https://github.com/mkhanal2/CourseProject) where we put all the documentation and source-code for the project. Follow following instruction to run the code:
- Download the folder “source_code” from GitHub (link above)
- Makes sure you have folder called “data” under source_code folder which has (train.jsonl, test.jsonl) files , all of these files and folder are already in GitHub.
- We would need one for file in this data folder. Go to the link below to download the “GloVe” twitter file we need “glove.twitter.27B.25d.txt”. After downloading the file for the link, unizip the file and copy the file “glove.twitter.27B.25d.txt” onto the data folder.
	- Direct Link - http://nlp.stanford.edu/data/glove.twitter.27B.zip
	- OR: Go to below link and download below mentioned file.
		- https://nlp.stanford.edu/projects/glove/
		- Download “glove.twitter.27B.zip” form this site.
	- Note: Chrome didn’t work for me while downloading, so I used “Microsoft Edge” to download the above file. 
- Now open Jupiter Notebook on you laptop (usually within Anaconda).
- Using Jupiter Notebook open the source code from the downloaded folder (source code file name: Project Source Code.ipynb)
After that you can run the code. Please make sure that all the packages used in the 2nd cell of the notebook are already installed. I have provided the instruction on 1st cell of the notebook on how to install the packages.

# Text Classification Competition: Twitter Sarcasm Detection 

Dataset format:

Each line contains a JSON object with the following fields : 
- ***response*** :  the Tweet to be classified
- ***context*** : the conversation context of the ***response***
	- Note, the context is an ordered list of dialogue, i.e., if the context contains three elements, `c1`, `c2`, `c3`, in that order, then `c2` is a reply to `c1` and `c3` is a reply to `c2`. Further, the Tweet to be classified is a reply to `c3`.
- ***label*** : `SARCASM` or `NOT_SARCASM` 

- ***id***:  String identifier for sample. This id will be required when making submissions. (ONLY in test data)

For instance, for the following training example : 

`"label": "SARCASM", "response": "@USER @USER @USER I don't get this .. obviously you do care or you would've moved right along .. instead you decided to care and troll her ..", "context": ["A minor child deserves privacy and should be kept out of politics . Pamela Karlan , you should be ashamed of your very angry and obviously biased public pandering , and using a child to do it .", "@USER If your child isn't named Barron ... #BeBest Melania couldn't care less . Fact . 💯"]`

The response tweet, "@USER @USER @USER I don't get this..." is a reply to its immediate context "@USER If your child isn't..." which is a reply to "A minor child deserves privacy...". Your goal is to predict the label of the "response" while optionally using the context (i.e, the immediate or the full context).

***Dataset size statistics*** :

| Train | Test |
|-------|------|
| 5000  | 1800 |

For Test, we've provided you the ***response*** and the ***context***. We also provide the ***id*** (i.e., identifier) to report the results.

***Submission Instructions*** : Follow the same instructions as for the MPs -- create a private copy of this repo and add a webhook to connect to LiveDataLab.Please add a comma separated file named `answer.txt` containing the predictions on the test dataset. The file should have no headers and have exactly 1800 rows. Each row must have the sample id and the predicted label. For example:

twitter_1,SARCASM  
twitter_2,NOT_SARCASM  
...
