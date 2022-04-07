# Weeks 7 & 8 - WordPress vs Kali

Time Spent: 6 hours spent in total

> Objective: Find, analyze, recreate, and document three vulnerabilities affecting an old version of WordPress

## Report

### 1. WordPress <= 4.2 - Unauthenticated Stored Cross-Site Scripting (XSS)
	- Summary:An unauthenticated attacker can inject JavaScript in WordPress comments. The script is triggered when the comment is viewed.
	- Vulnerability Types: XSS
	- Tested in version: 4.2
	- Fixed in Version: 4.2.1
	- GIF Walkthrough: 
		<img src="Ass7-1.gif">
	- Steps to recreate: 
    		- From the main page click on the Hello World post
    		- Scroll to the comment form and fill the fields
    		- In the comment content field paste:
            		<a title='x onmouseover=alert(unescape(/hello%20world/.source)) 
            		style=position:absolute;left:0;top:0;width:5000px;height:5000px  
            		AAAAA...[64kb]..AAA'></a>
    		- Post it 
    		- Login as admin and approve
    		- Logout
    		- Visit the page again with your comment posted
	- Affected source code: 

### 2. 
	- Summary:
	- Vulnerability Types:
	- Tested in version: 
	- Fixed in Version: 
	- GIF Walkthrough: 
	- Steps to recreate: 
	- Affected source code: 

### 3. 
	- Summary:
	- Vulnerability Types:
	- Tested in version: 
	- Fixed in Version: 
	- GIF Walkthrough: 
	- Steps to recreate: 
	- Affected source code: 
