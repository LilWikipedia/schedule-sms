# schedule-sms
Schedule your daily appointments and notify via sms

Dependencies:

  Python 3.6 or higher

Install the following Python packages using pip:

  pip install google-auth google-auth-oauthlib google-auth-httplib2 google-api-python-client
  
  pip install pytz
  
  pip install requests
  
  pip install python-dotenv

These packages are required for the Google Calendar API and the Textlocal API.


Setting up accounts:

Google Calendar API:

To use the Google Calendar API, you'll need to set up a Google Cloud Platform (GCP) project and enable the API. Here are the steps to do that:
a. Go to the Google Cloud Console (https://console.cloud.google.com/) and create a new project.
b. Once the project is created, go to the APIs & Services dashboard and enable the Google Calendar API.
c. Create credentials for the API by going to the Credentials page and selecting "Create credentials" -> "Service account key".
d. Choose a name for the service account and give it the "Project" -> "Editor" role. Then click "Create" to generate the credentials file.
e. Download the credentials file and store it in a safe location. You'll need to reference this file in your code to authenticate with the API.


Textlocal API:

To use the Textlocal API, you'll need to sign up for a Textlocal account and obtain an API key. Here are the steps to do that:
a. Go to the Textlocal website (https://www.textlocal.com/) and sign up for a free account.
b. Once you've signed up, log in to your Textlocal account and go to the Developers section.
c. Create a new API key by clicking "Create a new API Key" and following the prompts.
d. Copy the API key and store it in a safe location. You'll need to reference this key in your code to authenticate with the API.

Note: The free Textlocal account has a daily limit of 10 messages, and messages will be branded with "Sent via Textlocal". If you need to send more messages or want to remove the branding, you'll need to upgrade to a paid plan.


Environment variables:

To keep sensitive information like API keys out of your code, you can store them as environment variables. Here are the steps to set up environment variables for the Google Calendar API and Textlocal API:
a. Create a new file in your project directory named ".env" and add the following lines:
makefile

  

  GOOGLE_APPLICATION_CREDENTIALS=<path_to_credentials_file>
  TEXTLOCAL_API_KEY=<textlocal_api_key>


Replace <path_to_credentials_file> with the file path of the credentials file you downloaded in step 1.e, and replace <textlocal_api_key> with the API key you obtained in step 2.d.
b. In your Python code, add the following line at the top of the file:
python

  from dotenv import load_dotenv


c. Add the following line before any code that references the environment variables:
scss

  load_dotenv()


This loads the environment variables from the .env file into your code.
