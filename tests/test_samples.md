
# Test Results

Python version used: 3.12.12   |   Operating system: Windows 11  |   Date: 29 October 2026
| # | Input | Expected result | Actual result | Pass/Fail |
|---|-------|-----------------|---------------|-----------|
| 1 | https://www.example.com/login |  No listed warning signs | No listed warning signs found. This does NOT prove safety | [Pass] |
| 2 | http://192.0.2.10/account | IP address + HTTP | Uses an IP address instead of a familiar domain + Uses HTTP. HTTPS alone does not prove trust | [Pass] |
| 3 | http://example.com@sample.invalid/login | @ symbol + HTTP | Contains an @ symbol; inspect carefully + Uses HTTP. HTTPS alone does not prove trust | [Pass] |
| 4 | https://a.b.c.d.e.example.invalid/path |  Many hostname segments | Contains many hostname segments/subdomains | [Pass] |
| 5 |  https://xn--example.invalid/ | Punycode-style hostname | Contains a punnycode-style hostname | [Pass] |

| 1 | https://www.example.com/login | No listed warning signs | | |
| 2 | http://192.0.2.10/account | IP address + HTTP | | |
| 3 | http://example.com@sample.invalid/login | @ symbol + HTTP | | |
| 4 | https://a.b.c.d.e.example.invalid/path | Many hostname segments | | |
| 5 | https://xn--example.invalid/ | Punycode-style hostname | | |

## Notes
I learned how to programmatically parse and inspect different components of a URL for security risks, I also learned about many deceptive techniques attackers can use, such as punycode or excessive subdomains MFA fatigue, to make malicious links appear legitimate. It surprised me to see in practice that URL can easily  use HTTPS but still contain highly suspicious structural red flags like embedded IP addresses or @ symbols.
