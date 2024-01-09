# 粉面弹子CVV鱼站管理 / "Fenmiandanzi CVV fish station management"

## Description
The Fenmiandanzi framework is a boilerplate template used by phishers to get credit cards, by replicating legit websitets (ex.: USPS).
The vulnerability in the framework (v1.0.0) is that the information within the control pannel public can modify the API connector variables.

## CVSS
CVSS:4.0/AV:N/AC:L/AT:N/PR:N/UI:A/VC:H/VI:H/VA:H/SC:H/SI:H/SA:H
Score: 9.4 / Critical 
    Macro vector: 100100
    Exploitability: Medium
    Complexity: High
    Vulnerable system: High
    Subsequent system: Medium
    Exploitation: High
    Security requirements: High


## Impact:
- Information Disclosure
- Code injection
- DoS
- & much more

## Proof of concept:
In v1.0.0 the following can be done:
1. Navigate to /static/config.js; ex: `127.100.20.18/static/config.js`
2. Append to serverURL getRuleList; ex `serverURL:"127.0.40.1/abc/"` -> `127.0.40.1/abc/getRuleList`
3. Navigate to the new url; ex: `127.0.40.1/abc/getRuleList`
4. You can modify the variables that will be parsed by Vue.js live. Example of impact: DoS by deleting all of the variables.
