---
title: Apache JSPWiki security advisories
description: Security information for Apache JSPWiki
layout: single
---

# Reporting

Do you want disclose a potential security issue for Apache JSPWiki? You can read more about the projects' security policy on their [security page](https://jspwiki-wiki.apache.org/Wiki.jsp?page=Security), and email your report to the [Apache Security Team](mailto:security@apache.org).

# Advisories

This section is experimental: it provides advisories since 2023 and may lag behind the official CVE publications. It may also lack details found on the [project security page](https://jspwiki-wiki.apache.org/Wiki.jsp?page=Security). If you have any feedback on how you would like this data to be provided, you are welcome to reach out on our public [mailinglist](/mailinglist) or privately on [security@apache.org](mailto:security@apache.org)
{.bg-warning}

## XSS vulnerability on Denounce plugin ## { #CVE-2021-40369 }

CVE-2021-40369 [\[CVE json\]](./CVE-2021-40369.cve.json)

### Affected

* Apache JSPWiki from Apache JSPWiki through 2.11.0.M8


### Description

A carefully crafted plugin link invocation could trigger an XSS vulnerability on Apache JSPWiki, related to the Denounce plugin, which could allow the attacker to execute javascript in the victim's browser and get some sensitive information about the victim.  Apache JSPWiki users should upgrade to 2.11.0 or later. 

### References
* https://jspwiki-wiki.apache.org/Wiki.jsp?page=CVE-2021-40369
* https://lists.apache.org/thread/r2j00nrnpjgcmoxvlv3pgfoq9kzrcsfh


### Credits
* Apache JSPWiki would like to thank map1e (root@lazymaple.pw) for discovering this issue.


## Arbitrary file deletion on logout ## { #CVE-2021-44140 }

CVE-2021-44140 [\[CVE json\]](./CVE-2021-44140.cve.json)

### Affected

* Apache JSPWiki from Apache JSPWiki through 2.11.0.M8


### Description

Remote attackers may delete arbitrary files in a system hosting a JSPWiki instance, versions up to 2.11.0.M8, by using a carefuly crafted http request on logout, given that those files are reachable to the user running the JSPWiki instance. Apache JSPWiki users should upgrade to 2.11.0 or later. 

### References
* https://jspwiki-wiki.apache.org/Wiki.jsp?page=CVE-2021-44140
* https://lists.apache.org/thread/5qglpjdhvobppx7j550lf1sk28f6011t


### Credits
* Apache JSPWiki would like to thank haby0 (forhaby0@gmail.com) from Duxiaoman Financial Security Team for discovering and proposing the fix for this issue.


## Apache JSPWiki CSRF Account Takeover ## { #CVE-2022-24947 }

CVE-2022-24947 [\[CVE json\]](./CVE-2022-24947.cve.json)

### Affected

* Apache JSPWiki at Apache JSPWiki up to 2.11.1 


### Description

Apache JSPWiki user preferences form is vulnerable to CSRF attacks, which can lead to account takeover.   Apache JSPWiki users should upgrade to 2.11.2 or later. 

### References
* https://lists.apache.org/thread/txrgykjkpt80t57kzpbjo8kfrv8ss02c


### Credits
* This issue was discovered initially by Cristian Borlovan from Ounce Labs Security (ref. JSPWIKI-79), and later on and independently from this by Paulos Yibelo, from Octagon Networks. 


## Apache JSPWiki Cross-site scripting vulnerability on User Preferences screen ## { #CVE-2022-24948 }

CVE-2022-24948 [\[CVE json\]](./CVE-2022-24948.cve.json)

### Affected

* Apache JSPWiki at Apache JSPWiki up to 2.11.1 


### Description

A carefully crafted user preferences for submission could trigger an XSS vulnerability on Apache JSPWiki, related to the user preferences screen, which could allow the attacker to execute javascript in the victim's browser and get some sensitive information about the victim.  Apache JSPWiki users should upgrade to 2.11.2 or later. 

### References
* https://lists.apache.org/thread/86p0yzopc4mw2h5bkwpt927b2c8tfq3b


### Credits
* This issue was discovered by Paulos Yibelo, from Octagon Networks. 


## XSS vulnerability on XHRHtml2Markup.jsp in JSPWiki 2.11.2 ## { #CVE-2022-27166 }

CVE-2022-27166 [\[CVE json\]](./CVE-2022-27166.cve.json)

### Affected

* Apache JSPWiki from Apache JSPWiki through Apache JSPWiki up to 2.11.2


### Description

A carefully crafted request on XHRHtml2Markup.jsp could trigger an XSS vulnerability on Apache JSPWiki up to and including 2.11.2, which could allow the attacker to execute javascript in the victim's browser and get some sensitive information about the victim.

### References
* https://jspwiki-wiki.apache.org/Wiki.jsp?page=CVE-2022-28732


### Credits
* Issue was discovered by Salt, <saltnekoko AT gmail DOT com>


## Apache JSPWiki Cross-site scripting vulnerability on AJAXPreview.jsp ## { #CVE-2022-28730 }

CVE-2022-28730 [\[CVE json\]](./CVE-2022-28730.cve.json)

### Affected

* Apache JSPWiki from Apache JSPWiki through Apache JSPWiki up to 2.11.2


### Description

A carefully crafted request on AJAXPreview.jsp could trigger an XSS vulnerability on Apache JSPWiki, which could allow the attacker to execute javascript in the victim's browser and get some sensitive information about the victim.

This vulnerability leverages CVE-2021-40369, where the Denounce plugin dangerously renders user-supplied URLs. Upon re-testing CVE-2021-40369, it appears that the patch was incomplete as it was still possible to insert malicious input via the Denounce plugin.  

Apache JSPWiki users should upgrade to 2.11.3 or later. 

### References
* https://jspwiki-wiki.apache.org/Wiki.jsp?page=CVE-2022-28732


### Credits
* This issue was discovered by Poh Jia Hao, from Star Labs <info AT starlabs DOT sg>


## Apache JSPWiki CSRF in UserPreferences.jsp ## { #CVE-2022-28731 }

CVE-2022-28731 [\[CVE json\]](./CVE-2022-28731.cve.json)

### Affected

* Apache JSPWiki from Apache JSPWiki through Apache JSPWiki up to 2.11.2


### Description

A carefully crafted request on UserPreferences.jsp could trigger an CSRF vulnerability on Apache JSPWiki before 2.11.3, which could allow the attacker to modify the email associated with the attacked account, and then a reset password request from the login page. 

### References
* https://jspwiki-wiki.apache.org/Wiki.jsp?page=CVE-2022-28732


### Credits
* This issue was discovered by Fabrice Perez, <fabioperez AT gmail DOT com> 


## Apache JSPWiki Cross-site scripting vulnerability on WeblogPlugin ## { #CVE-2022-28732 }

CVE-2022-28732 [\[CVE json\]](./CVE-2022-28732.cve.json)

### Affected

* Apache JSPWiki from Apache JSPWiki through Apache JSPWiki up to 2.11.2


### Description

A carefully crafted request on WeblogPlugin could trigger an XSS vulnerability on Apache JSPWiki, which could allow the attacker to execute javascript in the victim's browser and get some sensitive information about the victim.  Apache JSPWiki users should upgrade to 2.11.3 or later. 

### References
* https://jspwiki-wiki.apache.org/Wiki.jsp?page=CVE-2022-28732


### Credits
* This issue was discovered by Wang Ran, from JDArmy, @jd.com 


## User Group Privilege Escalation ## { #CVE-2022-34158 }

CVE-2022-34158 [\[CVE json\]](./CVE-2022-34158.cve.json)

### Affected

* Apache JSPWiki from unspecified through Apache JSPWiki up to 2.11.2


### Description

A carefully crafted invocation on the Image plugin could trigger an CSRF vulnerability on Apache JSPWiki before 2.11.3, which could allow a group privilege escalation of the attacker's account. Further examination of this issue established that it could also be used to modify the email associated with the attacked account, and then a reset password request from the login page. 

### References
* https://jspwiki-wiki.apache.org/Wiki.jsp?page=CVE-2022-34158


### Credits
* This issue was discovered by Huiseong Seo (t0rchwo0d), <awdr1624AT gmail DOT com>


## XSS Injection points in several plugins ## { #CVE-2022-46907 }

CVE-2022-46907 [\[CVE json\]](./CVE-2022-46907.cve.json)

### Affected

* Apache JSPWiki before Apache JSPWiki up to 2.12.0 


### Description

A carefully crafted request on several JSPWiki plugins could trigger an XSS vulnerability on Apache JSPWiki, which could allow the attacker to execute javascript in the victim's browser and get some sensitive information about the victim.  Apache JSPWiki users should upgrade to 2.12.0 or later.<br>

### References
* https://lists.apache.org/thread/1m0mkq2nttx8tn94m11mytn4f0tv1504


### Credits
* This issue was discovered by Eugene Lim and Sng Jay Kai from Government Technology Agency of Singapore (finder)
