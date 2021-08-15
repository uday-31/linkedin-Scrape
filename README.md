# linkedin-scraper
Scrape data from LinkedIn profiles

This code does two things: 
- Capture all the data from a LinkedIn profile and save it in a CSV file
- Capture the profile suggestions for each profile, and scrape them as well

# Requirements
- [Firefox](https://www.mozilla.org/en-US/firefox/new/) browser
- [geckodriver](https://github.com/mozilla/geckodriver) web driver for Firefox
- Packages given in *requirements.txt*

# Usage Examples
For the first execution, call the function *initialRun*, and pass the URL and Name of the profile you want to scrape, as well as the email ID and password of a (dummy) LinkedIn account, and the number of profiles to be scraped.
```python
URL = 'https://www.linkedin.com/in/userid/'
Name = 'John Doe'
email = 'login@client.com'
passw = 'password'
req = 100
initialRun(URL,Name,email,passw,req)
```

For subsequent executions (in case of interruptions or security checks), call the function *subsequentRun* and pass the email, password, serial number of profile to start from, and the number of profiles to be scraped.
```python
email='login@client.com'
passw='password'
number=15 #if you got interrupted after 14 profiles
req=100
subsequentRun(email,passw,number,req)
```

# Output
- Profile data is stored in *linkedinProfileData.csv*
- A temporary log file with the list of profiles to be scraped is stored in *dump.data*

# Troubleshooting
If there is any problem in running the geckodriver WebDriver for Firefox, make sure that the path is correct in the *login* function.
```python
driver = webdriver.Firefox(options=options ,executable_path='enter path here')
```
