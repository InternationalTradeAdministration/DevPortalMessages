# Getting Started with the New API Store
* [Subscribing to an API](#subscribing-to-an-api)
* [Invoking an API](#invoking-an-api)
* [Frequently Asked Questions](#frequently-asked-questions)

## Subscribing to an API
1. Using the Login link at the top right corner, log in to the [API store](https://api.trade.gov/apps/store/apis/list). If you have not done this before, you will first need to create an account.
2. All our APIs are available. Click on an API to view its details.
3. The selected API’s information will be visible. As a subscribed user, you can now add ratings and provide comments to the API, which will be moderated.
4. An application is a logical collection of one or more APIs and is required when subscribing to an API. Select an application from the Applications drop-down list. You can use the default application or create a new one right from the drop-down list. You can view, create, rename, and delete applications from the “My Applications” tab.  
<img src="getting-started-screenshots/Applications_mgmt.png" alt="Managing an application" width="600"/>

5. Select a service tier (currently we only have one tier) then click on the Subscribe button. If the subscription is successful, a message appears congratulating you on your successful subscription.  
<img src="getting-started-screenshots/Subscribing.png" alt="Subscribing to an API" width="600"/>

## Invoking an API
The new APIs use Bearer Authentication, so your request must include this in the Authorization header `Authorization: Bearer <access_token>`.
1. You can view or regenerate your Access Token in your Application's Access Token tab: 

  <img src="getting-started-screenshots/Application_AccessTokenTab.png" alt="Application Access Token Tab" width="600"/>  
  
  **If you regenerate the Access Token, the old Access Token expires. Only the most recent token is valid for each Application.**

2. Next, in the API Console Tab of an API to which you have subscribed, confirm that your Access Token is present in the `Authorization : Bearer` field, and click the blue "GET" button.  In the drop down console that appears, click "Try it out".  Here, you can enter in various query parameters, and click the "Execute" button under the query parameters to execute the request.  
  <img src="getting-started-screenshots/API_Console1.png" alt="API_Console1" width="500"/>
  <img src="getting-started-screenshots/API_Console2_TryItButton.png" alt="API_Console2_TryItButton" width="600"/>
  <img src="getting-started-screenshots/API_Console3_Execute.png" alt="API_Console3_Execute" width="600"/>

3. Notice also that the request URL is updated from what you might have been using previously.  A customized cURL command is also available here so you can try it in your terminal, and shows the specific command that was executed.  
<img src="getting-started-screenshots/RequestCurl.png" alt="RequestCurl" width="600"/>


## Frequently Asked Questions
### General Questions
* _Where can I find the documentation for each of the APIs?_
  * In the API Console tab, after clicking on the `GET /search` button, you will find information on the parameters and the model for responses for that API.  The Overview tab has a brief summary about the substance and source of the data. 

### API Keys
* _How can I obtain an access token for production and another one for prototype?_
  * Currently, only one access token - the most recently generated, non-expired access token - is valid per application.  And at this time, each username can generate one application.

* _What is the difference between API Key and Access Token? Which do I use and how?_
  * The new API store uses the Bearer authentication scheme (also called token authentication), so instead of API keys, you have an Access Token.  Your application will use the Access Token to fetch data from the API. 
  For more information about the Access Token, see the instructions for [Invoking an API](#invoking-an-api).

* _I see in your documentation that the creation of a new key will inactivate any old(er) keys. So, if I create a new key in the new system, will that inactivate my older key from your older system?_
  * The current system and the new system are completed separate. Any work you do in the new system will not alter anything in the current system. The key you are currently using will continue to work. You will also need to create a new login to access our new system. In the new system we use “access tokens.” If you generate a new access token, your previously generated access token will no longer work. Again, this will not deactivate the API key that you are using from the current system.

### Throttling
* _When setting up a new API access token, I noticed it states that 100 requests are allowed per minute per access token. Is that all the information about throttling available?_ 
  * Yes.  If you have more specific questions, please email [DataServices@trade.gov](mailto:DataServices@trade.gov?subject=API%20Request%20Throttling%20Question)

* _I have seen the information about the throttling. Are there any other restrictions that I should be aware of?_
  * See the [Terms of Service](https://api.trade.gov/apps/store/ita/terms-of-service) for more information.

* _How can we get the ability to run more than 100 requests per minute and what would the prices be?_
  * We are looking into offering higher limits of throughput. We will send out an email with additional information once we have additional information.

### Consolidated Screening List (CSL)
* _With the new API store, is it possible to download the entire CSL list?_
  * While the full CSL is not downloadable from the API, you can download it from export.gov as either a [CSV](https://api.trade.gov/consolidated_screening_list/search.csv?api_key=OHZYuksFHSFao8jDXTkfiypO) or a [TSV](https://api.trade.gov/consolidated_screening_list/search.tsv?api_key=OHZYuksFHSFao8jDXTkfiypO) file.

* _Are we still able to download the CSV and TSV files for the Consolidated Screening List?_
  * Yes, see above.

* _I have an API Key for downloading the CSV file. Do I need to get a new API key to continue downloading the CSV file?_
  * An API key is no longer needed for downloading the CSV file: [https://www.export.gov/article?id=Consolidated-Screening-List](https://www.export.gov/article?id=Consolidated-Screening-List)