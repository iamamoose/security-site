---
title: Apache DolphinScheduler security advisories
description: Security information for Apache DolphinScheduler
layout: single
---

# Reporting

Do you want disclose a potential security issue for Apache DolphinScheduler? Send your report to the [Apache Security Team](mailto:security@apache.org).

# Advisories

This section is experimental: it provides advisories since 2023 and may lag behind the official CVE publications. If you have any feedback on how you would like this data to be provided, you are welcome to reach out on our public [mailinglist](/mailinglist) or privately on [security@apache.org](mailto:security@apache.org)
{.bg-warning}

## Apache DolphinScheduler (incubating) Permission vulnerability ## { #CVE-2020-13922 }

CVE-2020-13922 [\[CVE json\]](./CVE-2020-13922.cve.json)

### Affected

* Apache DolphinScheduler from Apache DolphinScheduler before 1.3.2


### Description

Versions of Apache DolphinScheduler prior to 1.3.2 allowed an ordinary user under any tenant to override another users password through the API interface.

### References
* https://www.mail-archive.com/announce%40apache.org/msg06076.html


### Credits
* This issue was discovered by xuxiang of DtDream security


## DolphinScheduler mysql jdbc connector parameters deserialize remote code execution ## { #CVE-2021-27644 }

CVE-2021-27644 [\[CVE json\]](./CVE-2021-27644.cve.json)

### Affected

* Apache DolphinScheduler from Apache DolphinScheduler before 1.3.6


### Description

In Apache DolphinScheduler before 1.3.6 versions, authorized users can use SQL injection in the data source center. (Only applicable to MySQL data source with internal login account password)


### References
* https://lists.apache.org/thread.html/r35d6acf021486a390a7ea09e6650c2fe19e72522bd484791d606a6e6%40%3Cdev.dolphinscheduler.apache.org%3E


### Credits
* This issue was discovered by Jinchen Sheng of Ant FG Security Lab


## Apache DolphinScheduler user registration is vulnerable to ReDoS attacks ## { #CVE-2022-25598 }

CVE-2022-25598 [\[CVE json\]](./CVE-2022-25598.cve.json)

### Affected

* Apache DolphinScheduler from Apache DolphinScheduler before 2.0.5


### Description

Apache DolphinScheduler user registration is vulnerable to Regular express Denial of Service (ReDoS) attacks, Apache DolphinScheduler users should upgrade to version 2.0.5 or higher.Uncontrolled Resource Consumption vulnerability in __COMPONENT__ of Apache DolphinScheduler allows an attacker to __IMPACT__.  This issue affects Apache DolphinScheduler Apache DolphinScheduler versions prior to 2.0.5.

### References
* https://lists.apache.org/thread/hwnw7xr969sg5nv84wz75nfr2c76fl93


### Credits
* This issue was discovered by Zheng Wang of HIT


## Apache DolphinScheduler exposes files without authentication ## { #CVE-2022-26884 }

CVE-2022-26884 [\[CVE json\]](./CVE-2022-26884.cve.json)

### Affected

* Apache DolphinScheduler from Apache DolphinScheduler before 2.0.6


### Description

Users can read any files by log server, Apache DolphinScheduler users should upgrade to version 2.0.6 or higher.

### References
* https://lists.apache.org/thread/xfdst5y4hnrm2ntmc5jzrgmw2htyyb9c


## Apache DolphinScheduler config file read by task risk ## { #CVE-2022-26885 }

CVE-2022-26885 [\[CVE json\]](./CVE-2022-26885.cve.json)

### Affected

* Apache DolphinScheduler from Apache DolphinScheduler before 2.0.6


### Description

When using tasks to read config files, there is a risk of database password disclosure.   We recommend you upgrade to version 2.0.6 or higher.

### References
* https://lists.apache.org/thread/z7084r9cs2r26cszkkgjqpb5bhnxqssp


## Apache DolphinScheduler prior to 3.0.0 allows path traversal ## { #CVE-2022-34662 }

CVE-2022-34662 [\[CVE json\]](./CVE-2022-34662.cve.json)

### Affected

* Apache DolphinScheduler from Apache DolphinScheduler through 3.0.0-beta-1


### Description

When users add resources to the resource center with a relation path will cause path traversal issues and only for logged-in users. You could upgrade to version 3.0.0 or higher

### References
* https://lists.apache.org/thread/pbdzqf9ntxyvs4cr0x2dgk9zlf43btz8


### Credits
* This issue was discovered by Jigang Dong of M1QLin Security Team


## Apache DolphinScheduler prior to 2.0.5 have command execution vulnerability ## { #CVE-2022-45462 }

CVE-2022-45462 [\[CVE json\]](./CVE-2022-45462.cve.json)

### Affected

* Apache DolphinScheduler from unspecified through 2.0.5


### Description

Alarm instance management has command injection when there is a specific command configured. It is only for logged-in users. We recommend you upgrade to version 2.0.6 or higher

### References
* https://lists.apache.org/thread/2f126y32bf1v3mvxkdgt2jr5j3l1t01w


### Credits
* This issue was discovered by Jigang Dong of M1QLin Security Team


## Remote command execution Vulnerability in script alert plugin ## { #CVE-2022-45875 }

CVE-2022-45875 [\[CVE json\]](./CVE-2022-45875.cve.json)

### Affected

* Apache DolphinScheduler from 3.0 through 3.0.1
* Apache DolphinScheduler from 3.1 through 3.1.0


### Description

Improper validation of script alert plugin parameters in Apache DolphinScheduler to avoid remote command execution vulnerability.  This issue affects Apache DolphinScheduler version 3.0.1 and prior versions; version 3.1.0 and prior versions.<br><span style="background-color: rgb(255, 255, 255);">This attack can be performed only by authenticated users which can login to DS.</span><br><br>

### References
* https://lists.apache.org/thread/r0wqzkjsoq17j6ww381kmpx3jjp9hb6r


### Credits
* 4ra1n of Chaitin Tech (finder)


## Apache DolphinScheduler 3.0.0 to 3.1.1 python gateway has improper authentication ## { #CVE-2023-25601 }

CVE-2023-25601 [\[CVE json\]](./CVE-2023-25601.cve.json)

### Affected

* Apache DolphinScheduler from 3.0.0 before 3.1.2


### Description

On version 3.0.0 through 3.1.1, Apache DolphinScheduler's python gateway suffered from improper authentication: an attacker could use a socket bytes attack without authentication. This issue has been fixed from version 3.1.2 onwards. For users who use version 3.0.0 to 3.1.1, you can turn off the python-gateway function by changing the value `python-gateway.enabled=false` in configuration file `application.yaml`. If you are using the python gateway, please upgrade to version 3.1.2 or above.<br>

### References
* https://lists.apache.org/thread/25g77jqczp3t8cz56hk1p65q7m6c64rf


## Apache dolphinscheduler sensitive information disclosure ## { #CVE-2023-48796 }

CVE-2023-48796 [\[CVE json\]](./CVE-2023-48796.cve.json)

### Affected

* Apache DolphinScheduler from 3.0.0 before 3.0.2


### Description

Exposure of Sensitive Information to an Unauthorized Actor vulnerability in Apache DolphinScheduler.<br><br>The information exposed to unauthorized actors may include sensitive data such as database credentials.<br><br>Users who can't upgrade to the fixed version can also set environment variable `MANAGEMENT_ENDPOINTS_WEB_EXPOSURE_INCLUDE=health,metrics,prometheus` to workaround this, or add the following section in the `application.yaml` file<br><br><br>```<br>management:<br>&nbsp; endpoints:<br>&nbsp; &nbsp; web:<br>&nbsp; &nbsp; &nbsp; exposure:<br>&nbsp; &nbsp; &nbsp; &nbsp; include: health,metrics,prometheus<br>```<br><p><br></p><p>This issue affects Apache DolphinScheduler: from 3.0.0 before 3.0.2.</p><p>Users are recommended to upgrade to version 3.0.2, which fixes the issue.</p>

### References
* https://lists.apache.org/thread/ffrmkcwgr2lcz0f5nnnyswhpn3fytsvo


## Information Leakage Vulnerability ## { #CVE-2023-49068 }

CVE-2023-49068 [\[CVE json\]](./CVE-2023-49068.cve.json)

### Affected

* Apache DolphinScheduler before 3.2.1


### Description

Exposure of Sensitive Information to an Unauthorized Actor vulnerability in Apache DolphinScheduler.<p>This issue affects Apache DolphinScheduler: before 3.2.1.<br></p><p>Users are recommended to upgrade to version 3.2.1, which fixes the issue. At the time of disclosure of this advisory, this version has not yet been released. In the mean time, we recommend you make sure the logs are only available to trusted operators.<br></p>

### References
* https://github.com/apache/dolphinscheduler/pull/15192
* https://lists.apache.org/thread/jn6kr6mjdgtfgpxoq9j8q4pkfsq8zmpq


### Credits
* Y4tacker and 4ra1n from Y4secTeam (finder)


## Authenticated users could delete UDFs in resource center they were not authorized for ## { #CVE-2023-49620 }

CVE-2023-49620 [\[CVE json\]](./CVE-2023-49620.cve.json)

### Affected

* Apache DolphinScheduler from 2.0.0 before 3.1.0


### Description

Before DolphinScheduler version 3.1.0, the login user could delete UDF function in the resource center unauthorized (which almost used in sql task), with&nbsp;unauthorized&nbsp;access vulnerability (IDOR), but after version 3.1.0 we fixed this issue. We mark this cve as moderate level because it still requires user login to operate, please upgrade to version 3.1.0 to avoid this&nbsp;vulnerability

### References
* https://github.com/apache/dolphinscheduler/pull/10307
* https://lists.apache.org/thread/zm4t1ykj4cro1c8183q7y32z0yzfz8yj


### Credits
* Yuanheng Lab of zhongfu (finder)
