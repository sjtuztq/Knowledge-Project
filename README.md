# Knowledge Project
![](https://img.shields.io/badge/2018-Happy_New_Year!-orange.svg?style=flat-square)
[![made-with-Markdown](https://img.shields.io/badge/Made%20with-Markdown-1f425f.svg?style=flat-square)](http://commonmark.org)

This project is created on Jan 1, 2018. As a new year project to manage daily notes and my knowledge systematically.
## Motivation of this project
This project is motivated by Evernote and Confluence. The idea of organizing knowledge in a proper way, syncing across devices.

The basic requirement is:
- good looking
- support hierarchical page structure
- support markdown
- support content search

Some more requirement:
- Good looking

## Complete Workflow of this Project
### 1. Writing
Just create whatever folder/file you need. Text content should be in `.md` format

For reference of markdown syntax, visit [Github Guides: Mastering Markdown](https://guides.github.com/features/mastering-markdown/)
### 2. Viewing contents locally
With `grip`, you can preview the exact Github rendered markdown result locally

1. Install `grip`
```
pip install --user grip
```
2. Preview with `grip`
```
grip foo.md
```

Due to restriction of Github API usage, you need to set up grip password before using grip. For details refer to [this issue](https://github.com/joeyespo/grip/issues/35)

For further information, please visit [`grip`](https://github.com/joeyespo/grip) project page
### 3. Search contents
Use `ack` to search for interested content. For more information, please visit [`ack`](https://beyondgrep.com) project page

### 4. Push to github
View my knowledge everywhere

## How to utilize full power of this project
1. Use this as an `Evernote/Confluence` alternative that supports markdown[M↓]
1. Organize every file properly
    - Naming protocol
2. Use [`ack`](https://beyondgrep.com) to search
3. View every folder as an alternative of Evernote Notebook
