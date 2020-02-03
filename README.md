## Arc Publishing Platform Postman collection

This repo contains the Postman collection with pre-baked calls to the Arc Publishing Platform. For now, this includes all endpoints available as part of the Draft API.

### Getting Started:

This Postman Collection uses a pre-defined environment called `Testing Environment` which can be found in this repo. This environment contains Postman variables that make using the Collection easier, like setting a `lastDocumentId` variable so no copying and pasting of document_ids needs to occur. It's **very handy** and we strongly recommend using it!

To use the Collection and Environment, first import both to your local Postman Client.

Next, set the following variables in the Environment, which will be used across all your API calls:

1. `token` - a developer token from your Arc Developer Center (if you need help, see the docs in the Supporting Documentation section)
2. `org` - the org id associated with your organization in Arc (found in your Arc URL: https://ORG.arcpublishing.com)
3. `defaultWebsite` - the site you'd like your API calls to hit against
4. `userId` - your Arc user id (used to login to Okta)
5. `websiteId1` - the id of a website to test circulating to and from
6. `websiteId2` - the id of a website to test circulating to and from


### How the Collection Works:

This Collection does some automagical variable filling to prevent users from needing to copy and paste or come up with new and existing fake story headlines!

When Creating New Documents, for example, you'll see the POST Body pre-filled to use your `defaultWebsite` and `org` where required, but also to use your user name and a document creation counter to auto-generate headlines and slugs. For your first creation, if your username is `meg-delaunay`, the headline will become `Test Document meg-delaunay 0`. This counter variable will increment automagically for you and update throughout the collection. The same holds true for any other "counter" variables throughout the collection.

Throughout the collection, you'll see many endpoints use a `latestDocumentId` variable, which pulls the document_id from the response body of your most recent call and uses it in your next call. This way, if you want to create a document and then immediately get the document you created, the document_id will already be filled in for you. The same holds for `latestRevisionId`, `latestDraftRevisionId`, and any other "latest" variables throughout! Nifty!

The `websiteId1` and `websiteId2` parameters are used in the `/circulation`, `/redirect`, and `url-format-rule` endpoints in order to, again, prevent copying and pasting of different website names across different API calls. These calls benefit from having two different websites preloaded, in order to see the multisite features of circulations and to test redirects.

All of these auto-filling variables make using the Collection easier, but feel free to override them where appropriate. On a similar note, the ANS used in creating a document is a bare minimum version, and can be modified as needed to test "real" stories.

### Maintaining this Collection:

The Team behind the Arc Publishing Platform (Draft API) will be periodically updating this repo with new features, endpoints, or documentation, in order to keep it up to date with the latest version of the Publishing Platform. If you find an error in the collection, please feel free to submit a PR and help us keep this maintained for everyone. 

### Supporting Documentation:

[ALC Guide to Creating a Developer Token](https://redirector.arcpublishing.com/alc/arc-products/developer/user-documentation/accessing-the-arc-api/?product=developer)

[ALC User Guides for Draft API](https://redirector.arcpublishing.com/alc/collection/LY7R6OUSXVGFNKKLXXTJIUMSJA)

[Draft API Swagger Docs](https://redirector.arcpublishing.com/alc/docs/swagger/?url=./arc-products/draft.json)
