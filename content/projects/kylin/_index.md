---
title: Apache Kylin security advisories
description: Security information for Apache Kylin
layout: single
---

# Reporting

Do you want disclose a potential security issue for Apache Kylin? Send your report to the [Apache Security Team](mailto:security@apache.org).

# Advisories

This section is experimental: it provides advisories since 2023 and may lag behind the official CVE publications. If you have any feedback on how you would like this data to be provided, you are welcome to reach out on our public [mailinglist](/mailinglist) or privately on [security@apache.org](mailto:security@apache.org)
{.bg-warning}

## Improper Access Control to Streaming Coordinator & SSRF ## { #CVE-2021-27738 }

CVE-2021-27738 [\[CVE json\]](./CVE-2021-27738.cve.json)

### Affected

* Apache Kylin from Apache Kylin 3 before 3.1.2


### Description

All request mappings in `StreamingCoordinatorController.java` handling `/kylin/api/streaming_coordinator/*` REST API endpoints did not include any security checks, which allowed an unauthenticated user to issue arbitrary requests, such as assigning/unassigning of streaming cubes, creation/modification and deletion of replica sets, to the Kylin Coordinator.

For endpoints accepting node details in HTTP message body, unauthenticated (but limited) server-side request forgery (SSRF) can be achieved.

This issue affects Apache Kylin Apache Kylin 3 versions prior to 3.1.2.

### References
* https://lists.apache.org/thread/vkohh0to2vzwymyb2x13fszs3cs3vd70


### Credits
* Wei Lin Ngo <ngo.weilin@starlabs.sg>


## Apache Kylin unsafe class loading ## { #CVE-2021-31522 }

CVE-2021-31522 [\[CVE json\]](./CVE-2021-31522.cve.json)

### Affected

* Apache Kylin from Apache Kylin 2 through 2.6.6
* Apache Kylin from Apache Kylin 3 through 3.1.2
* Apache Kylin from Apache Kylin 4 through 4.0.0


### Description

Kylin can receive user input and load any class through Class.forName(...).
This issue affects Apache Kylin 2 version 2.6.6 and prior versions; Apache Kylin 3 version 3.1.2 and prior versions; Apache Kylin 4 version 4.0.0 and prior versions.

### References
* https://lists.apache.org/thread/hh5crx3yr701zd8wtpqo1mww2rlkvznw


### Credits
* bo yu <forhaby0@gmail.com>


## Mysql JDBC Connector Deserialize RCE ## { #CVE-2021-36774 }

CVE-2021-36774 [\[CVE json\]](./CVE-2021-36774.cve.json)

### Affected

* Apache Kylin from Apache Kylin 2 through 2.6.6
* Apache Kylin from Apache Kylin 3 through 3.1.2


### Description

Apache Kylin allows users to read data from other database systems using JDBC. The MySQL JDBC driver supports certain properties, which, if left unmitigated, can allow an attacker to execute arbitrary code from a hacker-controlled malicious MySQL server within Kylin server processes. 
This issue affects Apache Kylin 2 version 2.6.6 and prior versions; Apache Kylin 3 version 3.1.2 and prior versions.

### References
* https://lists.apache.org/thread/lchpcvoolc6w8zc6vo1wstk8zbfqv2ow


### Credits
* jinchen sheng <jincsheng@gmail.com>


## Command injection ## { #CVE-2021-45456 }

CVE-2021-45456 [\[CVE json\]](./CVE-2021-45456.cve.json)

### Affected

* Apache Kylin at Apache Kylin 4 4.0.0


### Description

Apache kylin checks the legitimacy of the project before executing some commands with the project name passed in by the user. There is a mismatch between what is being checked and what is being used as the shell command argument in DiagnosisService. This may cause an illegal project name to pass the check and perform the following steps, resulting in a command injection vulnerability.
This issue affects Apache Kylin 4.0.0.

### References
* https://lists.apache.org/thread/70fkf9w1swt2cqdcz13rwfjvblw1fcpf


### Credits
* Alvaro Munoz <pwntester@github.com>


## Overly broad CORS configuration  ## { #CVE-2021-45457 }

CVE-2021-45457 [\[CVE json\]](./CVE-2021-45457.cve.json)

### Affected

* Apache Kylin from Apache Kylin 2 through 2.6.6
* Apache Kylin from Apache Kylin 3 through 3.1.2
* Apache Kylin from Apache Kylin 4 through 4.0.0


### Description

In Apache Kylin, Cross-origin requests with credentials are allowed to be sent from any origin.

This issue affects Apache Kylin 2 version 2.6.6 and prior versions; Apache Kylin 3 version 3.1.2 and prior versions; Apache Kylin 4 version 4.0.0 and prior versions.

### References
* https://lists.apache.org/thread/rzv4mq58okwj1n88lry82ol2wwm57q1m


### Credits
* Alvaro Munoz <pwntester@github.com>


## Hardcoded credentials ## { #CVE-2021-45458 }

CVE-2021-45458 [\[CVE json\]](./CVE-2021-45458.cve.json)

### Affected

* Apache Kylin from Apache Kylin 2 through 2.6.6
* Apache Kylin from Apache Kylin 3 through 3.1.2
* Apache Kylin from Apache Kylin 4 through 4.0.0


### Description

Apache Kylin provides encryption classes PasswordPlaceholderConfigurer to help users encrypt their passwords. In the encryption algorithm used by this encryption class, the cipher is initialized with a hardcoded key and IV.  If users use class PasswordPlaceholderConfigurer to encrypt their password and configure it into kylin's configuration file, there is a risk that the password may be decrypted.
This issue affects Apache Kylin 2 version 2.6.6 and prior versions; Apache Kylin 3 version 3.1.2 and prior versions; Apache Kylin 4 version 4.0.0 and prior versions.

### References
* https://lists.apache.org/thread/oof215qz188k16vhlo97cm1jksxdowfy


### Credits
* Alvaro Munoz <pwntester@github.com>


## Apache Kylin prior to 4.0.2 allows command injection when the configuration overwrites function overwrites system parameters ## { #CVE-2022-24697 }

CVE-2022-24697 [\[CVE json\]](./CVE-2022-24697.cve.json)

### Affected

* Apache Kylin from Apache Kylin 2 before 2.6.6
* Apache Kylin from Apache Kylin 3 through 3.1.2
* Apache Kylin from Apache Kylin 4 through 4.0.1


### Description

Kylin's cube designer function has a command injection vulnerability when overwriting system parameters in the configuration overwrites menu. RCE can be implemented by closing the single quotation marks around the parameter value of “-- conf=” to inject any operating system command into the command line parameters. This vulnerability affects Kylin 2 version 2.6.5 and earlier, Kylin 3 version 3.1.2 and earlier, and Kylin 4 version 4.0.1 and earlier.

### References
* https://lists.apache.org/thread/07mnn9c7o314wrhrwjr10w9j5s82voj4


### Credits
* Kylin Team would like to thanks Kai Zhao of ToTU Secruity Team.


## Command injection by Useless configuration ## { #CVE-2022-43396 }

CVE-2022-43396 [\[CVE json\]](./CVE-2022-43396.cve.json)

### Affected

* Apache Kylin from Apache Kylin 4 through 4.0.2


### Description

In the fix for CVE-2022-24697, a blacklist is used to filter user input commands. But there is a risk of being bypassed. The user can control the command by controlling the&nbsp;kylin.engine.spark-cmd&nbsp;parameter of conf.

### References
* https://lists.apache.org/thread/ob2ks04zl5ms0r44cd74y1xdl1rzfd1r


### Credits
* Yasax1 Li <pp1ove.lit@gmail.com> (finder)


## Command injection by Diagnosis Controller ## { #CVE-2022-44621 }

CVE-2022-44621 [\[CVE json\]](./CVE-2022-44621.cve.json)

### Affected

* Apache Kylin from Apache Kylin 4  through 4.0.2


### Description

Diagnosis Controller miss parameter validation, so user may attacked by command injection via HTTP Request.

### References
* https://lists.apache.org/thread/7ctchj24dofgsj9g1rg1245cms9myb34


### Credits
* Messy God <godimessy@gmail.com> (finder)
