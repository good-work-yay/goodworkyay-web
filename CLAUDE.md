# goodworkyay-web

Static HTML/CSS landing pages served via Cloudflare Pages. No build step — files deploy as-is.

## Tech Stack
- **Pure HTML + CSS** — no framework, no bundler, no npm
- **Cloudflare Pages** — static file hosting, auto-deploys on push to `main`
- **Cloudflare Workers** — edge logic lives alongside Pages if needed

## Structure
```
index.html              # goodworkyay.com home
about.html              # Company / legal entity details
contact.html            # Contact routes + account deletion
privacy.html            # Website privacy policy
terms.html              # Terms of use
404.html                # Cloudflare Pages not-found page
scriptdrill/
  index.html            # ScriptDrill product landing page
  privacy.html          # ScriptDrill app privacy policy
dot-threads/
  index.html            # Dot Threads product + support page
  privacy.html          # Dot Threads app privacy policy (AdMob)
```

Every page carries the same header nav and footer. The footer names the legal
entity (GoodWork, LLC) on every page — Apple Developer enrollment requires the
domain to be visibly associated with the enrolling organization.

## Deployment
Push to `main` → Cloudflare Pages auto-deploys. No build command, no preview step needed.

## Conventions
- Inline `<style>` blocks — keeps each page self-contained, no external stylesheet coordination
- No JavaScript unless strictly necessary (this is a marketing site)
- Mobile-first, system font stack (`-apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif`)
- New pages go in a subdirectory named after the product (e.g. `scriptdrill/`, `gospel/`)

## Orchestration
This project is simple enough that subagents are rarely needed. If adding a new product page, copy the structure from `scriptdrill/index.html`.

## Cloud sessions (Claude Code on the web)

- 정적 HTML 이라 설치 단계가 없다. `main` 에 머지되면 Cloudflare Pages 가 자동 배포하므로 클라우드 세션은 PR 까지만.
