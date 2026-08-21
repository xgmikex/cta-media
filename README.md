# cta-media

Media host for CTA Roofing social scheduling. Run by Fixe Media.

## What this is for

Buffer's API has no upload mutation. Every asset field — image, video,
document — takes a public URL and nothing else. This repo is that URL.

Finished post assets get pushed here, and Buffer fetches them by
`raw.githubusercontent.com` link when the post is created. That is the only
reason this repo exists.

## Layout

```
YYYY-MM/<post id>/<file>
```

For example:

```
2026-08/C010/C010_influencer-clapback_ALL_reel.mp4
```

which is served at:

```
https://raw.githubusercontent.com/xgmikex/cta-media/main/2026-08/C010/C010_influencer-clapback_ALL_reel.mp4
```

## Rules

**This repo is public.** It has to be. Raw URLs on a private repo need an auth
header and Buffer cannot send one.

**Finished social assets only.** Things that are about to be published publicly
anyway. Never contracts, credentials, client documents, invoices, or raw job
media that has not been cleared for publication.

**Deleting a file does not erase it.** Git keeps the blob in history and this
repo does not rewrite history. Assume anything committed here is permanent and
public. If that is not acceptable for a given file, it does not belong here.

**Prune the working tree.** Video is heavy. Once a month's posts have all gone
live, delete that month's folder so the checkout stays small.

## Source of truth

The assets themselves are built and kept in the client folder on George's Mac
under `Claude/Clients/CTA Roofing/03_Content/`. This repo is a delivery
mechanism, not an archive. If the two ever disagree, the client folder wins.
