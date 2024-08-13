# ⭐️Goals
* Starting point if you want to grind, but aren't sure where to start
* Start a good foundation in the three main pentesting areas (web, linux, windows)
* Learn how to research and grow on your own
* Learn when to ask for help/look for a writeup or hint
# 📝Note Taking
This is quite literally the most import thing you can take away from this document. Taking notes on techniques, tactics, and procedures (TTPs) is your new religion. All hail your notes 🙏
* As you you go through these labs and start getting hands on experience, make sure to take notes on TTPs as you come across them
* These in no way need to be complete right off the bat, they should be living documents that you update as you learn
* Stick to a good note taking tool
	* I like obsidian because I can format things nicely and publish them to my github :)
# 🌐Web
Portswigger will be your bestie. Learn her, love her, cherish her 😍
* Cross site scripting
	* https://portswigger.net/web-security/cross-site-scripting/reflected/lab-html-context-nothing-encoded
	* https://portswigger.net/web-security/cross-site-scripting/contexts/lab-href-attribute-double-quotes-html-encoded
* LFI/RFI
	* https://portswigger.net/web-security/file-path-traversal/lab-simple
	* https://portswigger.net/web-security/file-path-traversal/lab-absolute-path-bypass
* SQLi
	* https://portswigger.net/web-security/sql-injection/lab-login-bypass
	* https://portswigger.net/web-security/sql-injection/lab-retrieve-hidden-data
	* https://portswigger.net/web-security/sql-injection/union-attacks/lab-determine-number-of-columns
	* https://portswigger.net/web-security/sql-injection/union-attacks/lab-retrieve-data-from-other-tables
	* https://portswigger.net/web-security/sql-injection/union-attacks/lab-retrieve-multiple-values-in-single-column
	* https://portswigger.net/web-security/sql-injection/blind/lab-conditional-responses
	* https://portswigger.net/web-security/sql-injection/blind/lab-time-delays
	* https://portswigger.net/web-security/sql-injection/blind/lab-out-of-band-data-exfiltration
	* https://portswigger.net/web-security/sql-injection/lab-sql-injection-with-filter-bypass-via-xml-encoding
* SSRF
	* https://portswigger.net/web-security/ssrf/lab-basic-ssrf-against-localhost
	* https://portswigger.net/web-security/ssrf/lab-basic-ssrf-against-backend-system
* Access Control
	* https://portswigger.net/web-security/access-control/lab-unprotected-admin-functionality
	* https://portswigger.net/web-security/access-control/lab-user-role-can-be-modified-in-user-profile
	* https://portswigger.net/web-security/access-control/lab-insecure-direct-object-references
	* https://portswigger.net/web-security/access-control/lab-referer-based-access-control
* Authentication
	* https://portswigger.net/web-security/authentication/password-based/lab-username-enumeration-via-different-responses
	* https://portswigger.net/web-security/authentication/multi-factor/lab-2fa-simple-bypass
	* https://portswigger.net/web-security/authentication/other-mechanisms/lab-password-reset-broken-logic
* Logic Issues
	* https://portswigger.net/web-security/logic-flaws/examples/lab-logic-flaws-excessive-trust-in-client-side-controls
	* https://portswigger.net/web-security/logic-flaws/examples/lab-logic-flaws-inconsistent-handling-of-exceptional-input
	* https://portswigger.net/web-security/logic-flaws/examples/lab-logic-flaws-infinite-money
* Request Smuggling
	* https://portswigger.net/web-security/request-smuggling/finding/lab-confirming-cl-te-via-differential-responses
* CORS
	* https://portswigger.net/web-security/cors/lab-basic-origin-reflection-attack
* XXE Injection
	* https://portswigger.net/web-security/xxe/lab-exploiting-xxe-to-retrieve-files
* Web sockets
	* https://portswigger.net/web-security/websockets/lab-manipulating-messages-to-exploit-vulnerabilities
* Oauths
	* https://portswigger.net/web-security/oauth/lab-oauth-authentication-bypass-via-oauth-implicit-flow
* JWTs
	* https://portswigger.net/web-security/jwt/lab-jwt-authentication-bypass-via-unverified-signature
* GraphQL
	* https://portswigger.net/web-security/graphql/lab-graphql-reading-private-posts
* API Testing
	* https://portswigger.net/web-security/api-testing/lab-exploiting-api-endpoint-using-documentation
# 🔴Linux
Linux is pretty straightforward, especially if you are familiar with the command line. I don't have specific htb's to recommend because the ones I really like are paywalled, but you can apply these TTPs to any box you do!
* 
# 🟦Windows
Windows can be really intimidating (it literally took me halfway through my internship to bite the bullet and dive into it head first; you're not alone). The great thing about Windows is that is a glorified mess, and once you learn some TTPs you can start to see how easy it is to break. Like Linux, I don't have specific htb's to recommend because the ones I really like are paywalled, but you can apply these TTPs to any box you do!
* [ASREPRoasting](https://book.hacktricks.xyz/windows-hardening/active-directory-methodology/asreproast)
	* you'll need to subsequently crack the hashes
```bash
impacket-GetNPUsers htb.local/ -usersfile users.txt -format hashcat -outputfile output.hash -dc-ip <IPADDR>
```

```bash
hashcat -m 18200 -a 0 output.hash /usr/share/wordlists/rockyou.txt.gz
```
* Kerberoasting
* ldapsearch
* bloodhound
	* need to start a neo4j instance
	* need to run bloodhound
	* need to run sharphound on 
* [Secretsdump](https://book.hacktricks.xyz/windows-hardening/stealing-credentials)
```bash
impacket-secretsdump 'FOREST.HTB.LOCAL'/'user':'pass'@'DC' -target-ip <IPADDR>
```
# 📖Resources

| Resource     | Link                                                |
| ------------ | --------------------------------------------------- |
| Hack Tricks  | https://book.hacktricks.xyz/                        |
| Port Swigger | https://portswigger.net/web-security                |
| Payloads     | https://github.com/swisskyrepo/PayloadsAllTheThings |
| Hack the Box | https://app.hackthebox.com/                         |
