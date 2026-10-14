# ByteHma Personal Drive Backup — OAuth information site

This repository hosts a small, **public, static information site** for a **personal rclone-based Google Drive backup connector**. It contains no backup data, OAuth client secrets, access tokens, encryption passwords, or cloud integration code.

**This is not an authentication callback, web application, or backup destination.** The actual transfers and encryption happen locally on the owner's computer using separately configured backup tools.

## GitHub Pages setup

1. Open [Repository → Settings → Pages](https://github.com/ByteHma/symmetrical-octo-couscous/settings/pages).
2. Under **Build and deployment**, choose **Deploy from a branch**.
3. Select branch **`master`**, folder **`/(root)`**, then **Save**.
4. After GitHub deploys, open these public URLs:
   - Home: https://bytehma.github.io/symmetrical-octo-couscous/
   - Privacy: https://bytehma.github.io/symmetrical-octo-couscous/privacy.html
   - Terms: https://bytehma.github.io/symmetrical-octo-couscous/terms.html

If GitHub changes the repository's default branch, choose the branch actually containing `index.html`.

## Google Auth Platform configuration

Open [Google Auth Platform → Branding](https://console.cloud.google.com/auth/branding) **in the Cloud project for the existing rclone OAuth desktop client**.

- **App name:** use the actual name of that OAuth client. The site uses *ByteHma Personal Drive Backup* as a descriptive site title; adjust the site's title if the OAuth brand substantially differs.
- **User support email:** your own email, entered in Google Console (not in this public repository).
- **Application home page:** `https://bytehma.github.io/symmetrical-octo-couscous/`
- **Application privacy policy link:** `https://bytehma.github.io/symmetrical-octo-couscous/privacy.html`
- **Terms (if required):** `https://bytehma.github.io/symmetrical-octo-couscous/terms.html`
- **Authorized domain:** follow the actual Google Console instructions for the site's host. Do not invent domain ownership or attempt to verify a domain you do not own.

Go to [Audience](https://console.cloud.google.com/auth/audience) and check whether **Publish app** becomes available. GitHub Pages does **not** guarantee that Google's independent domain verification requirements will accept a shared `github.io` host. If Google requests ownership verification that cannot be satisfied, stop and resolve that requirement legitimately.

For a personal account, use **External** audience, not Workspace-only **Internal**. Keep the currently working rclone `drive.file` scope; publishing the website does not change your rclone token. After publication, reauthorize the existing remote *only if needed*, without changing its remote name or scope. Verify restore capability separately.

## Site contents

- `index.html` — homepage, scope and data-flow explanation
- `privacy.html` — Google user data privacy disclosure
- `terms.html` — intended use and limitations
- `assets/site.css` — local styles, no JavaScript, external fonts, analytics, or tracking
- `.nojekyll` — publish static files as-is

All links and styles are relative so the project site works at `/symmetrical-octo-couscous/`.

## Keeping this accurate

This site describes a **personal** setup, using rclone on the owner's device and the restricted Google Drive `drive.file` scope. If access scopes, storage destinations, encryption behavior, collection, or sharing change, update the public privacy policy **before** relying on it in production. Do not publish sensitive logs or credentials.

This repository is independently hosted by GitHub Pages and is not affiliated with Google or rclone.

## Helpful documentation

- [GitHub Pages publishing source](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site)
- [rclone Google Drive OAuth setup](https://rclone.org/drive/#making-your-own-client-id)
- [Google OAuth user data policy](https://developers.google.com/identity/protocols/oauth2/policies)
