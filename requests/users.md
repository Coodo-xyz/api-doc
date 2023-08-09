# Users

### users/:id

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

### users/:id/polls

{% swagger method="get" baseUrl="https://api.coodo.xyz" summary="Get user polls by ID" path="/users/:id/polls" expanded="false" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="path" type="String" required="true" name="id" %}
ID of the user to get polls 
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
