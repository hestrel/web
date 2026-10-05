# Hestrel website

Minimal black-and-white static HTML site. No build, JavaScript, or external assets.

## Preview

Run `python3 -m http.server 8080` in this directory and open http://localhost:8080.

## GitHub Pages

In `hestrel/hestrel.github.io` → Settings → Pages, select **GitHub Actions** as the source. Push to `main` or run the Deploy GitHub Pages workflow. The workflow publishes only the HTML, CSS, and `.nojekyll` file.

Expected URLs after deployment:

- Homepage: https://hestrel.github.io/
- Privacy policy: https://hestrel.github.io/privacy.html
- Terms: https://hestrel.github.io/terms.html
- Support: michaljach@gmail.com

## Google OAuth verification

This repository supplies the website portion of verification, not Google approval. Before submitting:

1. Deploy the site and confirm all three URLs are publicly accessible without sign-in.
2. Use **Hestrel** as the consent-screen app name, the support email above, and the deployed URLs. Include developer contact details in Google Auth Platform.
3. Verify ownership of the website domain in Google Search Console using an account associated with the Google Cloud project. GitHub Pages hosting alone does not establish domain ownership. If Google cannot verify or accept the `hestrel.github.io` subdomain, attach a domain you own to Pages, verify that domain, and update the consent-screen URLs. Do not claim ownership of `github.io` itself. No verification token is included because Google must issue it for your property.
4. Declare the scopes the iOS app actually requests: `https://www.googleapis.com/auth/gmail.readonly`, `https://www.googleapis.com/auth/calendar.readonly`, `https://www.googleapis.com/auth/drive.readonly`, plus the basic identity scopes requested by Google Sign-In. Justify each scope and provide a demonstration of the consent flow and features. Gmail and Drive read-only access require restricted-scope review; a security assessment may also apply depending on data handling and applicable exceptions.
5. Review the privacy policy against production behavior before publishing it. Its Limited Use and no-generalized-model-training statements are commitments: verify every configured AI provider's retention, training, and transfer terms, and ensure app controls and user disclosures enforce those commitments. Arbitrary user-configured providers cannot be assumed compliant. Confirm operator identity, deletion/backup retention, support handling, and any additional production processors or logs; update the policy if needed.
6. Complete brand verification and any sensitive/restricted-scope verification in Google Auth Platform. A website alone does not satisfy the app's consent, data handling, or security obligations.

The copy follows the adjacent iOS app's read-only Google integration and the Cloudflare account/sync service. Google data included in chats can reach the selected model provider and account sync; the policy intentionally discloses both.

Official references:

- https://developers.google.com/identity/protocols/oauth2/production-readiness/brand-verification
- https://developers.google.com/identity/protocols/oauth2/production-readiness/restricted-scope-verification
- https://developers.google.com/terms/api-services-user-data-policy
