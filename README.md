# Cadet AI — privacy policy redirect

**This repository does not contain the privacy policy.** It serves one page,
[`index.html`](index.html), which redirects to the canonical policy:

> **https://cadetai.co.uk/privacy.html**

That URL, in the [website repository](https://github.com/Lowestofttim/cadet-ai-website),
is the single source of truth. Everything else points at it: the in-app Privacy
Policy screen, `docs/PRIVACY_POLICY.md` in the app repo, and the Google Play
**Data safety** policy URL.

## Why this repo still exists

The old GitHub Pages URL (`https://lowestofttim.github.io/cadet-ai-privacy/`) is
already published in places we do not control — Play Console history, in-app
links in builds users still have installed, and anywhere it has been linked. A
redirect keeps those working. Deleting the repo would break them.

## Do not add policy text here

This page used to be a full second copy of the policy, hand-synchronised with
the app repo and the website by following a paragraph of prose in this README.
Nothing checked it, so it drifted, and the two copies ended up disagreeing about
who the data controller is, whether a parent can get an under-13 an account, how
long TANGO chat history is kept, and which provider synthesises the voice
(audit finding **M-10**). For an app used by children that is not a
documentation problem: it is two competing normative privacy policies, and a
cadet, a parent, the ICO or a Play reviewer could reasonably read either as the
one that binds us.

`.github/workflows/policy-parity.yml` now fails the build if `index.html` grows
policy prose again. That gate is the point of this change — please do not
weaken it. If the policy needs to change, change it in the website repo, where
`scripts/validate-policy-contract.mjs` checks the wording against the controls
that are actually deployed.
