# Chemistry: Easy Machine Walkthrough for Beginners

URL: https://app.hackthebox.com/machines/Chemistry

## Machine Overview

## Tools

- Nmap 


### Enumeration

In the first step, I recommend running Nmap to identify open ports on the provided HTB IP address. This initial scan will reveal accesible ports, giving us a clearer picture of the services that might be running on the target machine. By examining these services, we can assess potential entry points and gain isight into the target's configuration and vulnerabilities.

### NMAP Result

```
sudo nmap -sS -sC  10.10.11.38

Starting Nmap 7.94SVN ( https://nmap.org ) at 2024-11-02 16:38 CST
Nmap scan report for 10.10.11.38
Host is up (0.15s latency).
Not shown: 998 closed tcp ports (reset)
PORT     STATE SERVICE
22/tcp   open  ssh
| ssh-hostkey: 
|   3072 b6:fc:20:ae:9d:1d:45:1d:0b:ce:d9:d0:20:f2:6f:dc (RSA)
|   256 f1:ae:1c:3e:1d:ea:55:44:6c:2f:f2:56:8d:62:3c:2b (ECDSA)
|_  256 94:42:1b:78:f2:51:87:07:3e:97:26:c9:a2:5c:0a:26 (ED25519)
5000/tcp open  upnp

Nmap done: 1 IP address (1 host up) scanned in 10.29 seconds
```

As observed, the port scan reveals two open ports: 22 and 5000. The first port, 22, is typically used for SSH services. However, without valid credentials, we currently lack access to this service.

The second port, 5000, is less immediately identifiable. To investigate further, we can attempt to access it via a web browser at http://10.10.11.38:5000/. This may reveal a web-based service or application running on the target, which could offer additional information or potential entry points for exploitation.

### Web Service Discovery
![alt text](images/1.png)

Upon accessing port 5000, we discovered a web application titled "Chemistry CIF Analyzer." The landing page displays the message:

- "Welcome to the Chemistry CIF Analyzer. This tool allows you to upload a CIF (Crystallographic Information File) and analyze the structural data contained within."

In addition to this functionality, the page also features two buttons for Login and Register. This suggests that user authentication may be a part of the application’s process.

This message provides valuable insight into the functionality of the application, indicating that it enables users to upload and analyze CIF files. Understanding this feature will be crucial in navigating the challenges associated with this machine. Given the nature of file uploads and user authentication, it may also present opportunities for exploitation, which we will explore further.

![alt text](images/2.png)

When clicking the Login button, we are presented with a login form. However, before attempting an SQL injection attack, it’s worth noting the message displayed above the form: "Don't have an account? Register here."

This prompts us to consider registering for an account first, as it may provide additional access or information that could be beneficial for our exploration of the application.

![alt text](images/3.png)

After clicking "Register here," we are presented with a form requiring a username and password for account creation. To proceed, we will enter the following test credentials:

    Username: test
    Password: test

Once the information is filled out, we will submit the form to create the account and then attempt to log in with the same credentials.

![alt text](images/4.png)
