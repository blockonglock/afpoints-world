# Namecheap DNS For GitHub Pages

Before changing DNS, add `afpoints.world` as the custom domain in the GitHub Pages settings for the public site repository. GitHub recommends doing this first to reduce custom-domain takeover risk.

In Namecheap:

1. Open `Domain List`.
2. Click `Manage` for `afpoints.world`.
3. Open `Advanced DNS`.
4. In `Host Records`, remove conflicting old Railway, redirect, `A`, or `CNAME` records for `@` and `www`.
5. Add these records:

| Type | Host | Value | TTL |
| --- | --- | --- | --- |
| A Record | @ | 185.199.108.153 | Automatic |
| A Record | @ | 185.199.109.153 | Automatic |
| A Record | @ | 185.199.110.153 | Automatic |
| A Record | @ | 185.199.111.153 | Automatic |
| CNAME Record | www | blockonglock.github.io | Automatic |

After DNS propagates, return to GitHub Pages and enable `Enforce HTTPS`.

Verification commands:

```sh
dig afpoints.world +noall +answer -t A
dig www.afpoints.world +noall +answer -t CNAME
```
