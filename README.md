# Google Dorks Cheat Sheet

A curated and expanded collection of powerful Google Dork queries, techniques, and real-world use cases for advanced search, OSINT (Open-Source Intelligence), and security research.

> **Disclaimer:** These techniques are intended for educational, ethical, and defensive security purposes only. Do not use them to access systems or data without authorization.

---

## Table of Contents

* [What is Google Dorking?](#what-is-google-dorking)
* [Core Dorking Commands](#core-dorking-commands)

  * [Cache](#cache)
  * [Intext / Allintext](#intext)
  * [Filetype](#filetype)
  * [Intitle / Allintitle](#intitle)
  * [Inurl / Allinurl](#inurl)
  * [Site](#site)
  * [Ext](#ext)
  * [Inanchor / Allinanchor](#inanchor)
  * [Around](#around)
  * [Quotes](#quotes)
  * [Related](#related)
  * [Info](#info)
* [Advanced Dorking Techniques](#advanced-dorking-techniques)

  * [Finding Login Portals](#login-portals)
  * [Exposed Documents & Files](#documents)
  * [Database Dumps & Backups](#databases)
  * [Cloud Storage Leaks](#cloud)
  * [Cameras & IoT Devices](#iot)
  * [Admin Panels](#admin)
  * [Error Messages & Debug Pages](#errors)
* [Operators](#operators)
* [Search Parameters](#search-parameters)
* [Useful Tools](#tools)
* [Contribution](#contribution)

---

## What is Google Dorking?

Google Dorking (also called Google Hacking) involves using advanced search operators to uncover hidden or sensitive information indexed by search engines.

This can include:

* Misconfigured servers
* Exposed credentials
* Public documents
* Debug pages
* Backup files

---

## Core Dorking Commands

### 1. Cache <a name="cache"></a>

View Google's cached version of a webpage.

```
cache:example.com
cache:https://example.com login
```

Useful when:

* A page is down
* Content was removed or altered

---

### 2. Intext / Allintext <a name="intext"></a>

Search for keywords within page content.

```
intext:"password"
allintext:"username" "password"
```

Use cases:

* Finding credential leaks
* Searching logs or config files

---

### 3. Filetype <a name="filetype"></a>

Filter results by file extension.

```
filetype:pdf
filetype:xls
filetype:log
```

Common targets:

* PDFs with sensitive info
* Excel sheets with data
* Log files

---

### 4. Intitle / Allintitle <a name="intitle"></a>

Search within page titles.

```
intitle:"index of"
allintitle:"admin login"
```

Great for:

* Directory listings
* Admin pages

---

### 5. Inurl / Allinurl <a name="inurl"></a>

Search for keywords inside URLs.

```
inurl:admin
allinurl:admin login panel
```

Useful for:

* Finding login pages
* API endpoints

---

### 6. Site <a name="site"></a>

Limit results to a specific domain.

```
site:example.com
site:gov filetype:pdf
```

Combine with other operators for targeted searches.

---

### 7. Ext <a name="ext"></a>

Alternative to `filetype:`.

```
ext:log
ext:sql
```

---

### 8. Inanchor / Allinanchor <a name="inanchor"></a>

Search based on anchor text (link text).

```
inanchor:"click here"
allinanchor:"admin login"
```

---

### 9. Around <a name="around"></a>

Find terms within proximity.

```
"password" AROUND(3) "username"
```

---

### 10. Quotes <a name="quotes"></a>

Exact match search.

```
"confidential report"
```

---

### 11. Related <a name="related"></a>

Find similar websites.

```
related:example.com
```

---

### 12. Info <a name="info"></a>

Get information about a site.

```
info:example.com
```

---

## Advanced Dorking Techniques

### Finding Login Portals <a name="login-portals"></a>

```
inurl:login
intitle:"login page"
inurl:admin intitle:login
```

---

### Exposed Documents <a name="documents"></a>

```
filetype:pdf "confidential"
filetype:xls "internal use only"
filetype:doc "do not distribute"
```

---

### Database Dumps & Backups <a name="databases"></a>

```
filetype:sql "dump"
filetype:bak "database"
inurl:backup filetype:sql
```

---

### Cloud Storage Leaks <a name="cloud"></a>

```
site:s3.amazonaws.com "password"
site:drive.google.com "confidential"
site:dropbox.com "private"
```

---

### Cameras & IoT Devices <a name="iot"></a>

```
inurl:"/view.shtml"
intitle:"Live View / - AXIS"
inurl:"ViewerFrame?Mode="
```

Accessing live systems without permission is illegal.

---

### Admin Panels <a name="admin"></a>

```
inurl:admin
intitle:"admin panel"
inurl:cpanel
```

---

### Error Messages & Debug Pages <a name="errors"></a>

```
"SQL syntax error"
"Warning: include("
"Fatal error:"
```

Helps identify vulnerable applications.

---

## Operators

| Operator | Description  | Example                |
| -------- | ------------ | ---------------------- |
| OR       | Either term  | admin OR login         |
| AND      | Both terms   | admin AND panel        |
| -        | Exclude term | admin -login           |
| *        | Wildcard     | "password * file"      |
| ()       | Grouping     | (admin OR login) panel |

---

## Search Parameters

Refine your searches using Google URL parameters:

* `&num=100` → Show more results
* `&start=20` → Pagination
* `&hl=en` → Language
* `&gl=us` → Region

Example:

```
https://www.google.com/search?q=site:example.com&num=100
```

---

## Useful Tools <a name="tools"></a>

* Google Advanced Search
* Wayback Machine (web archives)
* Cache checkers
* OSINT frameworks

---

## Good Tips

* Combine multiple operators for precision
* Use quotes to reduce noise
* Try different file types (`pdf`, `xls`, `txt`)
* Search in different languages
* Think like a developer (file names, paths, structures)

---

## Contribution

Feel free to contribute:

* New dorks
* Real-world examples
* Better categorizations
* Tools & automation scripts

Submit a pull request and help improve this resource 

---

## Final Note

Google Dorking is powerful—but with great power comes responsibility.

Use it to:

* Improve security
* Learn OSINT
* Audit your own systems

Not to exploit others.

---

