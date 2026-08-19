# Regen Registry — capital campaign

The funder-facing narrative site for the Regen Registry capital campaign.
Published at GitHub Pages from `index.html` on `main`.

**Do not edit `index.html` by hand.** It is generated.

- Master (internal, with the editorial record and open decisions):
  `regen/projects/registry-fundraise/registry-campaign-deck.html`
- Build: `python3 build-external.py` from that folder, then commit `site/index.html`.

The build strips everything internal — the open-decisions appendix, the editorial
record and its toggle, the section on multi-year projections that have not been
modelled, placeholder notes, "rights not yet cleared" markers, and the names of
developers who approached us unsolicited and have not consented to being named.

## Before circulating widely

The page carries `noindex`. Five partner photographs are not yet rights-cleared
(Terrasos, SeaTrees, Carboneg, Bromborough Estate, Sharamentsa). Clear them, or
remove them, before this is posted publicly or indexed.

## Custom domain

Add a `CNAME` file containing the hostname (e.g. `campaign.regen.network`) and
point a DNS CNAME at `regen-network.github.io`.
