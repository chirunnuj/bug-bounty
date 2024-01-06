# Bug Bounty Knowledge Base

## Index

- [Bug Bounty Knowledge Base](#bug-bounty-knowledge-base)
  - [Index](#index)
  - [Articles](#articles)
  - [Techniques](#techniques)
  - [Tools](#tools)
    - [Subdomain, URL Enumeration](#subdomain-url-enumeration)
    - [Parameter Enumeration](#parameter-enumeration)
    - [Javascript Discovery](#javascript-discovery)

## Articles

- Parameter Enumeration: [ParamSpider](https://portswigger.net/daily-swig/paramspider-new-tool-helps-in-the-discovery-of-url-parameter-vulnerabilities)
- ParamMiner
  Discovery using wordlists and guessing techniques

## Techniques

## Tools

### Subdomain, URL Enumeration

- [waybackurl](https://github.com/tomnomnom/waybackurls)
  ```
    cat domains.txt | waybackurls > urls
  ```
- [subfinder](https://github.com/projectdiscovery/subfinder)

  ```
    Example: $> subfinder -d $domain -all > subdomains.txt
  ```

- [assetfinder](https://github.com/tomnomnom/assetfinder)

  ```
    Example: $> assetfinder $domain -subs-only | grep $domain$ >> subdomains.txt
  ```

- Eliminate duplicated subdomains
  ```
    $> cat subdomains.txt | sort -u > sub-list.txt
  ```
- Check whether the subdomains are alive using [httpx](https://github.com/projectdiscovery/httpx)
  ```
    $> cat sub-list.txt | httpx > live-sub.txt
  ```

### Parameter Enumeration

- [ParamSpider](https://github.com/devanshbatham/ParamSpider) discover by query web archives.

  ```
    $> paramspider -d example.com
  ```

- [ParamMiner](https://portswigger.net/bappstore/17d2949a985c4b7ca092728dba871943) [**BurbSuite Extension**] discovers URL parameters using wordlists and guessing techniques.

### Javascript Discovery

- [Retire.js](https://portswigger.net/bappstore/36238b534a78494db9bf2d03f112265c) [**BurpSuite Extension**]
- [Uproot.js](https://github.com/0xDexter0us/uproot-JS) [**BurpSuite Extension**] downloads javascript files
- [JS Link Finder](https://portswigger.net/bappstore/0e61c786db0c4ac787a08c4516d52ccf) [**BurpSuite Extension**] scans JavaScript for endpoints links.
