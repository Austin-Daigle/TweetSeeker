# TweetSeeker 1.4

TweetSeeker is a Python-based Twitter Scrapper that automatically goes with a given Twitter account name/handle and 
extracts account data into a file named ___@*insert-name-here*_account_data.csv___ with the account attributes (see "Account Data Format" below).
Also, a second file named ___@*insert-name-here*_tweet_data.csv___ which contains all of the data from all of the tweets in
the format of one tweet per line using the fields in order of below (see "Tweet Data format" below)


**Account Data Format:**

        ["accountID","accountName","screenName","description",
        "descriptionEntities","isVerified","followersCount","friendsCount",
        "listedCount","ratio","createdAt","timeZone","geoEnabled","location",
        "profileURL","profileImageURL","hasProtectedTweets"]
        
**Tweet Data format:**


        ["tweetID","createdAt","tweetText","language","tweetURL",
        "favoriteCount","retweetCount","mentionedUsers","tweetEntities",
        "tweetPhotoURLs","tweetVideoURLs","tweetURLs","geoData","coordinates"]

## How to Use:
Navigate through the repository and download the newest version of TweetSeeker 
(in this case, TweetSeeker 1.4v) as a Python file. Either run the Python file
via the command line or run it in an IDE.

Once the latest version of TweetSeeker has been executed, program launch options
GUI will appear, asking the user to choose from either starting the program directly using
Twitter API Developers Keys or to use AWS IAM Login details.* 

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

<img src="https://user-images.githubusercontent.com/100094056/235819364-96c99884-2d57-4a14-8fc1-bd112591e430.png" alt="image" width="190"/>








\* This will require an AWS Instance with the adequately configured Secret Manager service,
Key manager and IAM users to be correctly setup and running with the Twitter API backend.
(Please see instructions on this process below). 




## How to make AWS Secrets Manager:
