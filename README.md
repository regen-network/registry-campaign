# Regen Registry — capital campaign

Two surfaces, one source. **Never edit `index.html` by hand — it is generated.**

| | Audience | Built by | Hosted |
|---|---|---|---|
| **This repo** | Funders, external | `build-external.py` | GitHub Pages — https://regen-network.github.io/registry-campaign/ |
| `../site-internal/` | Becca, David, Gregory | `build-internal.py` | Cloudflare Pages, behind Cloudflare Access |

Source of truth for both is the master fragment:
`regen/projects/registry-fundraise/registry-campaign-deck.html`

## Updating

```sh
cd ~/regen/projects/registry-fundraise

# funder-facing
python3 build-external.py
cd site && git add index.html && git commit -m "…" && git push

# internal
python3 build-internal.py
npx wrangler pages deploy site-internal --project-name=registry-campaign-internal
```

`build-external.py` strips everything internal — the open-decisions appendix, the
editorial record and its toggle, the crossover section whose projections have not
been modelled, placeholder notes, "rights not yet cleared" markers, and the names
of developers who approached us unsolicited and have not consented to being named.
It fails loudly if an edit upstream breaks one of its anchors, so a change to the
master cannot silently leak onto the public site.

The internal build strips nothing and must never be committed here.

## Before circulating widely

This page carries `noindex`, but it is public — anyone with the URL can read it.
Five partner photographs are not yet rights-cleared (Terrasos, SeaTrees, Carboneg,
Bromborough Estate, Sharamentsa). Clear them, or remove them, before this is posted
publicly or linked from anywhere indexed.

## Custom domain

Add a `CNAME` file containing the hostname (e.g. `campaign.regen.network`) and point
a DNS CNAME at `regen-network.github.io`. `regen.network` DNS is on NS1, not
Cloudflare, so that record is added there.
