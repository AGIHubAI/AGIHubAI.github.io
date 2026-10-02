# AGIHubAI.github.io

Source for https://agihub.ai, served by GitHub Pages (Jekyll, `jekyll-theme-minimal`).

| Path | Contents |
|---|---|
| `index.md` | Landing page |
| `docs/` | Strategic model, growth engine, monetization, open questions |
| `CNAME` | Custom domain `agihub.ai` |

## DNS for agihub.ai

At the domain registrar:

| Type | Host | Value |
|---|---|---|
| A | @ | 185.199.108.153 |
| A | @ | 185.199.109.153 |
| A | @ | 185.199.110.153 |
| A | @ | 185.199.111.153 |
| CNAME | www | agihubai.github.io |

Then enable "Enforce HTTPS" in repo Settings → Pages once the certificate is issued.

## Local preview

```bash
gem install bundler jekyll
jekyll serve
```
