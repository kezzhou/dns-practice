# Domain Name Service - Practice
HHA 504 // Week 10 // Assignment 8

## Description:

In this repository, we practice linking a purchased domain name to an existing IP address. First, we must build a flask app to run remotely. In this case, we simply borrow a previously built flask app from a previous project: flask-with-db. The host and port parameters in our flask app remain unchaged: host:0.0.0.0 and port:80. After standing up our vm, running the app, and accessing it on a web browser via its public IP seamlessly, we are ready to transition to the next step.

Now we must acquire a domain name. We have purchased the domain name: "zhoukevin.tech" from get.tech.com. In our case, we are able to acquire this domain for a year free of charge by linking our Github accounts with student statuses. Then, we navigate to get.tech.com's Control Panel, where we can manage our domain name. We can then navigate to DNS Management > Manage DNS > A Records. When we click on Manage DNS, we have several options: A Records, AAAA Records, MX Records, CNAME Records, NS Records, etc. Between A Records and AAAA Records, we'll want to go with A Records as we'll be utilizing IPV4. Luckily, the Manage DNS menu opens to A Records by default. We can then click Add A Record. There are three fields modifiable to us: Name, Destination IPV4 Address, and Time To Load (TTL). For our name, we can simply leave it blank or add an '@' symbol to signify a wildcard, enabling zhoukevin.tech itself to access the destination IP. For our Destination IPV4 Address, we can populate this with our Azure VM IP Address, which is 20.106.91.67. TTL we leave as 7200, as this is the minimum TTL value accepted by get.tech.com. Now that these fields are completed, we can click add record. Granted that the VM is running our flask app with no 404s, we are able to access the app from zhoukevin.tech.


## Resources:

[Source Code for Project](https://github.com/kezzhou/flask-with-db)

[.Tech Domains](https://get.tech/)

[Acquire a Domain for a Year for Free](https://get.tech/github-student-developer-pack)

## Requirements:

- VS Code/Python Program of Choice
- Chrome/Safari/Browser of Choice
- Flask app script
- Azure/GCP/Virtual Machine Service of Choice

For package requirements and dependencies, please refer to requirements.txt and the notes section below.

## Notes:

Populating the Name field when adding an A Record with '@' or leaving it blank creates a loading error when trying to access our flask app via "zhoukevin.tech." However, when we populate the Name field with an alternative value, such as "api.zhoukevin.tech" or "db.zhoukevin.tech" will allow us to access the app through that url.