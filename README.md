# home

[![release](https://github.com/pay-api/home/actions/workflows/release.yml/badge.svg)](https://github.com/pay-api/home/actions/workflows/release.yml)

## instructions to deploy a new version

1. Vist: <https://www.notion.so/pay-api/pay-api-973e2cf1cacb4c83a3743917ac727225>

2. make the respective changes

3. ellipsis -> export (see options below) -> unzip -> move file into `public/` -> rename `index.html`

export options:
- export format: html
- include content: everything
- include subpages: true

## detailed example for diffs/how to edit:

go to `dev-resources/sample-diffs` dir

run `vimdiff index.html pay-api-623a482ac65c4d5aaf29e424c89b3543.html`

notice the diff is:

- favicon (make sure to keep favicon; was added manually by me)
- tabs vs spaces (unimportant)
- html content diff (see below)
- image loading location (moved to host via github, faster latency)

html content diff:

```html
<p id="0ed652ad-0496-41bf-bc4c-73c5f2b6b6eb" class=""><a href="https://www.npmjs.com/package/@pay-api/api">sdk</a></p>
```

so you want to add this to `public/index.html`

choices are:
- insert manually (likely easier)
- take notion's version, and just add the two manual edits:
-- favicon
-- image loading location points to local version

the two manual edits can possibly be scripted, along with the automating of the
export / unzip from notion, but tbh not many changes atm.

## verifying changes before deploy

easy,

```bash
open public/index.html
```

## add favicon

in the `<head>` tag, replace this line:

```html
<html><head><meta http-equiv="Content-Type" content="text/html; charset=utf-8"/><title>pay-api</title><style>
```
with this:

```html
<html><head><meta http-equiv="Content-Type" content="text/html; charset=utf-8"/><title>pay-api</title><link rel="icon" type="image/png" href="favicon.png"><style>
```

note added `<link rel="icon" type="image/png" href="favicon.png">`, which adds the favicon

## image sourced from github pages (faster latency)

at the very end of the `html`, replace

```html
</p><figure id="623a482a-c65c-4d5a-af29-e424c89b3543" class="image"><a href="pay-api%20623a482ac65c4d5aaf29e424c89b3543/Word__logo.svg"><img style="width:672px" src="pay-api%20623a482ac65c4d5aaf29e424c89b3543/Word__logo.svg"/></a></figure></div></article></body></html>
```

```html
</p><figure id="623a482a-c65c-4d5a-af29-e424c89b3543" class="image"><a href="Word__logo.svg"><img style="width:672px" src="Word__logo.svg"/></a></figure></div></article></body></html>
```

note that the `<a src>` attribute changed to `src="Word__logo.svg"` (hosted locally)

## links
- favicon generator: <https://favicon.io/favicon-converter/>
