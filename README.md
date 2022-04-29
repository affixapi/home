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
</style></head><body><article id="973e2cf1-cacb-4c83-a374-3917ac727225" class="page sans"><header><img class="page-cover-image" src="https://images.unsplash.com/photo-1535136104956-115a2cd67fc4?ixlib=rb-1.2.1&amp;q=85&amp;fm=jpg&amp;crop=entropy&amp;cs=srgb" style="object-position:center 50%"/><h1 class="page-title">pay-api</h1></header><div class="page-body"><p id="c50bb4aa-0444-4131-906f-57afb7b9e913" class=""><a href="https://docs.pay-api.link">docs</a></p><p id="0ed652ad-0496-41bf-bc4c-73c5f2b6b6eb" class=""><a href="https://www.npmjs.com/package/@pay-api/api">sdk</a></p><p id="4a3b4acd-b2ae-455a-8aa4-bcdf647cad79" class=""><a href="https://signup.pay-api.link">signup / register</a></p><p id="e89c0319-d8e4-4c93-aad5-1997182d4d20" class=""><a href="https://status.pay-api.link">status</a></p><p id="7cd0fb11-b80c-430f-ac08-0407c42ed4e2" class=""><a href="https://www.linkedin.com/in/skilbeck/">author</a></p><p id="dea0ee1b-4bd9-4c45-b185-a87fa420a10e" class="">
</p><p id="32ad4780-be3a-40ef-ab55-ae0768af2a3d" class="">
</p><figure id="623a482a-c65c-4d5a-af29-e424c89b3543" class="image"><a href="pay-api%20623a482ac65c4d5aaf29e424c89b3543/Word__logo.svg"><img style="width:672px" src="pay-api%20623a482ac65c4d5aaf29e424c89b3543/Word__logo.svg"/></a></figure></div></article></body></html>
```

```html
</style></head><body><article id="973e2cf1-cacb-4c83-a374-3917ac727225" class="page sans"><header><img class="page-cover-image" src="photo-1535136104956-115a2cd67fc4.jpeg" style="object-position:center 50%"/><h1 class="page-title">pay-api</h1></header><div class="page-body"><p id="c50bb4aa-0444-4131-906f-57afb7b9e913" class=""><a href="https://docs.pay-api.link">docs</a></p><p id="0ed652ad-0496-41bf-bc4c-73c5f2b6b6eb" class=""><a href="https://www.npmjs.com/package/@pay-api/api">sdk</a></p><p id="4a3b4acd-b2ae-455a-8aa4-bcdf647cad79" class=""><a href="https://signup.pay-api.link">signup / register</a></p><p id="e89c0319-d8e4-4c93-aad5-1997182d4d20" class=""><a href="https://status.pay-api.link">status</a></p><p id="8fcb7a45-561c-4b03-b8bc-e41d69f413c6" class=""><a href="https://pay-api.link/privacy">privacy</a></p><p id="7cd0fb11-b80c-430f-ac08-0407c42ed4e2" class=""><a href="https://www.linkedin.com/in/skilbeck/">author</a></p><p id="dea0ee1b-4bd9-4c45-b185-a87fa420a10e" class="">
</p><p id="32ad4780-be3a-40ef-ab55-ae0768af2a3d" class="">
</p><figure id="623a482a-c65c-4d5a-af29-e424c89b3543" class="image"><a href="Word__logo.svg"><img style="width:672px" src="Word__logo.svg"/></a></figure></div></article></body></html>
```

note that the `<a src>` attribute changed to `src="Word__logo.svg"` (hosted locally),
as well as `<img class="page-cover-image" src="https://images.unsplash.com/photo-1535136104956-115a2cd67fc4?..."` to `<img class="page-cover-image" src="photo-1535136104956-115a2cd67fc4.jpeg"` (also hosted locally)

## privacy policy + terms of service

### privacy policy
- username: john.skilbeck+termly@gmail.com
- <https://app.termly.io/dashboard/website/5f27a0c8-1f5f-43c4-afb1-c4a2141c1847/privacy-policy>
- add to website -> html format -> paste to public/privacy.html

### terms of service
- username: john.skilbeck+termly2@gmail.com
- <https://app.termly.io/dashboard/website/599acae1-0ea2-42f1-b5f9-22ef47e80fae/terms-of-service>

## links
- favicon generator: <https://favicon.io/favicon-converter/>
