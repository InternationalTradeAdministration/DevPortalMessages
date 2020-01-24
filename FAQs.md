# Frequently Asked Questions
* [General Questions](#general-questions)
* [API Keys, Access Tokens and Bearer Codes](#api-keys-access-tokens-and-bearer-codes)
* [Throttling](#throttling)
* [Consolidated Screening List (CSL)](#consolidated-screening-list-csl)
* [Errors](#errors)

## General Questions
* _Do you know when the transition from the old service to the new service will take place? How long do we have until we can no longer use the current service?_
  * The legacy platform will be shut down on January 30, 2020. The [notice](https://internationaltradeadministration.github.io/DevPortalMessages/DevPortalUpgrade.html) describing the transition can be viewed on our legacy platform.

* _During this change, were any changes made to the APIs themselves?_
  * The contents and format of the APIs have not been altered. The method for accessing the APIs has changed.

* _Where can I find the documentation for each of the APIs?_
  * In the API Console tab, after clicking on the `GET /search` button, you will find information on the parameters and the model for responses for that API.  The Overview tab has a brief summary about the substance and source of the data. 

* _How can I subscribe to emails from Data Services for updates to the platform or APIs?_
  * You can subscribe by clicking this link: [https://public.govdelivery.com/accounts/USITATRADE/subscriber/new?topic_id=USITATRADE_1704](https://public.govdelivery.com/accounts/USITATRADE/subscriber/new?topic_id=USITATRADE_1704)

## API Keys, Access Tokens and Bearer Codes
* _With the new system, can I just switch out the `api_key` parameter with `bearer_code`?_
  * No, the new platform requires every HTTP client to send search requests with an access token in the HTTP request header. This is the only supported authentication scheme. It does not support authentication using the URL query string.

    If you need to see the results in a web browser, you can use the existing console in our API platform or you will need to use a browser extension, such as the [Advanced REST Client](https://chrome.google.com/webstore/detail/advanced-rest-client/hgmloofddffdnphfgcellkdfbfbjeloo/related?hl=en-US). This is not a recommendation for this product, but rather an example of a browser extension that could be used for this function.

    For additional help with making HTTP requests using your access token, see [How to interact with the APIs using the new authentication type](https://internationaltradeadministration.github.io/DevPortalMessages/IntroToNewAuthType)  

* _How can I obtain an access token for production and another one for prototype?_
  * Currently, only one access token - the most recently generated, non-expired access token - is valid per application.  And at this time, each username can generate one application.

* _What is the difference between API Key and Access Token? Which do I use and how?_
  * The new API store uses the Bearer authentication scheme (also called token authentication), so instead of API keys, you have an Access Token.  Your application will use the Access Token to fetch data from the API. 
  For more information about the Access Token, see the instructions for [Invoking an API](https://internationaltradeadministration.github.io/DevPortalMessages/GettingStarted_NewAPIStore#invoking-an-api).

* _I see in your documentation that the creation of a new key will inactivate any old(er) keys. So, if I create a new key in the new system, will that inactivate my older key from your older system?_
  * The current system and the new system are completed separate. Any work you do in the new system will not alter anything in the current system. The key you are currently using will continue to work. You will also need to create a new login to access our new system. In the new system we use “access tokens.” If you generate a new access token, your previously generated access token will no longer work. Again, this will not deactivate the API key that you are using from the current system.

## Throttling
* _What is the error code returned when my access token is throttled?_
  * The API returns with HTTP status `429` on requests that have reached the throttle limit. Here is an example of the JSON body in the response:
    ```js
    {
      "fault": {
        "code": 900804,
        "message": "Message throttled out",
        "description": "You have exceeded your quota",
        "nextAccessTime": "2020-Jan-08 16:59:00+0000 UTC"
      }
    }
    ```

* _When setting up a new API access token, I noticed it states that 100 requests are allowed per minute per access token. Is that all the information about throttling available?_ 
  * Yes.  If you have more specific questions, please email [DataServices@trade.gov](mailto:DataServices@trade.gov?subject=API%20Request%20Throttling%20Question)

* _I have seen the information about the throttling. Are there any other restrictions that I should be aware of?_
  * See the [Terms of Service](https://api.trade.gov/apps/store/ita/terms-of-service) for more information.

* _How can we get the ability to run more than 100 requests per minute and what would the prices be?_
  * We are looking into offering higher limits of throughput. We will send out an [email](https://public.govdelivery.com/accounts/USITATRADE/subscriber/new?topic_id=USITATRADE_1704) with additional information once we have additional information.

## Consolidated Screening List (CSL)
* _With the new API store, is it possible to download the entire CSL list?_
  * Yes. For customers wishing to batch process their queries with multiple threads over a shorter period of time, we recommend downloading the full CSL as either a [CSV](http://api.trade.gov/static/consolidated_screening_list/consolidated.csv) or a [TSV](http://api.trade.gov/static/consolidated_screening_list/consolidated.tsv) and running the queries locally.

* _I have an API Key for downloading the CSV file. Do I need to get a new API key to continue downloading the CSV file?_
  * An API key is no longer needed for downloading the [CSV](http://api.trade.gov/static/consolidated_screening_list/consolidated.csv) or [TSV](http://api.trade.gov/static/consolidated_screening_list/consolidated.tsv) file.

## Errors
* _When subscribing to an API I receive the error "Application is not accessible to the user."_
  * This occurs when you have already subscribed to the API and are trying to subscribe again. To verify that you have already subscribed:
    * Go to your Applications page: https://api.trade.gov/apps/store/site/pages/applications.jag
    * Click on "DefaultApplication"
    * Click on the "Subscriptions" tab and you should see your current API subscriptions.
