# Lecture on "Web Security" for the course "Web Application" at the University of Padova

This repository contains the material for the lecture on "Web Security" for the course "Web Application" at the University of Padova, held by Francesco L. De Faveri.


# Setup

## Docker

### Build the Docker Image - Linux & MacOS
To build the Docker image, move to the lab folder that you are interested in and run the following command:
```bash
sudo docker-compose build
```

Once the image is built, you can run the container with the following command:
```bash
sudo docker-compose up
```

When the compose is up, you must also modify the `/etc/hosts` (or `/private/etc/hosts` in MacOS) file on your machine to include the following line:
```
sudo nano /etc/hosts
```
Add the following lines:
- SQL Injection Lab:
    ```nano
        # SQL Injection Lab
        10.9.0.5        www.seed-server.com
    ```

- XSS Lab:
    ```nano
        # XSS Lab 
        10.9.0.5        www.seed-server.com
        10.9.0.5        www.example32a.com
        10.9.0.5        www.example32b.com
        10.9.0.5        www.example32c.com
        10.9.0.5        www.example60.com
        10.9.0.5        www.example70.com
    ```
- CSRF Lab:
    ```nano
        # CSRF Lab
        10.9.0.5        www.seed-server.com
        10.9.0.5        www.example32.com
        10.9.0.105      www.attacker32.com
    ```

Finally, when you are done with the lab, you can stop the container with the following command:
```bash
sudo docker-compose down
```

**Remark:** You'll need `root` permission to build and run the containers. 

### Build the Docker Image - Windows
Build, and run the containers as you usually do in your machine.

To modify the `/etc/hosts` file on Windows, follow:

1. Execute NotePad as Administrator
2. Select Open File (make sure to have `all types of format files` to open)
3. Open `C:\Windows\System32\drivers\etc\hosts`
4. Modify the file as described for Linux & MacOS



## Virtual Box
Go to the following link to download the VM image: https://drive.google.com/file/d/1l5WNoWdisWlNtBm_dXQ-inGeXyVjL0xc/view?usp=sharing

It downloads a zip folder containing the VM image and the README file. The README file contains the user and the password to access the VM.
The VM is a VirtualBox image. The VM is a Ubuntu 20.04 system and it is around 6.5GB.

You can import it into VirtualBox by following these steps:

1. Open VirtualBox.
2. Click on the "File" menu and select "Import".
3. Select the VM image file that you downloaded, and follow the instructions.
4. Start the VM and follow the instructions above for the Linux user.

# Lab 1: SQL Injection Attack

To start fresh use:

```bash
sudo rm -rf mysql_data
```

to restore the original data in the db.

## Description
SQL Injection is a code injection technique that exploits a vulnerability in a Web Application by inserting malicious SQL code into the input fields. This code manipulates the database, allowing the attacker to access, modify, or delete data.

## Tasks
1. Basic SQL Injection Attack: Entering without a password.
2. SQL Injection Attack: Changing the salary of the user.
3. SQL Injection Attack: Changing the salary of another user.

# Lab 2: Cross-Site Scripting (XSS) Attack

## Description
XSS (Cross-Site-Scripting) is a vulnerability frequently encountered in Web Applications, enabling attackers to insert harmful code, like JavaScript, into a victim's web browser. This code allows the attacker to steal the victim's credentials, such as session cookies. Exploiting XSS vulnerabilities bypasses the access control measures, like the same origin policy, implemented by browsers to safeguard these credentials.

## Tasks
1. Get familiar with the seed lab environment and the Mozilla HTTP Header Live extension.
2. Changing the victim's description.
3. XSS Attack: Becoming the victim's friend and propagate.

Bonus not shown in the lab:
1. XSS Attack: Self-propagating-attack to other users.

# Lab 3: CSRF Attack

## Description
A CSRF (Cross-Site Request Forgery) attack occurs when a user, who is logged into a trusted website, visits a malicious site. The malicious site then injects unauthorized HTTP requests into the user's session with the trusted site, leading to the execution of unwanted actions.

## Tasks
1. Get familiar with the seed lab environment and the Mozilla HTTP Header Live extension.
2. CSRF Attack: Change the description of the victim's profile.

# Credits
Original work proposed by Wenliang Du, Syracuse University - Original SeedLabs Project
Link: https://seedsecuritylabs.org/Labs_20.04/Web/

Modified version: Francesco L. De Faveri

