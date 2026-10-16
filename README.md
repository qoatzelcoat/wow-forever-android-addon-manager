# WoW Forever Android Addon Manager

**Couldn't find one. So I'm making one.**

A personal addon manager project for WoW Forever on Android, under [Z3D Labs](https://z3dlabs.id).

I play WoW Forever on Android and couldn't find a suitable addon manager for this environment, so I decided to explore building one myself. This is a hobby project intended exclusively for my personal, non-commercial use. I do not plan to sell, monetize, or publicly distribute the application.

The project is in planning. No working application or API integration exists, and nothing is available for download. This repository contains project documentation and a small static landing page, not application source code or APKs.

## CurseForge API

CurseForge third-party API access is being evaluated. Approval has not been granted or implied, and implementation compliance has not been verified.

The intended principles are:

- No unauthorized addon redistribution, mirroring, or independent hosting.
- Respect mod authors' ownership and distribution permissions.
- Keep API credentials private and out of public source and browser code.
- Respect API rate limits and caching restrictions.
- Implement addon downloads only where permitted.

This repository is project documentation, not an addon distribution platform. Before implementation, review and follow the current [CurseForge 3rd Party API Terms and Conditions](https://support.curseforge.com/support/solutions/articles/9000207405-curseforge-3rd-party-api-terms-and-conditions). These are intended principles, not a claim of approval or verified compliance.

## Website

Intended address: https://addons.z3dlabs.id. Deployment is not yet verified.

The page in `site/` is plain HTML and CSS, with no JavaScript, dependencies, API calls, analytics, or build step. To view locally, run `python3 -m http.server 8001 --bind 127.0.0.1 --directory site` from the repository root and open the local server in a browser.

### Cloudflare Pages setup

1. Create or reuse the public GitHub repository `qoatzelcoat/wow-forever-android-addon-manager`, with description `A personal addon manager project for WoW Forever on Android.` Do not add a license, workflows, templates, or a second README. Push these files to `main` using the initial commit message `Initial project documentation and landing page`.
2. In Cloudflare, inspect the existing `z3dlabs.id` zone, its nameservers and DNS records, and Workers & Pages custom domains. Check specifically for an existing `addons` record or assignment. Reuse an existing project only if it belongs to this site; resolve any conflict before proceeding. Do not change the apex domain or the existing main-site project.
3. In Workers & Pages, choose **Create application → Pages → Connect to Git** (wording may vary). Authorize only the required GitHub repository and select it. Use project name `wow-forever-android-addon-manager`, production branch `main`, framework preset **None**, no build command, output directory `site`, and repository root `/`. No environment variables are required.
4. Stop before **Save and Deploy** until production publishing is confirmed. Once confirmed, deploy and check the assigned `pages.dev` address for the correct content and stylesheet.
5. In the Pages project's **Custom domains**, choose **Set up a custom domain** and enter `addons.z3dlabs.id`. Stop before activating the domain or changing DNS until confirmed. If the zone is in the same Cloudflare account, review the proposed `addons` CNAME to the project's assigned `pages.dev` hostname. If DNS is hosted elsewhere, follow Pages' displayed verification and CNAME instructions there. Do not overwrite an existing record without resolving ownership and purpose.
6. Wait for domain validation and TLS activation. Verify https://addons.z3dlabs.id serves this page and `style.css`, and that https://z3dlabs.id remains unchanged. Only then mark production deployment verified here.

Network restrictions prevented review of the live parent website and official CurseForge terms during initial preparation. Styling was matched to the available parent source repository. Live comparison, current terms review, DNS inspection, GitHub publication, and deployment verification remain pending.

---

An independent, non-commercial project. Not affiliated with Blizzard Entertainment, CurseForge, or Overwolf.
