## Arc Publishing Platform Postman collection

This repo contains the Postman collection with pre-baked calls to the Arc Publishing Platform. For now, this includes all endpoints available as part of the Draft API.

### Getting Started:

This Postman Collection uses a pre-defined environment called `Testing Environment` which can be found in this repo. This environment contains Postman variables that make using the Collection easier, like setting a `lastDocumentId` variable so no copying and pasting of document_ids needs to occur. It's **very handy** and we strongly recommend using it!

To use the Collection and Environment, first import both to your local Postman Client.

Next, set the following variables in the Environment, which will be used across all your API calls:

1. token - a developer token from your Arc Developer Center (if you need help, see the docs in the Supporting Documentation section)
2. org - the org id associated with your organization in Arc (found in your Arc URL: https://ORG.arcpublishing.com)
3. defaultWebsite - the site you'd like your API calls to hit against
4. userId - your Arc user id (used to login to Okta)
5. websiteId1 - the id of a website to test circulating to and from
6. websiteId2 - the id of a website to test circulating to and from

The `websiteId1` and `websiteId2` parameters are used in the `/circulation` endpoints in order to, again, prevent copying and pasting of different website names across different API calls.

### Supporting Documentation:

[ALC Guide to Creating a Developer Token](https://redirector.arcpublishing.com/alc/arc-products/developer/user-documentation/accessing-the-arc-api/?product=developer)

[ALC User Guides for Draft API](https://redirector.arcpublishing.com/alc/collection/LY7R6OUSXVGFNKKLXXTJIUMSJA)

[Draft API Swagger Docs](https://redirector.arcpublishing.com/alc/docs/swagger/?url=./arc-products/draft.json)
