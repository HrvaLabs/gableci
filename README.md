# Gableci

Gableci is a free, independent directory of weekly lunch menus from restaurants around Samobor, Croatia.

**Live site:** https://gableci.hrva.cc/  
**Organization:** [HrvaLabs](https://hrvalabs.net/)  
**Source:** https://github.com/HrvaLabs/gableci

## Architecture

This repository contains the static, user-facing website. It is deployed directly from the `main` branch through Cloudflare Pages.

- **Cloudflare Pages project:** `gableci-hrvalabs`
- **Production domain:** `gableci.hrva.cc`
- **No build command:** static HTML/CSS/JavaScript at the repository root
- **Content delivery:** the site reads menu data from `https://cdn.hrva.cc/gableci/menus.json`
- **Data processing and publishing:** maintained separately in `karlohrvacic/gableci-pipeline` (not moved as part of this website migration)

## Local development

```sh
python3 -m http.server 8080
```

Visit http://localhost:8080/.

The live menu feed is provided by a separate CDN and may be unavailable without network access.

## Deployment

Changes merged or pushed to `main` trigger a Cloudflare Pages production deployment. Verify the deployment and `gableci.hrva.cc` after making changes.

The former `gableci` Pages project was kept temporarily as a rollback option during the migration from `karlohrvacic/gableci` to `HrvaLabs/gableci`. It is not the production target.

## Notes

- Repository documentation and commit messages are in English; the public-facing site is in Croatian.
- The website is informational and is not affiliated with the restaurants whose menus are displayed.
- Do not publish access credentials, private backend URLs or internal infrastructure information in this repository.
