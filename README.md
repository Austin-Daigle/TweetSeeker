# TweetSeeker version 1.4:

**End-of-life Notice:**

Unfortunately, support for TweetSeeker has been discontinued. This decision stems from recent policy modifications within Elon Musk's Twitter Developer API. Twitter has implemented artificial limitations on per-person-per-session content access, and the backend infrastructure has undergone considerable restrictions, rendering it inaccessible to both general developers and hobbyist users.

**Introduction:**


TweetSeeker is a Python-based Twitter Scrapper that automatically goes with a given Twitter account name/handle and 
extracts account data into a file named ___@*insert-name-here*_account_data.csv___ with the account attributes (see "Account Data Format" below).
Also, a second file named ___@*insert-name-here*_tweet_data.csv___ which contains all of the data from all of the tweets in
the format of one tweet per line using the fields in order below (see "Tweet Data format" below)

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

Then, Either Download the [TweetSeeker v1.4 Executable (.exe)](https://drive.google.com/file/d/1nbhE-bUZDXTm9kanUSp3DMTMp89otyTb/view?usp=sharing) and run it or Navigate through the repository and download [TweetSeeker_v.1.4](https://github.com/Austin-Daigle/TweetSeeker/blob/main/TweetSeeker_v1.4.py) and either run the Python file via the command line or run it in an IDE.

Once the latest version of TweetSeeker has been executed, program launch options GUI will appear, asking the user to choose from either starting the program directly using Twitter API Developers Keys or using AWS IAM Login details.* 

**Program Launch Options GUI:**

<img src="https://user-images.githubusercontent.com/100094056/235785066-5f0fb226-c1d0-437d-963e-90d8b4c87861.png" alt="image" width="300"/>


Once the user has selected the details, popups verifying AWS/Twitter API Key details will
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

<img src="https://user-images.githubusercontent.com/100094056/235820591-2671c6dd-3df6-4b0d-9e73-7825baa60e52.png" alt="image" width="500"/>


\* This will require an AWS Instance with the adequately configured Secret Manager service,
Key manager and IAM users to be correctly setup and running with the Twitter API backend.
(Please see instructions on this process below). 

## Version History
* TwitterSeeker_core_v.1.0.py - This is the basic core of the Twitter Scrapper. It does not have a GUI or AWS support, it functions purely through code
modifications to scrap the given account. This program required the Twitter API keys to be hard-coded into its variables to correctly start (Also, Do not ever submit or share code with hard-coded secrets in it as this is a major breach of security). 
* TweetSeeker_v1.0_alpha.py - Basic stable developer's build of TweetSeeker with a basic verification GUI and nothing else. The actual scrapping functions need to be hard coded in, and this was originally an environment for my team to develop in. 
* TweetSeeker_v1.1_alpha.py - Improvements to GUI, authentication for AWS to Twitter API integration.
* TweetSeeker_v1.2_alpha.py - Improved Authentication Error handling and Twitter API error catching, plus team contributions
* TweetSeeker_v1.3_alpha.py - Team contributions for analytical functions plus a user Twitter name inputs and analytics GUI.
* TweetSeeker_v.1.4.py - This is the final stable release with all issues in the prior versions fixed.

## How to make AWS Secrets Manager:
Keep in mind that there may be slight variations in this process depending on how Amazon Web Services updates/maintains its services, also the source code of the original project may need to be modified to support a different AWS backend. These instructions were
Created using the default documentation provided by AWS and should be reviewed as well since backend implementations can be deprecated/changed for your instantiation of TweetSeeker.

Setting up AWS Cost Manager and Key Manager may be in your interest to set up as it allows for easier administration of the overall project.

__Instructions for creating the AWS Secrets Manager__

1.  Log in to your AWS Management Console and navigate to the AWS Secrets Manager service.
    
2.  Click on the "**Store a new secret**" button.
    
3.  Select "**Other type of secrets**" and then choose "**Credentials for RDS database, Redshift, DocumentDB, or Secrets Manager**" from the drop-down menu.
    
4.  Enter the Twitter Dev API keys as the secret values. You can enter the API key in the "**username**" field and the API secret key in the "**password**" field.
    
5.  In the "**Secret name**" field, enter "**TweetSeeker**".
    
6.  Optionally, you can enter a description for the secret in the "**Description**" field.
    
7.  Click on "**Next**" to proceed to the "**Configure secret**" page.
    
8.  Choose the "**Encryption key**" option to encrypt your secret values.
    
9.  Choose "**Default encryption key**" or "**Custom encryption key**" based on your preference.
    
10.  Optionally, you can choose to rotate the secret automatically or manually.
    
11.  Click on "**Next**" to proceed to the "**Review**" page.
    
12.  Review the information you have entered for accuracy and click on "**Store secret**" to create the secret.

__Here are the steps for setting up IAM roles for admin and developer roles:__

1.  Log in to your AWS Management Console and navigate to the IAM service.
    
2.  Click on "**Roles**" in the left navigation menu and then click on the "**Create role**" button.
    
3.  Select "**AWS service**" as the trusted entity and then choose "**EC2**" from the list of services.
    
4.  Click on "**Next: Permissions**" to proceed to the "**Attach permissions policies**" page.
    
5.  For the admin role, select the "**AdministratorAccess**" policy. This policy provides full access to all AWS services and resources.
    
6.  For the developer role, select the "**SecretsManagerReadWrite**" policy. This policy allows read-only access to AWS Secrets Manager.
    
7.  Click on "**Next: Tags**" to proceed to the "**Add tags**" page. You can add tags to your roles for better organization and management of your resources.
    
8.  Click on "**Next: Review**" to proceed to the "**Review**" page.
    
9.  Review the information you have entered for accuracy and click on "**Create role**" to create the role.
    
10.  After creating the roles, you can now assign them to users or EC2 instances that need access to the resources.


