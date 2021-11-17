## Purpose
This app collects data about Google Analytics properties and then detects the Google Tag Manager container implemented in the pages corresponding to those properties.

## Description
The app consists of two parts.
The first part ga_accounts_check.txt will run in the Google App Script Environment within Google Sheets. This part of the app crawls all of the available 
Google Analytics Accounts, Views and Properties and determines the amount of pagevies within the last 12 months. It returns the list of all accounts, properties and views
together with the corresponding amount of pageviews.

The second part gtm_check.ipynb is a Python notebook that was run within Azure Cloud. The notebook takes as an input the list with properties generated in part 1
and sends requests to all of the property urls contained in the list. In the response bodies the script searches for Google Tag Manager IDs contained in the sourse code
and writes them into a list. This list is then attached to the list of properties. The final result is a list of all GA properties and corresponding GTM-accounts.
