# Public pages for the App Store record

App Store Connect requires a public Support URL and Privacy Policy URL. This folder holds exactly two pages,
`privacy.html` (copied from pwa/privacy.html, regenerate after any privacy change) and `support.html`
(rendered from SUPPORT.md), plus an index redirect. Publishing these does not publish the code.

To publish as a small separate GitHub Pages site (one command, when the operator says "publish pages"):

    cd ~/projects/Be-20260908/ios/appstore/site && git init -q && git add -A && git commit -qm "Be support and privacy pages" \
      && gh repo create be-support --public --source=. --push \
      && gh api -X POST repos/{owner}/be-support/pages -f build_type=legacy -f 'source[branch]=main' -f 'source[path]=/'

URLs then are https://<account>.github.io/be-support/support.html and .../privacy.html. The account shown is the
GitHub handle, not a legal name.
