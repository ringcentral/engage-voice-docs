## Generating Permanent API Tokens

To generate the API token, you would either use your own login, or create an "API User" specifically to host the API tokens you need to call into our system. If you needed to integrate multiple services and each service needed a different level of permissions, you could create multiple API users, each with different Rights. If you had multiple services and they each required the same rights, you could create one or more API tokens for the same user and distribute a unique token around to each service (best practice).

### Authenticate current user to retrieve auth token

Get AuthToken for the user you would like to generate API token for (one time operation)

`curl -X POST https://portal.vacd.biz/api/v1/auth/login -d "username={email}&password={password}"`

In the result, you will see an `authToken` property. This is what you will use to manually generate the API tokens in the next step. You want to copy this, it will look something like:

`baf522ee-5d42-457a-a18d-7b8500eeb573`

### Generate an API Token for a user

Generate the permanent API tokens (every time you run the method below, another API token will be created and returned)

`curl -X POST https://portal.vacd.biz/api/v1/admin/token -H "x-auth-token: {AUTH TOKEN FROM STEP 1}"`

OR

`curl -X POST https://portal.vacd.biz/api/v1/admin/token -H "x-auth-token: {AN EXISTING API TOKEN FOR THIS USER}"`

You now have your permanent API token(s). The value returned from each of the POST requests above will be permanent and look very much like the authToken from Step1. If you lose track, you can always retrieve all of the permanent API tokens for a user by calling the following method with one of the API Tokens you know about, or by logging in with the user who's tokens you're interested in, and pulling the authToken from that user (as in Step 1). In other words, the temporary authToken is 100% interchangeable with the permanent API tokens for the same user.

### List all API Tokens for a user

To List all existing API Tokens for a user:

`curl -X GET https://portal.vacd.biz/api/v1/admin/token -H "x-auth-token: {AUTH TOKEN FROM STEP 1}"`

OR

`curl -X GET https://portal.vacd.biz/api/v1/admin/token -H "x-auth-token: {AN EXISTING API TOKEN FOR THIS USER}"`

### Delete an API Token

If you are done with an API Token and no longer need it, or you feel it may have been compromised, you can delete an existing token as follows.

`curl -X DELETE https://portal.vacd.biz/api/v1/admin/token/{API-TOKEN-FOR-DELETE} -H "x-auth-token: {AUTH TOKEN OR API TOKEN}"`

In the above request, you may use in the x-auth-token header the AuthToken or API Token for the user who's token is getting deleted (including the token for delete itself), or that of any parent user of the user who owns the API token for delete.