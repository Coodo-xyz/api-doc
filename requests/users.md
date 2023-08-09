# users

{% swagger method="get" path="/users/{userId}" baseUrl="https://api.coodo.xyz" summary="Find user by ID" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="path" name="userId" required="true" type="String" %}
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
