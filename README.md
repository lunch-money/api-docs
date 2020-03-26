---
description: >-
  Welcome to the Lunch Money developer API! We created this to enable the user
  and the community to build rich plug-ins to complement their Lunch Money
  experience.
---

# Getting Started

## Current Status

As of March 27, the developer API is officially in open public beta. During this time, please continue to heed caution and use this API at your own risk as any and all changes are irreversible.

We welcome feedback via email \(support@lunchmoney.app\). These docs are also on Github, so if you see a mistake or something that could be improved, feel free to open a pull request!

## Connecting to the Lunch Money API

### Get an access token

Get your access token by going to this page: [**https://my.lunchmoney.app/developers**](https://my.lunchmoney.app/developers)\*\*\*\*

### **Connect to the server**

You’ll be connecting to the URL **https://dev.lunchmoney.app**. There are two ways to make a request:

|  |  |
| :--- | :--- |
| Recommended | `https://dev.lunchmoney.app/v1/categories` with the Authorization header field set to `Bearer YOURACCESSTOKEN` |
| Not recommended | `https://dev.lunchmoney.app/v1/categories?access_token=YOURACCESSTOKEN` |

{% hint style="info" %}
**For POST requests, ensure you set Content-Type to application/json**
{% endhint %}



