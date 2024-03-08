## Get an access token ##

curl --location --request POST 'https://login.microsoftonline.com/{tenant}/oauth2/v2.0/token' \
--header 'Content-Type: application/x-www-form-urlencoded' \
--data-urlencode 'client_id={client_id}' \
--data-urlencode 'scope=https://graph.microsoft.com/.default' \
--data-urlencode 'client_secret={client_secret}' \
--data-urlencode 'grant_type=client_credentials'


## Get user information ##

userid={Object_ID} 
curl --location --request GET "https://graph.microsoft.com/v1.0/users/$userid"'?$select=displayName,givenName,postalCode,extension_{appId_without_hyphens}_{custom_attribute_name}' \
--header 'Authorization: Bearer {token}' 

Reference:
* [Get access on behalf of a user](https://learn.microsoft.com/en-us/graph/auth-v2-user?tabs=http)
* [Get a user](https://learn.microsoft.com/en-us/graph/api/user-get?view=graph-rest-1.0&tabs=http)