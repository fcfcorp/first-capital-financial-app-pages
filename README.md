# First Capital Financial Public App Pages

Standalone-ready static public pages for app store review and client help.

Required public URLs:

- `https://firstcapitalfinancial.xyz/privacy`
- `https://firstcapitalfinancial.xyz/support`
- `https://firstcapitalfinancial.xyz/account-deletion`

## Separate `fcfcorp` Repository Setup

1. Create a public repository while signed into the `fcfcorp` GitHub account.
2. Copy the contents of this `public-site` folder, including hidden `.github` and `.gitignore`
   files, into the new repository root.
3. Push the repository's `main` branch.
4. In **Settings > Pages**, set **Source** to **GitHub Actions**.
5. Confirm the `Deploy Public App Pages` workflow succeeds.
6. Configure the custom domain `firstcapitalfinancial.xyz` and its DNS records.

The included `.github/workflows/deploy-pages.yml` workflow publishes only the public app pages. It
explicitly excludes `admin-link-review/`, `README.md`, and host-specific `_headers`.

The included `.gitignore` also keeps `admin-link-review/` and `_headers` out of the new public
repository when files are added with Git.

The pages use relative asset and navigation links, so they work at both:

- `https://fcfcorp.github.io/<repository-name>/`
- `https://firstcapitalfinancial.xyz/`

Keep the authenticated admin link-review portal in a separately controlled deployment. Do not
publish it from the public app-pages repository.

For the mobile app environment, use:

```text
EXPO_PUBLIC_SUPPORT_EMAIL=support@firstcapitalfinancial.xyz
EXPO_PUBLIC_ACCOUNT_DELETION_URL=https://firstcapitalfinancial.xyz/account-deletion
```
