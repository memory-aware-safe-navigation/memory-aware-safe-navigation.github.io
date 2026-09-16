# Anonymous Academic Project Page (GitHub Pages)

Static site for **double-blind** review of:

> Memory-Aware Multi-Sensor Perception for Efficient and Safe Navigation in Dynamic Environments

**Authors on this page must remain: Anonymous Authors only.**

---

## Deploy to a burner GitHub Pages account

1. Create a **new / burner** GitHub account (do not use your real identity or known username).
2. Create a public repository, e.g. `anon-nav-web` (any non-identifying name).
3. Upload the contents of this folder to the **repository root** (so `index.html` is at `/` of the repo, not nested).
4. In **Settings → Pages**: set Source to **Deploy from a branch**, branch `main` (or `gh-pages`), folder `/ (root)`.
5. Wait for the Pages URL: `https://<burner-user>.github.io/<repo>/`.
6. Submit that URL for review. Keep the account and repo free of personal names, emails, affiliations, and prior commits that deanonymize you.

Optional: enable a custom domain only if it does not reveal identity.

---

## Where to drop assets

| Asset | Path |
|-------|------|
| Paper PDF | `static/pdfs/paper.pdf` (already included if copied) |
| Fig. 1 overview | `static/images/fig1_overview.svg` (or `.png`) |
| Fig. 2 simulation | `static/images/fig2_simulation.svg` |
| Fig. 3 trajectories | `static/images/fig3_trajectories.svg` |
| Fig. 4 hardware | `static/images/fig4_hardware.svg` |
| Teaser / sim / hardware videos | `static/videos/*.mp4` (see `static/videos/README.txt`) |
| Favicon | `static/images/favicon.svg` |

Placeholder SVGs ship in `static/images/`. Overwrite them with anonymized camera-ready figures. Do **not** include watermarks, lab logos, author faces, or institution names in media.

After dropping a teaser video, add a `<video>` tag in `index.html` pointing to `static/videos/teaser.mp4`.

---

## Anonymous code release (later)

For code, prefer an anonymous hosting option such as **[anonymous.4open.science](https://anonymous.4open.science/)** during review. Update the Code button only after the anonymous mirror is ready—**never** link a personal GitHub URL while under double-blind review.

---

## Anonymity grep checklist (run before publishing)

From the site root, search for forbidden identity tokens (prior-lab surnames, institution short name, prior GitHub handle, prior lab name). Example (split so this README itself stays clean):

```bash
# Reconstruct patterns locally; do not commit a filled-in copy of this command.
A='Xu'; B='e'          # prior first-author surname fragment
C='Figue'; D='roa'      # prior co-author surname
E='Pe'; F='nn'          # institution short name
G='yifan'; H='xueseas'  # prior GitHub handle
I='Figue'; J='roa Robotics'

rg -i "\\b${A}${B}\\b|\\b${C}${D}\\b|\\b${E}${F}\\b|${G}${H}|${I}${J}" .
```

Expected: **zero matches** in HTML/CSS/JS/Markdown/SVG (ignore third-party icon font false positives if any).

Also scan for your real name, email, lab, university, social handles, ORCID, and personal homepage URLs.

Additional checks:

- [ ] Meta tags use **Anonymous Authors**; `robots` is `noindex, nofollow`
- [ ] No Open Graph / Twitter cards with personal URLs
- [ ] No analytics (Statcounter, Google Analytics, etc.)
- [ ] No “More Works” / lab dropdown linking prior papers
- [ ] PDF and videos scrubbed of identifying metadata where feasible
- [ ] README / commit history on the burner repo do not reveal identity

---

## Local preview

Serve from the site root:

```bash
python3 -m http.server 8000
# open http://localhost:8000
```

---

## License

Page layout adapted from the Academic Project Page Template / Nerfies-style academic pages (CC BY-SA 4.0). Paper content remains with the anonymous authors pending acceptance.
