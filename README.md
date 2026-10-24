# GPT_SmokeyP public website

A standalone, buildless website for the privately operated GPT_SmokeyP assistant.
Prepared October 24, 2026. Public support/privacy contact: **mckechniep@gmail.com**.

## Files

| File | Purpose |
| --- | --- |
| `index.html` | Product description, Gmail/Calendar capabilities, data overview, FAQ |
| `privacy.html` | Dedicated policy covering Google access, use, storage, sharing, retention, revocation, and deletion |
| `terms.html` | Terms of use |
| `contact.html` | Support/privacy contact and deletion-request instructions |
| `assets/site.css` | Shared responsive styles, keyboard focus, reduced-motion and print support |
| `assets/mark.svg` | Local vector project mark and favicon |
| `.nojekyll` | Serves the site directly without a Jekyll build |

There is no JavaScript, package installation, build command, remote font, analytics,
cookie banner, sign-in form, or connection to the running assistant. The mark is
for this website; uploading it to Google’s consent screen is optional and can
introduce branding-verification requirements.

## Publish on GitHub Pages

This directory is its own Git repository. Push **only this website repository** to
GitHub. The adjacent assistant project contains private configuration and runtime
data and is not part of the website. The `.gitignore` deliberately allows only
the reviewed public site files; extend its allowlist when intentionally adding assets.

1. Commit and push the site files to your selected GitHub repository and branch.
2. In that repository, open **Settings → Pages**.
3. Under **Build and deployment**, choose **Deploy from a branch**.
4. Select the branch you pushed (this local repository initially uses `master`;
   use `main` instead if you rename it) and the **`/(root)`** folder. Save.
5. Wait for the Pages deployment to finish and open the URL GitHub reports.
6. Enable **Enforce HTTPS** when available. Check all four pages in a signed-out
   browser, including the privacy and contact links.

No GitHub Actions workflow or custom domain is required by this static site.
Relative asset and navigation links support both a repository subpath and a root
domain. GitHub Free supports Pages from public repositories; private repositories
require a supported paid plan. The published website itself is public.

## Google Auth Platform fields

Use the exact live address GitHub gives you as the base URL. For a typical project
site, the following are examples only; replace `YOUR-USERNAME` and `YOUR-REPOSITORY`
with the actual published address. Do not paste placeholder URLs into Google.

| Google field | Value |
| --- | --- |
| App name | `GPT_SmokeyP` (keep the existing name consistent) |
| User support email | `mckechniep@gmail.com` if available in the account dropdown |
| Developer contact email | `mckechniep@gmail.com` |
| Application home page | `https://YOUR-USERNAME.github.io/YOUR-REPOSITORY/` |
| Application privacy policy | `https://YOUR-USERNAME.github.io/YOUR-REPOSITORY/privacy.html` |
| Application terms of service | `https://YOUR-USERNAME.github.io/YOUR-REPOSITORY/terms.html` |
| Logo | Optional; leave empty if you do not want branded consent-screen verification |

Keep the existing OAuth Desktop client and existing permissions. These website
links are informational links, not OAuth callback/redirect URLs. Do not replace
the Desktop client's loopback authorization flow with a website URL.

For **Authorized domains**, use the domain Google accepts for the published site,
without a scheme or path. A `github.io` site being publicly reachable does not
guarantee Google will accept its domain for your app. Google’s current OAuth domain
verification instructions require a Search Console **Domain property verified
through DNS**, not just a URL-prefix property or HTML verification file. If Google
requires that ownership check, use a domain you control and point it to GitHub Pages.
Use the new domain consistently for the homepage, privacy, and terms fields; verify
the appropriate root domain with the Google account that owns the Cloud project.

The personal-use exception to verification and the **Audience → In production**
publishing setting are separate from brand verification. These pages do not
guarantee OAuth approval. Review the exact current Console requirements rather
than starting an unnecessary verification submission.

After switching the existing Google project out of Testing, renew the affected
Gmail authorizations using the existing private helper and safely activate those
credentials on Spark. Publishing this site does not renew tokens, change Google
Cloud settings, or change any running assistant service.

Once the public address is final, also make the privacy-policy link visible in
the private assistant interface before connecting any additional users. That
runtime change is separate from this website and has not been made here.

## Content maintenance

The policies describe the current private deployment: Gmail `gmail.modify`,
Calendar list/event/availability permissions, local model inference, saved chats,
client records, and retained private backups. They do not promise automatic data
expiry or deletion of backup copies when a chat is deleted. The operator handles
deletion requests manually and should explain their scope and completion.

Review these pages if you add public registration, a cloud model provider,
analytics, new scopes, changed retention, or new sharing behavior. Update the
visible policy date when data practices change. Keep the Google policy URLs and
the private assistant’s disclosures synchronized. The site intentionally contains
no live mailbox addresses other than the approved public contact, credentials,
private endpoints, host names, model paths, conversation records, or backups.

## Local preview — Spark / Bash

From the website directory:

```bash
python3 -m http.server 8088 --bind 127.0.0.1
```

Open `http://127.0.0.1:8088/` in a browser on the Spark. Stop the preview with
Ctrl+C. This serves the public website files only; no assistant service is needed.

## Reference documentation

- [GitHub Pages publishing source](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site)
- [Custom domains on GitHub Pages](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site)
- [Google app homepage requirements](https://support.google.com/cloud/answer/13807376?hl=en)
- [Google privacy policy requirements](https://support.google.com/cloud/answer/13806988?hl=en)
- [Google domain verification](https://support.google.com/cloud/answer/13804266?hl=en)
- [Google personal-use verification exception](https://support.google.com/cloud/answer/13464323?hl=en)
- [Google Audience / publishing status](https://support.google.com/cloud/answer/15549945?hl=en)
- [Google API Services User Data Policy](https://developers.google.com/terms/api-services-user-data-policy)
