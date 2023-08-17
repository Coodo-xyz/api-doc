# Quick start

Here's an example of how you can make requests to `https://api.coodo.xyz/ping` using Node.js and Python, both with Bearer token authorization.

{% tabs %}
{% tab title="Node.JS" %}
```javascript
const axios = require('axios');

const apiUrl = 'https://api.coodo.xyz/ping';
const token = 'YOUR_BEARER_TOKEN';

const headers = {
  Authorization: `Bearer ${token}`
};

axios.get(apiUrl, { headers })
  .then(response => {
    console.log('Node.js Response:', response.data);
  })
  .catch(error => {
    console.error('Node.js Error:', error);
  });

```
{% endtab %}

{% tab title="Python" %}
```python
import requests

api_url = 'https://api.coodo.xyz/ping'
token = 'YOUR_BEARER_TOKEN'

headers = {
    'Authorization': f'Bearer {token}'
}

response = requests.get(api_url, headers=headers)

if response.status_code == 200:
    print('Python Response:', response.json())
else:
    print('Python Error:', response.text)

```
{% endtab %}
{% endtabs %}

## API Flow Diagram

<div data-full-width="true">

<figure><img src="../.gitbook/assets/Systems Api Usage Diagram.png" alt=""><figcaption></figcaption></figure>

</div>
