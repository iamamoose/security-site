---
title: Apache APISIX security advisories
description: Security information for Apache APISIX
layout: single
---

# Reporting

Do you want disclose a potential security issue for Apache APISIX? Send your report to the [Apache Security Team](mailto:security@apache.org).

# Advisories

This section is experimental: it provides advisories since 2023 and may lag behind the official CVE publications. If you have any feedback on how you would like this data to be provided, you are welcome to reach out on our public [mailinglist](/mailinglist) or privately on [security@apache.org](mailto:security@apache.org)
{.bg-warning}

## Bypass network access control ## { #CVE-2021-33190 }

CVE-2021-33190 [\[CVE json\]](./CVE-2021-33190.cve.json)

### Affected

* Apache APISIX Dashboard at Apache APISIX Dashboard 2.6 2.6


### Description

In Apache APISIX Dashboard version 2.6, we changed the default value of listen host to 0.0.0.0 in order to facilitate users to configure external network access. In the IP allowed list restriction, a risky function was used for the IP acquisition, which made it possible to bypass the network limit. At the same time, the default account and password are fixed.Ultimately these factors lead to the issue of security risks.  This issue is fixed in APISIX Dashboard 2.6.1


### References
* https://lists.apache.org/thread.html/re736aea55e8fd2478f0739c0c38a9375c4204fc1f0bd1ea687f57049%40%3Cdev.apisix.apache.org%3E


## Path traversal in request_uri variable ## { #CVE-2021-43557 }

CVE-2021-43557 [\[CVE json\]](./CVE-2021-43557.cve.json)

### Affected

* Apache APISIX from 1.5 before Apache APISIX 1.5*


### Description

The uri-block plugin in Apache APISIX before 2.10.2 uses $request_uri without verification. The $request_uri is the full original request URI without normalization.
This makes it possible to construct a URI to bypass the block list on some occasions. For instance, when the block list contains "^/internal/", a URI like `//internal/` can be used to bypass it.

Some other plugins also have the same issue. And it may affect the developer's custom plugin.

### References
* https://lists.apache.org/thread/18jyd458ptocr31rnkjs71w4h366mv7h


## security vulnerability on unauthorized access. ## { #CVE-2021-45232 }

CVE-2021-45232 [\[CVE json\]](./CVE-2021-45232.cve.json)

### Affected

* Apache APISIX Dashboard at 2.7 and 2.7.1
* Apache APISIX Dashboard at 2.8
* Apache APISIX Dashboard at 2.9
* Apache APISIX Dashboard at 2.10


### Description

In Apache APISIX Dashboard before 2.10.1, the Manager API uses two frameworks and introduces framework `droplet` on the basis of framework `gin`, all APIs and authentication middleware are developed based on framework `droplet`, but some API directly use the interface of framework `gin` thus bypassing the authentication.  

### References
* https://lists.apache.org/thread/979qbl6vlm8269fopfyygnxofgqyn6k5


### Credits
* Independently discovered by ZHU Yucheng of YuanbaoTeach Security Team.


## apisix/batch-requests plugin allows overwriting the X-REAL-IP header ## { #CVE-2022-24112 }

CVE-2022-24112 [\[CVE json\]](./CVE-2022-24112.cve.json)

### Affected

* Apache APISIX from Apache APISIX 2.12 before 2.12.1
* Apache APISIX from Apache APISIX 2.10 before 2.10.4
* Apache APISIX from 1.3 before Apache APISIX 1*


### Description

An attacker can abuse the batch-requests plugin to send requests to bypass the IP restriction of Admin API.
A default configuration of Apache APISIX (with default API key) is vulnerable to remote code execution.
When the admin key was changed or the port of Admin API was changed to a port different from the data panel, the impact is lower. But there is still a risk to bypass the IP restriction of Apache APISIX's data panel.

There is a check in the batch-requests plugin which overrides the client IP with its real remote IP. But due to a bug in the code, this check can be bypassed.

### References
* https://lists.apache.org/thread/lcdqywz8zy94mdysk7p3gfdgn51jmt94


### Credits
* Original discovery by Real World CTF at Chaitin Tech. Reported by Sauercloud.


## Apache APISIX: the body_schema check in request-validation plugin can be bypassed ## { #CVE-2022-25757 }

CVE-2022-25757 [\[CVE json\]](./CVE-2022-25757.cve.json)

### Affected

* Apache APISIX from Apache APISIX through 2.12.1


### Description

In Apache APISIX before 2.13.0, when decoding JSON with duplicate keys, lua-cjson will choose the last occurred value as the result. By passing a JSON with a duplicate key, the attacker can bypass the body_schema validation in the request-validation plugin. For example, `{"string_payload":"bad","string_payload":"good"}` can be used to hide the "bad" input.

Systems satisfy three conditions below are affected by this attack:
1. use body_schema validation in the request-validation plugin
2. upstream application uses a special JSON library that chooses the first occurred value, like jsoniter or gojay
3. upstream application does not validate the input anymore.

The fix in APISIX is to re-encode the validated JSON input back into the request body at the side of APISIX.Improper Input Validation vulnerability in __COMPONENT__ of Apache APISIX allows an attacker to __IMPACT__.  This issue affects Apache APISIX Apache APISIX version 2.12.1 and prior versions.

### References
* https://lists.apache.org/thread/03vd2j81krxmpz6xo8p1dl642flpo6fv


### Credits
* Thanks for Guangli Dong from www.huoxian.cn


## apisix/jwt-auth may leak secrets in error response ## { #CVE-2022-29266 }

CVE-2022-29266 [\[CVE json\]](./CVE-2022-29266.cve.json)

### Affected

* Apache APISIX from Apache APISIX through 2.13.0


### Description

In Apache APISIX before 2.13.1, the jwt-auth plugin has a security issue that leaks the user's secret key because the error message returned from the dependency lua-resty-jwt contains sensitive information.

### References
* https://lists.apache.org/thread/6qpfyxogbvn18g9xr8g218jjfjbfsbhr


### Credits
* Discovered and reported by a team from Kingdee Software (China) Ltd. consisting of Zhongyuan Tang, Hongfeng Xie, and Bing Chen.
