# Git hooks

[Official Git Hooks info](https://git-scm.com/book/en/v2/Customizing-Git-Git-Hooks)


- Where are Git Hooks located? `.git/hooks`  
- Overview of posible Git Hooks  
  - client-side  
    - committing-workflow hooks  
      - pre-commit hook  
      - prepare-commit-msg hook  
      - commit-msg hook  
      - post-commit hook  
    - email-workflow hooks  
      - applypatch-msg hook  
      - pre-applypatch hook  
      - post-applypatch hook  
    - other hooks  
      - pre-rebase hook  
      - post-rewrite hook  
      - post-checkout hook  
      - post-merge hook  
      - pre-push hook  
  - server-side  
    - pre-receive hook  
    - update hook  
    - post-receive hook  
- How to install a hook?  
  - add a file with the correct name  
  - make the file executable `chmod +X <file-name>`  
