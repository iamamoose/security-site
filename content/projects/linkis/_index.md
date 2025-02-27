---
title: Apache Linkis security advisories
description: Security information for Apache Linkis
layout: single
---

# Reporting

Do you want disclose a potential security issue for Apache Linkis? Send your report to the [Apache Security Team](mailto:security@apache.org).

# Advisories

This section is experimental: it provides advisories since 2023 and may lag behind the official CVE publications. If you have any feedback on how you would like this data to be provided, you are welcome to reach out on our public [mailinglist](/mailinglist) or privately on [security@apache.org](mailto:security@apache.org)
{.bg-warning}

## The Apache Linkis JDBC EngineConn module has a RCE Vulnerability ## { #CVE-2022-39944 }

CVE-2022-39944 [\[CVE json\]](./CVE-2022-39944.cve.json)

### Affected

* Apache Linkis from Apache Linkis through 1.2.0


### Description

In Apache Linkis <=1.2.0 when used with the MySQL Connector/J, a deserialization vulnerability with possible remote code execution impact exists when an attacker has write access to a database and configures a JDBC EC with a MySQL data source and malicious parameters. Therefore, the parameters in the jdbc url should be blacklisted. Versions of Apache Linkis <= 1.2.0 will be affected, We recommend users to update to 1.3.0.


### References
* https://lists.apache.org/thread/rxytj48q17304snonjtyt5lnlw64gccc


### Credits
* This issue was discovered by 4ra1n and zac from ZAC Security Team


## The DatasourceManager module has a serialization attack vulnerability ## { #CVE-2022-44645 }

CVE-2022-44645 [\[CVE json\]](./CVE-2022-44645.cve.json)

### Affected

* Apache Linkis (incubating) through 1.3.0


### Description



In Apache Linkis &lt;=1.3.0 when used with the MySQL Connector/J in the data source module, a deserialization vulnerability with possible remote code execution impact exists when an attacker has to write access to a database and configures new data source with a MySQL data source and malicious parameters. Therefore, the parameters in the JDBC URL should be blacklisted. Versions of Apache Linkis &lt;= 1.3.0 will be affected.<br><br>We recommend users upgrade the version of Linkis to version 1.3.1.<br>

### References
* https://lists.apache.org/thread/zlcfmvt65blqc4n6fxypg6f0ns8fqfz4


### Credits
* Tian Xin WU (Bearcat) , Vulnerability Researcher at Numen Cyber ​​​​Labs, Singapore. (reporter)
* Department of Cyber Security Research (Jumbo, Unc1e) (remediation developer)
* s3gundo of Hundsun Tech  (remediation developer)


## The DatasourceManager module has a Local File Read Vulnerability ## { #CVE-2022-44644 }

CVE-2022-44644 [\[CVE json\]](./CVE-2022-44644.cve.json)

### Affected

* Apache Linkis (incubating) before 1.3.1


### Description

In Apache Linkis &lt;=1.3.0 when used with the MySQL Connector/J in the data source module, an authenticated attacker could read arbitrary local files by connecting a rogue MySQL server, By adding allowLoadLocalInfile to true in the JDBC parameter. Therefore, the parameters in the JDBC URL should be blacklisted. Versions of Apache Linkis &lt;= 1.3.0 will be affected.&nbsp;<br><br><span style="background-color: rgb(255, 255, 255);">We recommend users upgrade the version of Linkis to version 1.3.1</span><br>

### References
* https://lists.apache.org/thread/hwq9ytq6y1kdh9lz5znptkcrdll9x85h


### Credits
* Department of Cyber Security Research (Jumbo, Unc1e), Beijing Zhiqian Technology Co., LTD (reporter)
* s3gundo of Hundsun Tech  (reporter)


## Apache Linkis publicsercice module unrestricted upload of file ## { #CVE-2023-27602 }

CVE-2023-27602 [\[CVE json\]](./CVE-2023-27602.cve.json)

### Affected

* Apache Linkis through 1.3.1


### Description



<span style="background-color: rgb(255, 255, 255);">

In Apache Linkis &lt;=1.3.1, The PublicService module uploads&nbsp;</span><span style="background-color: rgb(255, 255, 255);">files without restrictions on the path to the uploaded&nbsp;</span><span style="background-color: rgb(255, 255, 255);">files, and file types.<br>

We recommend users upgrade the version of Linkis to version 1.3.2.&nbsp;<br></span>

### References
* https://lists.apache.org/thread/wt70jfc0yfs6s5g0wg5dr5klnc48nsp1


### Credits
* Laihan (reporter)


## Apache Linkis Mangaer module engineConn material upload exists Zip Slip issue ## { #CVE-2023-27603 }

CVE-2023-27603 [\[CVE json\]](./CVE-2023-27603.cve.json)

### Affected

* Apache Linkis through 1.3.1


### Description



<span style="background-color: rgb(255, 255, 255);">

In Apache Linkis &lt;=1.3.1, due to the Manager module engineConn material upload does not check the zip path,&nbsp;This is a Zip Slip issue, which will lead to a&nbsp;</span><span style="background-color: rgb(255, 255, 255);">potential RCE vulnerability.<br>

We recommend users upgrade the version of Linkis to version 1.3.2.

</span>



### References
* https://lists.apache.org/thread/6n1vlvnyn441rm02zdqc0wnpckj8ltn8
* https://www.openwall.com/lists/oss-security/2023/04/10/2


### Credits
* 4ra1n (reporter)


## Apache Linkis gateway module token authentication bypass ## { #CVE-2023-27987 }

CVE-2023-27987 [\[CVE json\]](./CVE-2023-27987.cve.json)

### Affected

* Apache Linkis through 1.3.1


### Description



In Apache Linkis &lt;=1.3.1,&nbsp;due to the default token generated by Linkis Gateway deployment being too simple, it is easy for attackers to obtain the default token for the attack.&nbsp;Generation rules should add random values.<br>



We recommend users upgrade the version of Linkis to version 1.3.2 And modify the default token value. You can refer to Token authorization[1]<br><a target="_blank" rel="nofollow" href="https://linkis.apache.org/docs/latest/auth/token">https://linkis.apache.org/docs/latest/auth/token</a>



<br>

### References
* https://lists.apache.org/thread/3cr1cz3210wzwngldwrqzm43vwhghp0p
* https://www.openwall.com/lists/oss-security/2023/04/10/3


### Credits
* Laihan (reporter)


## Apache Linkis JDBC EngineCon  has a deserialization command execution ## { #CVE-2023-29215 }

CVE-2023-29215 [\[CVE json\]](./CVE-2023-29215.cve.json)

### Affected

* Apache Linkis through 1.3.1


### Description

In Apache Linkis &lt;=1.3.1, due to the lack of effective filtering
of parameters, an attacker configuring malicious Mysql JDBC parameters in JDBC EengineConn Module will trigger a
deserialization vulnerability and eventually lead to remote code execution. Therefore, the parameters in the Mysql JDBC URL should be blacklisted. Versions of Apache Linkis &lt;= 1.3.0 will be affected.<br>We recommend users upgrade the version of Linkis to version 1.3.2.

<br>

### References
* https://lists.apache.org/thread/o682wz1ggq491ybvjwokxvcdtnzo76ls


### Credits
* sw0rd1ight (reporter)


## Apache Linkis DatasourceManager module has a deserialization command execution ## { #CVE-2023-29216 }

CVE-2023-29216 [\[CVE json\]](./CVE-2023-29216.cve.json)

### Affected

* Apache Linkis through 1.3.1


### Description



In Apache Linkis &lt;=1.3.1, because the parameters are not
effectively filtered, the attacker uses the MySQL data source and malicious parameters to
configure a new data source to trigger a deserialization vulnerability, eventually leading to
remote code execution.<br> Versions of Apache Linkis &lt;= 1.3.0 will be affected.<br>We recommend users upgrade the version of Linkis to version 1.3.2.

<br>

### References
* https://lists.apache.org/thread/18vv0m32oy51nzk8tbz13qdl5569y55l


### Credits
* sw0rd1ight (reporter)
