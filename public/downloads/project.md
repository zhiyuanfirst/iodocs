# klout

## Identity Methods 

#### Get Identity via Twitter ID 

> This method allows you to retrieve a KloutID for a numeric Twitter ID 

``` 
Method: GET, URI: /identity.json/tw/:twitterId 
``` 
Parameter | Type | Default | Description 
--------| -----------|------- |--------- 
twitterId | string | | A Twitter ID (e.g. 500042487) 
#### Get Identity via Google+ ID 

> This method allows you to retreve a Kloud ID for a numeric Google+ ID 

``` 
Method: GET, URI: /identity.json/gp/:googleId 
``` 
Parameter | Type | Default | Description 
--------| -----------|------- |--------- 
googleId | string | | A Google+ ID (e.g. 112620727907435773834) 
#### Get Identity via Instagram ID 

> This method allows you to retreve a Kloud ID for a numeric Instagram ID 

``` 
Method: GET, URI: /identity.json/ig/:instagramId 
``` 
Parameter | Type | Default | Description 
--------| -----------|------- |--------- 
instagramId | string | | An Instagram ID (e.g. 816029) 
#### Get Identity via Twitter Screen Name 

> This method allows you to retrieve a numeric KloutID for a Twitter Screen Name 

``` 
Method: GET, URI: /identity.json/twitter 
``` 
Parameter | Type | Default | Description 
--------| -----------|------- |--------- 
screenName | string | | A Twitter Screen Name (e.g. jtimberlake) 
#### Get Twitter ID via Kloud ID 

> This method allows you to retrieve a Twitter ID for a numeric KloutID 

``` 
Method: GET, URI: /identity.json/klout/:kloutId/tw 
``` 
Parameter | Type | Default | Description 
--------| -----------|------- |--------- 
kloutId | string | | A KloutId (e.g. 635263) 
## User Methods 

#### Show User 

> This method allows you to retrieve a user object 

``` 
Method: GET, URI: /user.json/:kloutId 
``` 
Parameter | Type | Default | Description 
--------| -----------|------- |--------- 
kloutId | string | | A KloutId (e.g. 635263) 
#### Score 

> This method allows you to retrieve a user's Klout Score and Deltas 

``` 
Method: GET, URI: /user.json/:kloutId/score 
``` 
Parameter | Type | Default | Description 
--------| -----------|------- |--------- 
kloutId | string | | A KloutId (e.g. 635263) 
#### Topics 

> This method allows you to retrieve a user's topics 

``` 
Method: GET, URI: /user.json/:kloutId/topics 
``` 
Parameter | Type | Default | Description 
--------| -----------|------- |--------- 
kloutId | string | | A KloutId (e.g. 635263) 
#### Influence 

> This method allows you to retrieve a user's influencers and influencees 

``` 
Method: GET, URI: /user.json/:kloutId/influence 
``` 
Parameter | Type | Default | Description 
--------| -----------|------- |--------- 
kloutId | string | | A KloutId (e.g. 635263) 
