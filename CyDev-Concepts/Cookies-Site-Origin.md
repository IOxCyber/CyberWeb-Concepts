## Cookies
- Small pieces of data that websites store on your browser to remember information about you. This can include things like login status, user preferences, and tracking information.

## Site: `a site is defined as the top-level domain (TLD)`
Usually something like .com or .net, plus one additional level of the domain name. This is often referred to as the TLD+1.

![image](https://github.com/user-attachments/assets/d04cc571-a60a-44ed-b95a-abc752d9e7ad)
- When determining whether a request is same-site or not, the URL scheme is also taken into consideration.

This means that a link from http://app.example.com to https://app.example.com is treated as cross-sites.

>>> You may come across the term "effective top-level domain" (eTLD). This is just a way of accounting for the reserved multipart suffixes that are treated as top-level domains in practice, such as .co.uk.

## Site Vs Origin:
- The difference between a site and an origin is their `scope; a site encompasses multiple domain names, whereas an origin only includes one.`
- ![image](https://github.com/user-attachments/assets/a5f16ed7-3b64-44d7-aafb-318f28834975)
- ![image](https://github.com/user-attachments/assets/94e77499-2650-4cb6-ab5a-86564c3b2bc6)


## Examples:
```
Same Origin:

> Both URLs share the same protocol (HTTPS), domain (example.com), and port (443, implied by HTTPS).
https://example.com/page1
https://example.com/page2

Different Origin:

> The protocols are different (HTTPS vs. HTTP).
https://example.com/page
http://example.com/page

> The domains are different (example.com vs. sub.example.com).
https://example.com/page
https://sub.example.com/page

> The ports are different (443 vs. 8443).
https://example.com:443/page
https://example.com:8443/page

```
