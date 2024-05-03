# Labs Presented during the Lecture "Web Security" of the course "Web Application" at the University of Padova - Prof. Nicola Ferro

# Lab 1: Cross-Site Scripting (XSS) Attack

## Description
XSS (Cross-Site-Scripting) is a vulnerability frequently encountered in Web Applications, enabling attackers to insert harmful code, like JavaScript, into a victim's web browser. This code allows the attacker to steal the victim's credentials, such as session cookies. Exploiting XSS vulnerabilities bypasses the access control measures, like the same origin policy, implemented by browsers to safeguard these credentials.

## Tasks
1. Get familiar with the seed lab environment and the Mozilla HTTP Header Live extension.
2. Print out the `cookie` value of a user of the Elgg WebApp.
3. XSS Attack: Becoming the victim's friend.

Bonus not shown in the lab:
1. XSS Attack: Self-propagating-attack to other users.

# Lab 2: CSRF Attack

## Description
A CSRF (Cross-Site Request Forgery) attack occurs when a user, who is logged into a trusted website, visits a malicious site. The malicious site then injects unauthorized HTTP requests into the user's session with the trusted site, leading to the execution of unwanted actions.

## Tasks
1. Get familiar with the seed lab environment and the Mozilla HTTP Header Live extension.
2. CSRF Attack: Change the description of the victim's profile.

# Lab 3: SQL Injection Attack

## Description
SQL Injection is a code injection technique that exploits a vulnerability in a Web Application by inserting malicious SQL code into the input fields. This code manipulates the database, allowing the attacker to access, modify, or delete data.

## Tasks
1. Basic SQL Injection Attack: Entering without a password.
2. SQL Injection Attack: Changing the salary of the user.
3. SQL Injection Attack: Changing the salary of another user.

# Credits
Wenliang Du, Syracuse University - Original SeedLabs Project
Link: https://seedsecuritylabs.org/Labs_20.04/Web/

