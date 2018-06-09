# Updates

- Two page can look the same with different vulnerabilities (gluetrash)
- Do we need to write impact and remediation in the report? 
  - Because it is an exam your report can be shorter than usual, but if you have the time write something for those sections
- “Does report have to include recon like break 1?”
  - You can write a little section about what you did to find the domains, but don’t go overboard and stress
- Do try to submit your report only once, that makes it easier for us :)
- “Any loss of marks by getting the flag by an unintended/worse than expected solution?”
  - No, as long as you can provide evidence that you got the flag via your payload then that’s fine (screenshots help if we cant reproduce it)
- Write up as much as you can - we will try and give out partial marks where we can

# General
- Content covered will include Weeks 1 to 10
- There is **no late penalty** for the exam, if you fail to submit before the deadline you will receive a mark of **0**

## Rules
- Any violation, either deliberate or accidental, of these rules or of the spirit of these rules will be considered academic misconduct.
- You are not to get any help from anyone on the exam. You should not talk to anyone else about the exam from the time you receive the full details until after the exam ends.
- Communication and collusion is prohibited as per regular exam rules.

## Supplementary

As per the course outline:

> **Supplementary exams** will only be awarded in well justified cases, in accordance with School policy for Special Consideration, **not** as a second chance for poorly performing students. In particular, it is unlikely that a supplementary will be awarded to students who have actually sat the proper exam. **Make up your mind whether or not you are sick before attempting the exam!**

If you are sick and do not wish to sit the exams, email [cs6443@cse.unsw.edu.au](mailto:cs6443@cse.unsw.edu.au) **BEFORE** the start of Exam 1 - Break (10:00 08/06/18). Otherwise, you agree to sitting both Exam 1 and Exam 2.

# Exam 1 - Break (6443 and 6843)

**Date**: 10:00 08/06/18 - 09:30 09/06/18

**Total Duration**: 24 hours

**Approximate time to complete**: 3-4 hours. Including recon

## Structure
1. At the beginning of the 24 hours you will get given a target scope, for example: `*.exam.ns.agency`
2. Use you recon skills to find 5 subdomains
    - 3 easy domains
    - 2 slightly harder domains (requiring permutation, for example: `something-qa.exam.ns.agency`
3. There is 1 vulnerability per website, hack each site and retrieve the flag
4. Write up each vulnerability as you would for a break assignment and submit one report.

You will be marked according to the same criteria you are marked on for a break assignment report except a leaner more 'bug bounty' style report is acceptable given exam conditions.

**The vulnerability classes examined will be the following:**

1 XSS

1 SQLi

1 Authorisation/IDOR

1 Authentication

1 Server Side
 
**Exam notification**

- XSS Flags are in the admin cookie. Please steal. There will be a bot to retrieve your request or payload (depending on the challenge).
- If you're unable to find the flag for a SQLi challenge, try checking table `trash` column `content`
- LFI/Server side attack flags are in a file on the filesystem called /flag
- If you're unable to find a flag for an IDOR challenge, try checking a user/account/post with id `9447`
- Account/authentication flaws will be in an account called 'admin' with id = 1

- For the auth challenge, here are two test accounts you can use:
```
username: guest
password: guest
secret_a: unsw
```
```
username: azured
password: hunter2
secret_a: *******
```

## Recommended Practice

Previous weeks exercises. (All should be presently live). 

## Submission

Submission will be through the Bugcrowd platform.
 
When submitting a report you will be asked to fill in a number of details, here is the naming convention we want to you to stick with:

` ziD - 6443 Exam Break`

If there are difficulties submitting through Bugcrowd and the deadline is fast approaching, email your submission to [cs6443@cse.unsw.edu.au](mailto:cs6443@cse.unsw.edu.au) using the same naming convention.

# Exam 2 - Build (6443 only)

**Date**: 10:00 09/06/18 - 09:30 10/06/18

**Total duration**: 24 hours

**Approximate time to complete**: 3-4 hours

## Structure
1. At the beginning of the 24 hours you get given the source code for the 5 targets you found during the break exam
2. You must write code to fix the vulnerabilities and pass the unit tests
3. Submit your code at the end

You will be marked by auto tests similar to each build assignment.
 
We recommend you study how to remediate the vulnerability classes assessed in the break exam, specifically how the recommended code patterns in Python.

**Exam Notifications**

1. When patching the app it still has to remain functional. You shouldn't for example, stop users from posting updates just because they used special characters. Make the existing functionality safe to use - following the remediation techniques we have learnt over the semester.

2. You don't have to comment your code, but it would be of help for us to see your thought pattern and the reasoning behind your code.

3. If you find some part of the application which you think shouldn't exist because it is a security flaw - you can remove it so long as you provide a good argument as to why removing it would be better for the security of the site.

4. Do not include `venv` or any other working files in your diff submission. Only create a diff with the changes that are required to patch the vulns, otherwise your diff will be very large.

## Recommended Practice

Revise common code patterns for Flask that introduce vulnerabilities

## Submission

Submission details in the code repo README.md

# Exam 2 - Extended Break (6843 only)

The extended Break exam will follow the same structure as the regular break exam except with different classes of vulnerabilities.
 
**The vulnerability classes examined will be the following:**

XSS

CSRF

XXE

SSRF

SSTI

Sessions & Authentication
 
**Additional Notes**

You may be required to chain vulnerabilities together to acquire the flag.

**Exam notification**

There are only 4 hosts

## Submission

Submission will be through the Bugcrowd platform.
 
When submitting a report you will be asked to fill in a number of details, here is the naming convention we want to you to stick with:

`ziD - 6843 Exam Break`
 
If there are difficulties submitting through Bugcrowd and the deadline is fast approaching, email your submission to [cs6443@cse.unsw.edu.au](mailto:cs6443@cse.unsw.edu.au) using the same naming convention.
