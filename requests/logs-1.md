# Stats



{% swagger method="get" path="/stats" baseUrl="https://api.coodo.xyz" summary="Get stats" %}
{% swagger-description %}
:warning: A maximum of 100 days of stats are returned
{% endswagger-description %}

{% swagger-parameter in="header" name="Authorization" type="String" required="true" %}
Bearer token
{% endswagger-parameter %}

{% swagger-parameter in="query" name="limit" %}
Limit filter
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```json
{
    "message": "OK",
    "data": [
        {
	    "date": <String>,
	    "guildsSize": <String>,
	    "usersSize": <String>,
	    "usersSizeSupport": <String>,
	    "dashbordUsersSize": <String>,
	    "premiumSize": <String>,
	    "votesCount": <String>,
	    "guilds": {
		"added": <String>
		"removed": <String>
	    }
	},
        ...
    ]
}
```
{% endswagger-response %}
{% endswagger %}
