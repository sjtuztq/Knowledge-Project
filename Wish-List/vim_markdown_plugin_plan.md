# Vim-markdown-plugin-plan
This is the plan for implementing my vim markdown plugin
## Existing work
- [Plugin 'suan/vim-instant-markdown'](https://github.com/suan/vim-instant-markdown) uses a github-like markdown renderor to provide markdown preview
- A python tool `grip` is for invoking github markdown API to provide exact Github-Flavoured-Markdown result
- Github markdown [offline renderer](https://github.com/joeyespo/grip/issues/35) is still in progress

## Plan
- replace `instant-markdown-d` invoked in `vim-instant-markdown` plugin with `grip`
- for an **Ad-hoc** solution to authenticating issues, please refer to [this link](https://github.com/joeyespo/grip/issues/35) for solution
