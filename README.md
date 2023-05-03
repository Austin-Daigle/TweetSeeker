# TweetSeeker version 1.4
TweetSeeker is a Python-based Twitter Scrapper that automatically goes with a given Twitter account name/handle and 
extracts account data into a file named ___@*insert-name-here*_account_data.csv___ with the account attributes (see "Account Data Format" below).
Also, a second file named ___@*insert-name-here*_tweet_data.csv___ which contains all of the data from all of the tweets in
the format of one tweet per line using the fields in order of below (see "Tweet Data format" below)


**Account Data Format:**
```
["accountID","accountName","screenName","description",
"descriptionEntities","isVerified","followersCount","friendsCount",
"listedCount","ratio","createdAt","timeZone","geoEnabled","location",
"profileURL","profileImageURL","hasProtectedTweets"]
```   
**Tweet Data format:**
```
["tweetID","createdAt","tweetText","language","tweetURL",
"favoriteCount","retweetCount","mentionedUsers","tweetEntities",
"tweetPhotoURLs","tweetVideoURLs","tweetURLs","geoData","coordinates"]
```
## Dependencies:

These are the packages that are required by the latest version of TweetSeeker:


    'tkinter'
    'tkinter.messagebox'
    'subprocess'
    'requests'
    'tweepy'
    'csv'
    'datetime'
    'os'
    'json'
    'boto3'
    're'
    'Counter'
    'pyqt5'

## How to Use:
Download and run [TweetSeeker_Dependencies_installer_v.1.2.py](https://github.com/Austin-Daigle/TweetSeeker/blob/main/TweetSeeker_Dependencies_installer_v1.2.py) or manually install each of the dependency packages required (see above).

Then, Navigate through the repository and download [TweetSeeker_v.1.4](https://github.com/Austin-Daigle/TweetSeeker/blob/main/TweetSeeker_v1.4.py) and either run the Python file via the command line or run it in an IDE.

Once the latest version of TweetSeeker has been executed, program launch options GUI will appear, asking the user to choose from either starting the program directly using Twitter API Developers Keys or to use AWS IAM Login details.* 

**Program Launch Options GUI:**

<img src="https://user-images.githubusercontent.com/100094056/235785066-5f0fb226-c1d0-437d-963e-90d8b4c87861.png" alt="image" width="300"/>


Once the details have been selected by the user, popups verifying AWS/Twitter API Key details will
popup depending on the options chosen by the user (note the AWS Popup will not appear if the Twitter API key
the option was selected instead of AWS):

* AWS Verification Pupup GUI:

<img src="https://user-images.githubusercontent.com/100094056/235783133-84360a32-fdce-4c12-a6ae-228da03c649d.png" alt="image" width="300"/>

* Twitter API Key Verification Pupup GUI:

<img src="https://user-images.githubusercontent.com/100094056/235784092-61c8073d-0a5d-404f-b327-b795a31f8e76.png" alt="image" width="300"/>

Once the TweetSeeker verifies all of the Twitter API details, a text input box appears
for the user to enter the desired Twitter account name to auto-scrap. 

* Twitter Username Popup Prompt GUI:
<img src="https://user-images.githubusercontent.com/100094056/235819364-96c99884-2d57-4a14-8fc1-bd112591e430.png" alt="image" width="190"/>


Next, the Tweet data and account data that was scrapped are saved as .csv files and the program displays a GUI with basic Twitter account analytics.

* Twitter Account Analytics GUI:

![image](https://user-images.githubusercontent.com/100094056/235820591-2671c6dd-3df6-4b0d-9e73-7825baa60e52.png)



\* This will require an AWS Instance with the adequately configured Secret Manager service,
Key manager and IAM users to be correctly setup and running with the Twitter API backend.
(Please see instructions on this process below). 

## Version History
* TwitterSeeker_core_v.1.0.py - This is the basic core the Twitter Scrapper, it does not have a GUI or AWS support, it functions purly through code
modifications to scrap the given account. This program required the Twitter API keys to be hard coded into its variables to correctly start (Also, Do not ever submit or share code with hardcoded secrets in it as this is a major breach of security). 
* TweetSeeker_v1.0_alpha.py - Basic stable developer's build of TweetSeeker with a basic verifcation GUI and nothing else, the actual scrapping functions need to be hard coded in and this was originally an environment for my team to develop on. 


## How to make AWS Secrets Manager:
