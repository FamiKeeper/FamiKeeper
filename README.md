# FamiKeeper support website

Static support and legal pages for the FamiKeeper iOS app. The site uses HTML, CSS,
and the app's existing logo. It has no JavaScript, build step, external fonts,
analytics, or tracking cookies.

## Public URLs

| Purpose | URL |
| --- | --- |
| Home | https://famikeeper.github.io/FamiKeeper/ |
| App Store Support URL | https://famikeeper.github.io/FamiKeeper/support.html |
| Privacy Policy URL | https://famikeeper.github.io/FamiKeeper/privacy.html |
| Terms of Use | https://famikeeper.github.io/FamiKeeper/terms.html |

Support and privacy contact: `dongdongh0408@163.com`.
The service provider is identified as the FamiKeeper developer. No company name
or jurisdiction is assumed.

## Local preview

```sh
python3 -m http.server 8765 --bind 127.0.0.1
```

Open `http://127.0.0.1:8765/`. Normal page links are relative so that they also work
under the GitHub Pages project path. The custom `404.html` uses `/FamiKeeper/` as
its base so its navigation works for missing nested URLs on the published site.

## Publishing

GitHub Pages publishes the root directory of `main`. The `.nojekyll` file keeps
the site buildless. Push changes to `main` to publish them. No custom domain or
separate deployment credentials are required.

```sh
git push origin main
gh api repos/FamiKeeper/FamiKeeper/pages
gh api repos/FamiKeeper/FamiKeeper/pages/builds/latest
```

## Maintenance

- Keep the shared header and footer consistent across all HTML pages.
- Keep `privacy.html` and `terms.html` at their existing paths.
- Update the effective date when a policy changes.
- Check mobile layouts, keyboard navigation, FAQ expansion, email links, and all
  page and section links before publishing.
- Verify privacy statements against the current app and backend. Update them
  before changing payments, SDKs, data processing, retention, or service providers.
- Do not add a fixed server deletion deadline without an operational guarantee.
- The App Store privacy answers and the iOS app's legal URL configuration are
  managed separately from this website.

## Reference requirements

- [Apple App Review Guidelines](https://developer.apple.com/app-store/review/guidelines/)
- [GitHub Pages publishing sources](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site)
- [GitHub Privacy Statement](https://docs.github.com/en/site-policy/privacy-policies/github-general-privacy-statement)
