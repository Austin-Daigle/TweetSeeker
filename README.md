# TweetSeeker 1.4

TweetSeeker is a Python-based Twitter Scrapper that 

## How to Use:
Navigate through the repository and download the newest verion of TweetSeeker 
(in this case it is TweetSeeker 1.4v) as a Python file. Either run the Python file
via command line or run it in a IDE.
Once the latested version of TweetSeeker has been executed, a program launch options
GUI will appear asking the user to choose from either starting the program directly using
Twitter API Developers Keys or to use AWS IAM Login details:* 

![image](https://user-images.githubusercontent.com/100094056/235781317-0966e6ab-74a6-44a4-90ce-57c20006b84a.png)

Once the details have been selected by the user popups verifying AWS/Twitter API Key details will
popup depending on the options choosen by the user (note the AWS Popup will not appear if the Twitter API key
option was selected insteead of AWS):

AWS Verification Pupup GUI:

![image](https://user-images.githubusercontent.com/100094056/235783133-84360a32-fdce-4c12-a6ae-228da03c649d.png)


Twitter API Key Verification Pupup GUI:

![image](https://user-images.githubusercontent.com/100094056/235784092-61c8073d-0a5d-404f-b327-b795a31f8e76.png)


* This will require an AWS Instance with the properly configured Secret Manager service,
Key manager, and IAM users to be properly setup and running with the Twitter API backend.
(Please see instructions on this process below). 




## How to make AWS Secrets Manager:
