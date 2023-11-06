# Users

### /user

{% swagger method="get" path="/user" baseUrl="https://api.coodo.xyz" summary="Find user using token" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="Authorization" type="String" required="true" %}
Bearer token
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```json
{
    "message": "OK",
    "data": {
    	"id": <string>,
	"username": <string>,
	"discriminator": <string>,
	"public_flags": <int>,
	"flags": <int>,
	"locale": <string>,
	"premium_type": <int>,
	"tag": <string>,
	"avatarURL": <string>,
	"disabled": <boolean>,
	"premium": <boolean>,
	"alerts": <int>,
	"roles": <array>,
	"lastUpdate": <int>,
	"email": <string>,
	"stripeCustomerId": <string>,
	"favoritesPolls": <array> // Array of polls ids
    }
}
```
{% endswagger-response %}
{% endswagger %}

{% swagger method="get" path="/user/favorites" baseUrl="https://api.coodo.xyz" summary="Find user favorites polls using token" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="Authorization" type="String" required="true" %}
Bearer token
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
<pre class="language-json"><code class="lang-json">{
    "message": "OK",
    "data": [
        { <a data-footnote-ref href="#user-content-fn-1">pollObject</a> },
        ...
    ]
}
</code></pre>
{% endswagger-response %}
{% endswagger %}

{% swagger method="put" path="/user/favorites" baseUrl="https://api.coodo.xyz" summary="Update user favorites polls using token" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="Authorization" type="String" required="true" %}
Bearer token
{% endswagger-parameter %}

{% swagger-parameter in="body" name="favoritesPolls" type="Array" required="true" %}
Array of polls ids
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```json
{
    "message": "OK",
    "data": <array> // Array of polls ids
}
```
{% endswagger-response %}
{% endswagger %}

### /users/:id

{% swagger method="get" path="/users/:id" baseUrl="https://api.coodo.xyz" summary="Find user by ID" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="path" name="id" required="true" type="String" %}
ID of the user to return
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Authorization" type="String" required="true" %}
Bearer token
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```json
{
    "message": "OK",
    "data": {
        "id": <string>,
        "username": <string>,
        "discriminator": <string>,
        "public_flags": <int>,
        "flags": <int>,
        "locale": <string>,
        "premium_type": <int>,
        "tag": <string>,
        "avatarURL": <string>,
        "disabled": <boolean>,
        "alerts": <int>,
        "roles": <array>,
        "favoritesPolls": <array>,
        "lastUpdate": <int>
    }
}
```
{% endswagger-response %}

{% swagger-response status="404: Not Found" description="" %}
```json
{
    "error": "Not Found"
}
```
{% endswagger-response %}
{% endswagger %}

{% swagger method="put" path="/users/:id" baseUrl="https://api.coodo.xyz" summary="Update user by ID" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="path" name="id" type="String" required="true" %}
ID of the user to edit
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Authorization" type="String" required="true" %}
Bearer token
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```json
{
    "message": "OK",
    "data": {
    	"id": <string>,
	"username": <string>,
	"discriminator": <string>,
	"public_flags": <int>,
	"flags": <int>,
	"locale": <string>,
	"premium_type": <int>,
	"tag": <string>,
	"avatarURL": <string>,
	"disabled": <boolean>,
	"premium": <boolean>,
	"alerts": <int>,
	"roles": <array>,
	"lastUpdate": <int>,
	"email": <string>,
	"stripeCustomerId": <string>,
	"favoritesPolls": <array>
    }
}
```
{% endswagger-response %}

{% swagger-response status="403: Forbidden" description="" %}
```json
{
    "error": "Forbidden"
}
```
{% endswagger-response %}

{% swagger-response status="404: Not Found" description="" %}
```json
{
    "error": "Not Found"
}
```
{% endswagger-response %}
{% endswagger %}

{% swagger method="delete" path="/users/:id" baseUrl="https://api.coodo.xyz" summary="Delete user by ID" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="path" name="id" type="String" required="true" %}
ID of the user to delete
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Authorization" type="String" required="true" %}
Bearer token
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```json
{
    "message": "OK",
    "data": {
    	"id": <string>,
	"username": <string>,
	"discriminator": <string>,
	"public_flags": <int>,
	"flags": <int>,
	"locale": <string>,
	"premium_type": <int>,
	"tag": <string>,
	"avatarURL": <string>,
	"disabled": <boolean>,
	"premium": <boolean>,
	"alerts": <int>,
	"roles": { type: Array },
	"lastUpdate": <int>,
	"email": <string>,
	"stripeCustomerId": <string>,
	"favoritesPolls": <array>
}
```
{% endswagger-response %}

{% swagger-response status="403: Forbidden" description="" %}
```json
{
    "error": "Forbidden"
}
```
{% endswagger-response %}

{% swagger-response status="404: Not Found" description="" %}
```json
{
    "error": "Not Found"
}
```
{% endswagger-response %}
{% endswagger %}

### /users/:id/polls

{% swagger method="get" baseUrl="https://api.coodo.xyz" summary="Get user polls by ID" path="/users/:id/polls" expanded="false" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="path" type="String" required="true" name="id" %}
ID of the user to get polls&#x20;
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Authorization" type="String" required="true" %}
Bearer token
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```json
{
    "message": "OK",
    "data": [
    	{
            "pollID": <string>,
            "channelID": <string>,
            "buttons": [], // RESULTS HIDDEN (-> /polls/:id/results
            "multiples": <boolean>,
            "choices_max": <int>,
            "anonymous": <boolean>,
            "ended": <boolean>,
	    "title": <string>,
	    "ownerID": <string>,
	    "timestamp": <string>,
	    "timestamp_close": <int>,
	    "hide_results": <boolean>,
	    "description": <string>,
	    "image": <string>
	},
	...
    ]
}
```
{% endswagger-response %}
{% endswagger %}

{% swagger method="delete" path="/users/:id/polls" baseUrl="https://api.coodo.xyz" summary="Delete user polls by ID" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="path" name="id" type="String" required="true" %}
ID of the user to delete polls
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Authorization" type="String" required="true" %}
Bearer token
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```json
{
    "message": "OK",
    "data": [
    	{
            "pollID": <string>,
            "channelID": <string>,
            "buttons": [], // RESULTS HIDDEN (-> /polls/:id/results
            "multiples": <boolean>,
            "choices_max": <int>,
            "anonymous": <boolean>,
            "ended": <boolean>,
	    "title": <string>,
	    "ownerID": <string>,
	    "timestamp": <string>,
	    "timestamp_close": <int>,
	    "hide_results": <boolean>,
	    "description": <string>,
	    "image": <string>
	},
	...
    ]
}
```
{% endswagger-response %}

{% swagger-response status="403: Forbidden" description="" %}
```json
{
    "error": "Forbidden"
}
```
{% endswagger-response %}
{% endswagger %}

### /users/:id/polls/count

{% swagger method="get" path="/users/:id/polls/count" baseUrl="https://api.coodo.xyz" summary="Get user polls count by ID" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="path" name="id" type="String" required="true" %}
ID of the user to delete polls
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Authorization" type="String" required="true" %}
Bearer token
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```json
{
    "message": "OK",
    "count": <int>,
    "max": <int>
}
```
{% endswagger-response %}
{% endswagger %}

### /users

{% swagger method="get" path="/users" baseUrl="https://api.coodo.xyz" summary="Get users" %}
{% swagger-description %}
:warning: A maximum of 50 users are returned
{% endswagger-description %}

{% swagger-parameter in="query" name="username" type="String" %}
Username filter
{% endswagger-parameter %}

{% swagger-parameter in="query" %}
Username id
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```json
{
    "message": "OK",
    "data": [
        {
            "id": <string>,
            "username": <string>,
            "discriminator": <string>,
            "public_flags": <int>,
            "flags": <int>,
            "locale": <string>,
            "premium_type": <int>,
            "tag": <string>,
            "avatarURL": <string>,
            "disabled": <boolean>,
            "alerts": <int>,
            "roles": <array>,
            "favoritesPolls": <array>,
            "lastUpdate": <int>
        }
        {...}
    ]
}
```
{% endswagger-response %}
{% endswagger %}

### /users/:id/guilds

{% swagger method="get" path="/users/:id/guilds" baseUrl="https://api.coodo.xyz" summary="Get user guilds by ID" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="path" name="id" type="String" required="true" %}
ID of the user to get polls&#x20;
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Authorization" type="String" required="true" %}
Bearer token
{% endswagger-parameter %}

{% swagger-parameter in="query" name="botOn" type="String" %}
Only user guilds where bot is on
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```json
{
    "message": "OK",
    "data": [
    	{
            "id": <string>,
            "name": <string>,
            "icon": <string>,
            "features": <array>,
            "approximate_member_count": <int>,
	    "approximate_presence_count": <int>,
            "owner_id": <string>, // only with botOn = true
	    "last_update": <int>, // only with botOn = true
	    "owner": <boolean>, // only with botOn = false
	    "permissions": <string>, // only with botOn = false
	    "channels": <array>, // only with botOn = false
	},
	...
    ]
}
```
{% endswagger-response %}
{% endswagger %}

[^1]: See polls requests page
