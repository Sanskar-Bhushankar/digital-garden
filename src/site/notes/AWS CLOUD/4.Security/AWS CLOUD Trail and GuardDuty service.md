---
{"dg-publish":true,"permalink":"/AWS CLOUD/4.Security/AWS CLOUD Trail and GuardDuty service/","created":"2024-12-13T17:48:39.337+05:30"}
---

one short security - [aws security - last min rev](../aws%20security%20-%20last%20min%20rev.md)

How cloud trail works
An activity happens in your account
cloud tril captures and records the activity which referred to as cloud trail event it contains details like
1. Who performed the request
2. when the event occured date,time of request
3. what the source Ip was
4. how request was made
5. which actions were performed
6. where the actions occured (in which region)
7. what the response was

> [!NOTE]
> ALL log files are stored as compressed files with a .gz extension

## cloud trail best practices

turn on cloud trail log file integrity validation
aggregate log files to single s3 bucket
ensure that cloudtrail isenabled across aws globally
restrict access to cloud trail s3 buckets
integrate with amazon cloudwatch



## Guard duty Detection

![](/img/user/AWS CLOUD/4.Security/attachments/Pasted image 20241213182126.png)

![](/img/user/AWS CLOUD/4.Security/attachments/Pasted image 20241213183121.png)