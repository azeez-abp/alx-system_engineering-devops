# Postmortem Report

## 404 Error while accessing a given URL
![](./404.jpg)


### Incident report for [404 error / Site Not found](https://github.com/azeez-abp/alx-system_engineering-devops/blob/master/0x17-web_stack_debugging_3/0-strace_is_your_friend.pp)

#### Issue Summary

On May 1st, 2024 at midnight the endpoint access went down resulting in 404 error for anyone trying to access the rendpoint on the website. Background on the server being based on a Word-press. The issue was detected on moitoring side. The issue is caused by missing script file.

#### Timeline

- **00:00 GMT** - 400 error for anyone trying to access the website
- **00:05 GMT** - Ensuring Apache and MySQL are up and running.
- **00:10 GMT** - The website did not load  which on background check revealed that the the file responsibble for handling the request is missing.
- **00:12 GMT** - After quick restart to Apache server returned a status of 200 and OK while trying to curl the website.
- **00:18 GMT** - Reviewing error logs to check where the error might be coming from.
- **00:25 GMT** - Investigate the file directory to look for the file that handle the 
- **00:29 GMT** - Detection that file extension is named badly form .php  to .phphp 
- **00:31 GMT** - Write puppet script that automate the fixing of the file 

#### Root Cause and Resolution

The issue is caused by bad file extension. The issue was fiexed by writting a puppet script that automaye the fixing of the extension

#### Corrective and Preventive Measures
- Every function on in function must be tested with unit test
- Before deployment, the test must be run
- All servers and sites should have error logging turned on to easily identify errors if anything goes wrong.
- All servers and sites should be tested locally before deploying on a multi-server setup this will result in correcting errors before going live resulting in less fixing time if site goes down.
