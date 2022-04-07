# Weeks 7 & 8 - WordPress vs Kali

Time Spent: 6 hours spent in total

> Objective: Find, analyze, recreate, and document three vulnerabilities affecting an old version of WordPress

## Report

### 1. WordPress <= 4.2 - Unauthenticated Stored Cross-Site Scripting (XSS)
	- Summary:An unauthenticated attacker can inject JavaScript in WordPress comments. The script is triggered when the comment is viewed.
	- Vulnerability Types: XSS
	- Tested in version: 4.2
	- Fixed in Version: 4.2.1
	- GIF Walkthrough: File Ass7-1.gif and Ass7-1-2.gif
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

### 2. WordPress 2.5-4.6 - Authenticated Stored Cross-Site Scripting (XSS)
	- Summary: Authenticated Cross Site Scripting through a post
	- Vulnerability Types: XSS
	- Tested in version: 4.2
	- Fixed in Version: 4.2.10
	- GIF Walkthrough: Ass7-2.gif and Ass7-2-2.gif
	- Steps to recreate: 
		- Login to WordPress as an admin
		- Create a post
		- Upload file with the file name: <img src=a onerror=alert(document.cookie)>.jpg
		- Whenever the file is opened, the exploit is run.

### 3. WordPress 4.0-4.7.2 - Authenticated Stored Cross-Site Scripting (XSS) in YouTube URL Embeds
	- Summary: You can execute js through Youtube embeds 
	- Vulnerability Types: XSS
	- Tested in version: 4.2
	- Fixed in Version: 4.2.13
	- GIF Walkthrough: Ass7-3.gif
	- Steps to recreate: 
		- Login as admin
		- Create new post
		- Paste this embedded link in the text box under the text tab: ([embed src='https://youtube.com/embed/12345\x3csvg onload=alert(1)\x3e'][/embed]) 
