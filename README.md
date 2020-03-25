# Get started

## Connecting to the Lunch Money API

### Get an access token

Get your access token by going to this page: [https://my.lunchmoney.app/developers](https://my.lunchmoney.app/developers)

### **Connect to the server**

You’ll be connecting to the URL [https://dev.lunchmoney.app](https://dev.lunchmoney.app). There are two ways to make a request:

|  |  |
| :--- | :--- |
| Recommended | `https://dev.lunchmoney.app/v1/categories` with the Authorization header field set to `Bearer YOURACCESSTOKEN` |
| Not recommended | `https://dev.lunchmoney.app/v1/categories?access_token=YOURACCESSTOKEN` |

{% hint style="info" %}
**For POST requests, ensure you set Content-Type to application/json**
{% endhint %}



