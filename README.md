# Protect Your Robinhood Portfolio GitHub Pages tool that helps Robinhood users generate **Gmail dot variants** that route to the **same inbox**, so they can review suspicious lookalike addresses, search their records, and report variants involved in phishing attacks.

> Defensive use only. This project does **not** create accounts, prefill signup forms, automate anything against Robinhood, or interact with Robinhood systems in any way.

---

## Why this exists

In late April 2026, multiple reports described a phishing campaign that combined:

1. **Gmail dot aliases** (`johnsmith@gmail.com`, `john.smith@gmail.com`, etc. all route to the same inbox), and
2. a reported flaw in **Robinhood’s account creation / onboarding email flow**

…to make phishing emails appear more legitimate.

The idea behind this tool is simple:

- You enter your Gmail address
- The page computes the **canonical Gmail mailbox**
- It generates every possible **dotted variant**
- You can then:
  - search your own systems/logs,
  - compare against suspicious emails,
  - copy the list,
  - or export it to CSV for reporting/documentation

---

## Official Robinhood resources

These are the **official Robinhood pages** linked from the app/site:

- [How to identify and report scams](https://robinhood.com/us/en/support/articles/how-to-identify-and-report-scams/)
- [Device approvals](https://robinhood.com/us/en/support/articles/device-approvals/)
- [Device monitoring](https://robinhood.com/us/en/support/articles/device-monitoring/)
- [Contact Robinhood securely](https://robinhood.com/contact)
- [Security best practices](https://robinhood.com/us/en/support/articles/best-practices/)

Robinhood’s official guidance includes:

- use only official support channels,
- avoid clicking suspicious links,
- deny unexpected device approvals,
- change your password immediately,
- remove unknown devices,
- and report suspected phishing to `reportphishing@robinhood.com`.

---

## Incident-specific public statement

I could not reliably surface the **direct Robinhood X post URL** in search results, so this project links to Robinhood’s official support pages above **plus** public reporting that quotes Robinhood’s statement about the incident.

Useful references:

- [BleepingComputer: Robinhood account creation flaw abused to send phishing emails](https://www.bleepingcomputer.com/news/security/robinhood-account-creation-flaw-abused-to-send-phishing-emails/)
- [Yahoo Finance / TheStreet syndication: Robinhood suffers phishing attempt ahead of quarterly earnings](https://finance.yahoo.com/markets/crypto/articles/robinhood-suffers-phishing-attempt-ahead-174923075.html)

If you later capture the exact official post URL from Robinhood’s X/help account, you can swap that into the page and this README.

---

## Features

- ✅ Static HTML / CSS / JavaScript only
- ✅ Runs entirely in the browser
- ✅ Supports `@gmail.com` and `@googlemail.com`
- ✅ Generates inbox-equivalent dotted Gmail variants
- ✅ Copy all results to clipboard
- ✅ Download results as CSV
- ✅ Filter results locally
- ✅ Robinhood-inspired black / green styling

---

## Defensive scope

This project is intended only for:

- reviewing inbox-equivalent Gmail variants,
- documenting suspicious lookalike addresses,
- support/reporting workflows,
- user education,
- defensive security awareness.

It is **not** for:

- creating Robinhood accounts,
- generating signup links,
- automating registration,
- bypassing account limits,
- impersonation,
- or any activity that would violate a platform’s terms or harm users.

---

## How it works

For a Gmail username with `n` characters after removing dots, there are:

`2^(n - 1)`

possible dot placements.

Example:

- Canonical mailbox: `janesmith@gmail.com`
- Equivalent Gmail variants include:
  - `jane.smith@gmail.com`
  - `ja.nesmith@gmail.com`
  - `j.a.n.e.s.m.i.t.h@gmail.com`

All of those still route to the **same Gmail inbox**.

---

## Quick start (GitHub Pages)

### Option A — project site

1. Create a new GitHub repository  
   Example: `protect-your-robinhood-portfolio`

2. Add these files:
   - `index.html`
   - `README.md`

3. Push to GitHub

4. In your repository, go to:

   **Settings → Pages**

5. Under **Build and deployment**:
   - Source: **Deploy from a branch**
   - Branch: `main`
   - Folder: `/ (root)`

6. Save

Your site will publish at:

`https://<your-username>.github.io/<repo-name>/`

---

### Option B — user site

If you want the site to live at the root domain:

`https://<your-username>.github.io/`

Create a repository named exactly:

`<your-username>.github.io`

Then place `index.html` at the repository root and enable Pages.

---

## Local testing

You can open `index.html` directly in a browser, or run a tiny local server.

### Python 3

```bash
python -m http.server 8080


