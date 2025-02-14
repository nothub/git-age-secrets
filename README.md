# git-age-secrets

An example setup for handling secret-encryption in git with age.

~/.gitconfig
```ini
...

[filter "age"]
    clean = age -R ~/.ssh/id_ed25519.pub -a -
    smudge = age -d -i ~/.ssh/id_ed25519 -
    required = true

...
```
