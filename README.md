# git-age-secrets

An example setup for automatic secret-encryption in git with age.

---

An ssh key-pair can be used for identity and recipient.

Add this filter to your `~/.config/git/config`:

```ini
[filter "age"]
	clean = age -R ~/.ssh/id_ed25519.pub -a -
	smudge = age -d -i ~/.ssh/id_ed25519 -
	required = true
```

---

Apply the filter in your projects `.gitattributes`:

```ini
/secret.yaml filter=age
/secrets/**  filter=age	
```

---

Further infos in a [post by Sean Liao](https://seankhliao.com/blog/12020-09-24-gitattributes-age-encrypt/).
