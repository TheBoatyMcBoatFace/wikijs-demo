---
title: Untitled Page
description: 
published: true
date: 2022-12-30T23:35:00.419Z
tags: 
editor: markdown
dateCreated: 2022-12-30T23:35:00.419Z
---

# Header
Your content here

```javascript
// Example usage
insertCodeBlock('TheBoatyMcBoatFace/upptime', '.github/workflows/response-time.yml');
```

```javascript
// Fetch the code file from the GitHub repository using the GitHub API
async function fetchCodeFile(repo, path) {
  const response = await fetch(`https://api.github.com/repos/${repo}/contents/${path}`);
  const file = await response.json();
  return file.content;
}

// Extract the code from the file
async function insertCodeBlock(repo, path) {
  const code = await fetchCodeFile(repo, path);
  const decodedCode = atob(code);
  
  // Insert the code into a code block in the Markdown file
  const codeBlock = `\`\`\`\n${decodedCode}\n\`\`\``;
  // Insert the code block into the desired location in the Markdown file
  document.getElementById('markdown').innerHTML += codeBlock;
}

// Example usage
insertCodeBlock('user/repo', 'path/to/file.ext');