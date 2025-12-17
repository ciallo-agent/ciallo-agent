---
name: github-api
description: How to interact with GitHub API using PowerShell. Use this skill when you need to create repos, submit PRs, manage issues, or interact with GitHub.
---

# GitHub API Skill

## Authentication
```powershell
$headers = @{ 
    "Authorization" = "token YOUR_TOKEN"
    "Accept" = "application/vnd.github.v3+json" 
}
```

## Common Operations

### Get User Info
```powershell
Invoke-RestMethod -Uri "https://api.github.com/user" -Headers $headers
```

### Create/Update File
```powershell
$content = "file content"
$contentBase64 = [Convert]::ToBase64String([System.Text.Encoding]::UTF8.GetBytes($content))
$body = @{ message = "commit message"; content = $contentBase64; sha = $existingSha } | ConvertTo-Json
Invoke-RestMethod -Uri "https://api.github.com/repos/OWNER/REPO/contents/PATH" -Method PUT -Headers $headers -Body $body
```

### Create PR
```powershell
$prBody = @{ title = "PR title"; body = "description"; head = "branch"; base = "main" } | ConvertTo-Json
Invoke-RestMethod -Uri "https://api.github.com/repos/OWNER/REPO/pulls" -Method POST -Headers $headers -Body $prBody
```

### Fork Repo
```powershell
Invoke-RestMethod -Uri "https://api.github.com/repos/OWNER/REPO/forks" -Method POST -Headers $headers
```

### Star Repo
```powershell
Invoke-RestMethod -Uri "https://api.github.com/user/starred/OWNER/REPO" -Method PUT -Headers $headers
```

## Important Notes
- README.md might be in .github/ folder, not root! Use /readme endpoint to find actual path
- Always verify diff before creating PR (check for "modified" not "new file")
- GitHub releases use redirects, curl needs -L flag