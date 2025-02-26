---
title: Apache AGE security advisories
description: Security information for Apache AGE
layout: single
---

# Reporting

Do you want disclose a potential security issue for Apache AGE? Send your report to the [Apache Security Team](mailto:security@apache.org).

# Advisories

This section is experimental: it provides advisories since 2023 and may lag behind the official CVE publications. If you have any feedback on how you would like this data to be provided, you are welcome to reach out on our public [mailinglist](/mailinglist) or privately on [security@apache.org](mailto:security@apache.org)
{.bg-warning}

## Python and Golang drivers allow data manipulation and exposure due to SQL injection ## { #CVE-2022-45786 }

CVE-2022-45786 [\[CVE json\]](./CVE-2022-45786.cve.json)

### Affected

* Apache AGE from Apache AGE for PostgreSQL 12 through 1.1.0
* Apache AGE from Apache AGE for PostgreSQL 11 through 1.1.0


### Description

There are issues with the AGE drivers for Golang and Python that enable SQL injections to occur. This impacts AGE for PostgreSQL 11 &amp; AGE for PostgreSQL 12, all versions up-to-and-including 1.1.0, when using those drivers.<br><br>The fix is to update to the latest Golang and Python drivers in addition to the latest version of AGE that is used for PostgreSQL 11 or&nbsp; PostgreSQL 12.<br><br>The update of AGE will add a new function to enable parameterization of the cypher() function, which, in conjunction with the driver updates, will resolve this issue.<br><br><u>Background (for those who want more information):</u><br><br>After thoroughly researching this issue, we found that due to the nature of the cypher() function, it was not easy to parameterize the values passed into it. This enabled SQL injections, if the developer of the driver wasn't careful. The developer of the Golang and Pyton drivers didn't fully utilize parameterization, likely because of this, thus enabling SQL injections.<br><br>The obvious fix to this issue is to use parameterization in the drivers for all PG SQL queries. However, parameterizing all PG queries is complicated by the fact that the cypher() function call itself cannot be parameterized directly, as it isn't a real function. At least, not the parameters that would take the graph name and cypher query.<br><br>The reason the cypher() function cannot have those values parameterized is because the function is a placeholder and never actually runs. The cypher() function node, created by PG in the query tree, is transformed and replaced with a query tree for the actual cypher query during the analyze phase. The problem is that parameters - that would be passed in and that the cypher() function transform needs to be resolved - are only resolved in the execution phase, which is much later. Since the transform of the cypher() function needs to know the graph name and cypher query prior to execution, they can't be passed as parameters.<br><br>The fix that we are testing right now, and are proposing to use, is to create a function that will be called prior to the execution of the cypher() function transform. This new function will allow values to be passed as parameters for the graph name and cypher query. As this command will be executed prior to the cypher() function transform, its values will be resolved. These values can then be cached for the immediately following cypher() function transform to use. As added features, the cached values will store the calling session's pid, for validation. And, the cypher() function transform will clear this cached information after function invocation, regardless of whether it was used.<br><br>This method will allow the parameterizing of the cypher() function indirectly and provide a way to lock out SQL injection attacks.

### References
* https://lists.apache.org/thread/of8x0gt5d2vfrm5ksxw55bwn2849ck1w
