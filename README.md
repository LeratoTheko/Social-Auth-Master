**Mastering Social Authentication with Django Allauth**
Welcome to my Django Allauth project, where I delve deep into integrating social authentication for Google, Facebook, and LinkedIn. This repository serves as a comprehensive guide and example for anyone looking to implement robust and scalable third-party authentication in their Django projects.

**Table of Contents**
About the Project
Tech Stack
Features
Getting Started
Installation
Configuration
Running the Project
Authentication Providers
Google Authentication
Facebook Authentication
LinkedIn Authentication
License
Contact

**About the Project**
This project demonstrates a thorough implementation of Django Allauth for social authentication. The aim is to master the configuration and setup of three major providers—Google, Facebook, and LinkedIn—while gaining expertise in Django Allauth and how to best leverage it within a modern Django application.

**Tech Stack**
Python 3.12
Django 4.0
Django Allauth for authentication
SQLite (for development and demo purposes)
Bootstrap 5 (for front-end styling)

**Features**
Full authentication and login/logout flow for Google, Facebook, and LinkedIn.
Django Allauth integrated to handle user authentication, account management, and email verification.
Clean and modular code to allow easy expansion to more providers.
Practical examples for extending functionality with custom templates and views.
Getting Started
Prerequisites
Ensure you have the following installed:

Python 3.12
Django (version 4.5)
Pipenv or Virtualenv for environment management
A Google, Facebook, and LinkedIn developer account with API credentials for each.
Installation
Clone the repo:
git clone https://github.com/LeratoTheko/Social-Auth-Master
cd mastering-social-auth
Set up a virtual environment:
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

**Install dependencies:**
pip install -r requirements.txt

**Apply migrations:**
python manage.py migrate

**Create a superuser for admin access:**
python manage.py createsuperuser

**Configuration**
Django Allauth settings: You need to add the allauth configuration to settings.py.

INSTALLED_APPS = [
    'django.contrib.sites',
    'allauth',
    'allauth.account',
    'allauth.socialaccount',
    'allauth.socialaccount.providers.google',
    'allauth.socialaccount.providers.facebook',
    'allauth.socialaccount.providers.linkedin_oauth2',
    ...
]

SITE_ID = 1

AUTHENTICATION_BACKENDS = (
    'django.contrib.auth.backends.ModelBackend',
    'allauth.account.auth_backends.AuthenticationBackend',
)

LOGIN_REDIRECT_URL = '/'
ACCOUNT_EMAIL_VERIFICATION = 'mandatory'
ACCOUNT_AUTHENTICATION_METHOD = 'email'
ACCOUNT_EMAIL_REQUIRED = True
API Keys for Social Providers: In your Django admin panel, navigate to Social Applications under Sites, and configure the credentials from Google, Facebook, and LinkedIn.

**URLs Configuration: Be sure to include Django Allauth’s URLs in your main urls.py file:**

from django.urls import path, include

urlpatterns = [
    path('accounts/', include('allauth.urls')),
]

**Running the Project**
Once you’ve configured everything, you can start the development server:
python manage.py runserver
Then, visit http://localhost:8000/accounts/login/ to view the social login options.

**Authentication Providers**

**Google Authentication**
To enable Google Authentication, follow these steps:

**Create a project in Google Developer Console.**
Enable the Google+ API and obtain OAuth credentials.
Set up the Redirect URI as http://localhost:8000/accounts/google/login/callback/.
Facebook Authentication
For Facebook, you need to:

**Create an app in the Facebook Developers Portal.**
Get the App ID and App Secret.
Set up the Redirect URI as http://localhost:8000/accounts/facebook/login/callback/.
LinkedIn Authentication
LinkedIn setup requires:

**Creating an app on LinkedIn Developer.**
Retrieving the Client ID and Client Secret.
Configure the Redirect URI as http://localhost:8000/accounts/linkedin/login/callback/.

**License**
This is free of use

**Contact**
Feel free to reach out with any questions or suggestions.

Email: thekothekolerato@gmail.com
GitHub: LeratoTheko

