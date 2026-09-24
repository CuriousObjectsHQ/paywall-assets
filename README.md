# paywall-assets

Static images served over the [jsDelivr](https://www.jsdelivr.com/) CDN for
Curious Objects paywalls and marketing.

> [!WARNING]
> **Everything here is public, permanent, and cannot be deleted.**
> The repo is world-readable, git keeps history forever, and pinned jsDelivr
> URLs are cached for about a year and cannot be purged. Assume anything
> committed here is public the moment it is pushed, for good.

## What belongs here

Assets we own or are licensed to use: paywall images, logos, icons,
email-template images, landing illustrations, documentation screenshots.

## What must never go here

- User-uploaded or customer content. jsDelivr's acceptable-use policy bans
  using it as an image host for uploads, and blocks repos that do.
- Screenshots containing real user data, emails, tokens, API keys, or
  internal URLs.
- Anything that might need to be deleted later.
- Videos, backups, or bulk media.
- Third-party images we do not have rights to.

## URLs

Always pin to a full commit SHA:

```
https://cdn.jsdelivr.net/gh/CuriousObjectsHQ/paywall-assets@<sha>/<path>
```

Never use `@main`, `@latest`, a bare `@`-less URL, or `raw.githubusercontent.com`.
Those are cached for hours to days and can serve changed content; the whole
point of a pinned SHA is that the bytes behind a URL never change.

To replace an image, commit the new version and hand out the URL with the new
SHA. Old URLs keep serving the old image, which is what makes a published
paywall safe.

## Layout

```
<project-or-brand>/<purpose>/<name>[-<width>w|@2x].<ext>
```

Lowercase, kebab-case, no spaces. Examples:

```
fujipic/paywall/hero-1600w.webp
parceler/paywall/logo@2x.png
```

## Limits

| Limit | Value |
| --- | --- |
| Single file | 20 MB (jsDelivr) |
| Repo contents at a commit | 150 MB |

Practical targets: paywall images under 500 KB, email images under 200 KB.
Compress before committing.

---

Uploads are normally made through Paywall Studio (`pw_upload_asset` or the
editor's image button), which compresses, commits, pins the SHA, and adds
`cdn.jsdelivr.net` to the project's asset allowlist. See CUR-902.
