---
name: browser
description: Web scraping and browser automation using shot-scraper. Use this to read web pages, extract content, and interact with websites.
---

# Browser Skill

## Basic Usage

### Extract headings from a page
```powershell
shot-scraper javascript "URL" "Array.from(document.querySelectorAll('h1,h2,h3')).map(h=>h.innerText).join('\n')" -r
```

### Get full page text
```powershell
$text = shot-scraper javascript "URL" "document.body.innerText" -r
```

### Search for keywords in page
```powershell
$text -split "`n`n" | Where-Object { $_ -match "keyword" } | Select-Object -First 3
```

### Get main content (first 2000 chars)
```powershell
shot-scraper javascript "URL" "document.querySelector('main')?.innerText.substring(0,2000)" -r
```

## Advanced
- Use `shot-scraper --help` for more options
- Can perform clicks and other interactions

## Notes
- Purchased for 10 Ciallo coins (on sale from 120)
- Acquired: 2025-12-17