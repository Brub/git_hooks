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
  - make the file executable `chmod +x <file-name>`  
- Specify the language on the first line of your  (you can use any scripting language as long as it can be run as an executable)
  - Bash `#!/bin/bash`  
  - Shell `#!/bin/sh`  
  - Python `#!/usr/bin python` 

## Hook pass / fail
In the hook you can check data and you can define if the hook pass or fail. This can be specified by the exit argument:  
- pass = `exit 0`
- fail = `exit 1`

## Examples  
### pre-commit hook (python)

This hook will print out all modified files.

```python  
#!/usr/bin/env python
import sys, os

staged_files = os.popen('git diff --cached --name-only --diff-filter=ACM')


# print all the modified files  
print("Mofified files:")
print("---------------")
for file in staged_files:
    print(f"- {file}")

sys.exit(0)  # continue the commit

```

## Resources
[Medium - Get Started with Git Hooks](https://medium.com/@f3igao/get-started-with-git-hooks-5a489725c639)  
[Atlassian - Git Hooks](https://www.atlassian.com/git/tutorials/git-hooks)  
[DigitalOcean - How To Use Git Hooks To Automate Development and Deployment Tasks](https://www.digitalocean.com/community/tutorials/how-to-use-git-hooks-to-automate-development-and-deployment-tasks)  
[Git hooks](https://githooks.com/)  
[hostinger - How to Use Git Hooks?](https://www.hostinger.com/tutorials/how-to-use-git-hooks/)
[Red Hat - Git hooks: How to automate actions in your Git repo](https://www.redhat.com/sysadmin/git-hooks)
