# Logs



{% swagger method="get" path="/logs" baseUrl="https://api.coodo.xyz" summary="Find api logs" %}
{% swagger-description %}
:warning: A maximum of 100 logs are returned
{% endswagger-description %}

{% swagger-parameter in="header" name="Authorization" type="String" required="true" %}
Bearer token
{% endswagger-parameter %}

{% swagger-parameter in="query" name="username" %}
Username filter
{% endswagger-parameter %}

{% swagger-parameter in="query" name="id" %}
User id filter
{% endswagger-parameter %}

{% swagger-parameter in="query" name="action" %}
Action id filter
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```json
{
    "message": "OK",
    "data": [
        {
            "user": {
                "id": <string>,
                "username": <string>
            },
            "action": {
                "id": <int>
            },
            "actions": [
                {
                    "type": <string>, // userId, pollId, roleId, string
                    "title": <string>,
                    "value": <string>
                }
            ],
            "timestamp": <int>
        },
        ...
    ]
}
```
{% endswagger-response %}
{% endswagger %}

<table data-full-width="true"><thead><tr><th data-type="number">ActionId</th><th></th></tr></thead><tbody><tr><td>1</td><td>Create a poll</td></tr><tr><td>2</td><td>Delete a poll</td></tr><tr><td>3</td><td>Login on dashboard</td></tr><tr><td>4</td><td>Vote on a poll</td></tr><tr><td>5</td><td>Update a poll</td></tr><tr><td>6</td><td>Update role</td></tr><tr><td>7</td><td>Buy a plan</td></tr><tr><td>8</td><td>Status page data posted</td></tr><tr><td>9</td><td>Delete a user</td></tr><tr><td>10</td><td>Update a user</td></tr><tr><td>11</td><td>Create a guild</td></tr><tr><td>12</td><td>Update a guild</td></tr><tr><td>13</td><td>Delete a guild</td></tr><tr><td>14</td><td>Create recurrent poll</td></tr><tr><td>15</td><td>Update recurrent poll</td></tr><tr><td>16</td><td>Delete recurrent poll</td></tr></tbody></table>
