# Polls

### /polls

{% swagger method="post" path="/polls" baseUrl="https://api.coodo.xyz" summary="Create a poll" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="Authorization" type="String" required="true" %}
Bearer token
{% endswagger-parameter %}

{% swagger-parameter in="body" name="buttons" type="Array" required="true" %}
Buttons array
{% endswagger-parameter %}

{% swagger-parameter in="body" name="anonymous" type="Boolean" required="true" %}
Hide users ids on results
{% endswagger-parameter %}

{% swagger-parameter in="body" name="multiples" required="true" type="Boolean" %}
Multiples choices
{% endswagger-parameter %}

{% swagger-parameter in="body" name="hide_results" required="true" type="Boolean" %}
Hide results while the poll is in progress
{% endswagger-parameter %}

{% swagger-parameter in="body" name="title" required="true" type="String" %}
Poll title
{% endswagger-parameter %}

{% swagger-parameter in="body" name="choices_max" required="true" type="Integer" %}
How many options users can select
{% endswagger-parameter %}

{% swagger-parameter in="body" name="guild" type="Object" required="true" %}
Guild id and name
{% endswagger-parameter %}

{% swagger-parameter in="body" name="timestamp_close" type="Integer" %}
Set an end date
{% endswagger-parameter %}

{% swagger-parameter in="body" name="description" type="String" %}
Poll description
{% endswagger-parameter %}

{% swagger-parameter in="body" name="image" type="String" %}
Poll image
{% endswagger-parameter %}

{% swagger-parameter in="body" name="channelID" type="String" %}
Discord channel ID
{% endswagger-parameter %}

{% swagger-response status="201: Created" description="" %}
```json
{
    "message": "Created",
    "data": {
	"pollID": <string>,
	"channelID": <string>,
	"guild": {
	    "id": <string>,
	    "name": <string>
	},
	"buttons": <array>,
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
    }
}
```
{% endswagger-response %}
{% endswagger %}

### /polls/:id

{% swagger method="get" path="/polls/:id" baseUrl="https://api.coodo.xyz" summary="Find a poll by ID" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="path" name="id" type="String" required="true" %}
ID of the poll to find
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Authorization" type="String" %}
Bearer token
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```json
{
    "message": "OK",
    "data": {
	"pollID": <string>,
	"guild": {
	    "id": <string>,
	    "name": <string>
	},
	"channelID": <string>,
	"buttons": [], // Array is empty (-> polls/:id/results)
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
    }
}
```
{% endswagger-response %}
{% endswagger %}

{% swagger method="get" path="/polls/:id/results" baseUrl="https://api.coodo.xyz" summary="Find poll results by ID" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="path" name="id" type="String" required="true" %}
ID of the poll to find
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Authorization" type="String" required="true" %}
Bearer token
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
<pre class="language-json"><code class="lang-json">{
    "message": "OK",
    "data": {
	"pollID": &#x3C;string>,
	"channelID": &#x3C;string>,
	"guild": {
	    "id": &#x3C;string>,
	    "name": &#x3C;string>
	},
	"buttons": [
<strong>	    {
</strong>                "title": &#x3C;string>,
                "name": &#x3C;string>,
                "ids": [
                    {
                        "id": &#x3C;string>,
                        "username": &#x3C;string>
                    },
                    ...
                ]
            },
            ...
	]
	"multiples": &#x3C;boolean>,
	"choices_max": &#x3C;int>,
	"anonymous": &#x3C;boolean>,
	"ended": &#x3C;boolean>,
	"title": &#x3C;string>,
	"ownerID": &#x3C;string>,
	"timestamp": &#x3C;string>,
	"timestamp_close": &#x3C;int>,
	"hide_results": &#x3C;boolean>,
	"description": &#x3C;string>,
	"image": &#x3C;string>
    }
}
</code></pre>
{% endswagger-response %}
{% endswagger %}

{% swagger method="put" path="/polls/:id" baseUrl="https://api.coodo.xyz" summary="Update a poll by ID" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="path" name="id" type="String" required="true" %}
ID of the poll to update
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Authorization" type="String" required="true" %}
Bearer token
{% endswagger-parameter %}

{% swagger-parameter in="body" name="ended" type="Boolean" %}
Poll state
{% endswagger-parameter %}

{% swagger-parameter in="body" name="title" type="String" %}
Poll title
{% endswagger-parameter %}

{% swagger-parameter in="body" name="timestamp_close" type="Integer" %}
Set an end date
{% endswagger-parameter %}

{% swagger-parameter in="body" name="description" type="String" %}
Poll description
{% endswagger-parameter %}

{% swagger-parameter in="body" name="image" type="String" %}
Poll image
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```json
{
    "message": "OK",
    "data": {
	"pollID": <string>,
	"channelID": <string>,
	"guild": {
	    "id": <string>,
	    "name": <string>
	},
	"buttons": [], // Array is empty (-> polls/:id/results)
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
{% endswagger %}

{% swagger method="delete" path="/polls/:id" baseUrl="https://api.coodo.xyz" summary="Delete a poll by ID" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="path" name="id" type="String" required="true" %}
ID of the poll to delete
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Authorization" type="String" required="true" %}
Bearer token
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```json
{
    "message": "OK",
    "data": {
	"pollID": <string>,
	"channelID": <string>,
	"guild": {
	    "id": <string>,
	    "name": <string>
	},
	"buttons": <array>,
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
{% endswagger %}

### /polls/:id/vote/:choiceId

{% swagger method="put" path="/polls/:id/vote/:choiceId" baseUrl="https://api.coodo.xyz" summary="Vote for a poll using ID" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="path" name="id" type="String" required="true" %}
ID of the user to delete
{% endswagger-parameter %}

{% swagger-parameter in="path" name="choiceId" type="String" required="true" %}
ID of the choice to vote
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Authorization" type="String" required="true" %}
Bearer token
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```json
{
    "message": "OK",
    "data": {
	"pollID": <string>,
	"channelID": <string>,
	"guild": {
	    "id": <string>,
	    "name": <string>
	},
	"buttons": [], // Array is empty (-> polls/:id/results)
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
    }
}ss
```
{% endswagger-response %}

{% swagger-response status="403: Forbidden" description="" %}
```json
{
    "error": "Forbidden"
}
```
{% endswagger-response %}

{% swagger-response status="404: Not Found" description="Poll or choice not found" %}
```json
{
    "error": "Not Found"
}
```
{% endswagger-response %}
{% endswagger %}
