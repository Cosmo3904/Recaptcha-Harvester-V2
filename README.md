# Recaptcha-Harvester-V2
# Solve Recaptcha Tokens for use in automated projects.

## SETUP
1. To install all the dependencies for the script simply download or pull the project
2. Open a terminal or shell window in the project's directory
3. Run the following command
```
pip3 install -r requirements.txt
```
4. Copy ChromeDriver to your machine's path (Download Link : https://sites.google.com/a/chromium.org/chromedriver/downloads)

###### Video Guide (Click for Full Video)
[![Requirements.txt Video](https://j.gifs.com/L8DO5A.gif)](https://www.youtube.com/watch?v=jolzFNb5iNQ)

## Server.py
Server.py is a Flask Script that will run on port 5000 by default. Server.py is the only file in the project that requires the templates folder. This Script will recieve input from the harvester and store tokens for later use. Each token is only valid for 110 seconds and will be removed from the tokens list after expiring. The Tokens can be viewed in a web browser by visiting http://YOURIPHERE:5000/json

###### Video Guide (Click for Full Video)
[![Server.py Video](https://j.gifs.com/BLpA1N.gif)](https://www.youtube.com/watch?v=1WxJDCtxMRs)

## Harvester.py
Harvester.py is a Selenium Script that can be automated for any project you use or it can be ran as a basic script (will ask for all the required input). The required inputs are the following fields: Sitekey, Domain, and Server IP. The optional inputs are Gmail Address and Gmail Password (This will just automate signing into google for ReCaptcha one-clicks). Sitekey is the ReCaptcha Sitekey you would like to harvest for, domain is the website that you are harvesting for, and serverip is the IP Address of the server that is running server.py. Server.py is required to store the tokens from the harvester, however it can be ran on the local machine if you point the harvester to localhost.

###### Basic Script Video Guide (Click for Full Video)
[![Harvester.py Video](https://j.gifs.com/4RwjWn.gif)](https://www.youtube.com/watch?v=g07LPTI4Yhg)

###### Automation Setup
```python
from Harvester import harvest
s = harvest('6Ld2sf4SAAAAAKSgzs0Q13IZhY02Pyo31S2jgOB5','http://patrickhlauke.github.io','127.0.0.1','me@gmail.com','gmailpasswordhere')
s.signin()
#When ready to solve do the below command
s.solve()
```

###### Basic Script Setup
```
Enter Sitekey : 6Ld2sf4SAAAAAKSgzs0Q13IZhY02Pyo31S2jgOB5
Solve For What Domain : http://patrickhlauke.github.io
What is the IP of the token server? : 127.0.0.1
Enter Gmail : me@gmail.com
Enter Gmail Password  : PASSWORDWILLENTERBLANKLY
```

## Fetch.py
Fetch.py is a Requests Script that will scrape your Token Server (Server.py) for an unused token, post it as a used token to the Token Server (Server.py) and return the token for use. Fetch.py is super easy to use and setup. Just simply run the 'main' function inside the script with the ip address of the Token Server (Server.py) as a parameter.
```python
from Fetch import main as getToken
serverIP = '127.0.0.1'
token = getToken(serverIP)
print('Token : ' + token)
```

###### Video Guide (Click for Full Video)
[![Fetch.py Video](https://j.gifs.com/mQ6m7r.gif)](https://www.youtube.com/watch?v=LdCfaG1esG0)

## iOS-Harvester
iOS-Harvester is and iOS app that will allow you to solve recaptchas and will post them to your Token Server (Server.py) for later use. The app has 3 text fields that can be changed at any time, the top field is for the ReCaptcha Sitekey, middle field is for the domain that the ReCaptcha is to be solved upon, and the bottom field is for the IP Address of the Token Server (Server.py). You may also sign into your google account by pressing the Google button. 

###### Setup
1. Open the project in XCode by opening the .xcodeproj file.
2. Plug in your iOS device
3. Product > Destination > Select your iOS Device
4. Product > Run
5. App should open on iOS Device.

###### Video Guide (Click for Full Video)
[![iOS-ReCaptcha Video](https://j.gifs.com/kZV7Pv.gif)](https://youtu.be/vDwiAzPJaQo)

# Leave me a follow on Twitter @Cosm00_!

