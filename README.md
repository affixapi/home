# home

[![release](https://github.com/pay-api/home/actions/workflows/release.yml/badge.svg)](https://github.com/pay-api/home/actions/workflows/release.yml)

## instructions to deploy a new version

Vist: <https://www.notion.so/pay-api/pay-api-973e2cf1cacb4c83a3743917ac727225>

export -> unzip -> move file into `public/` -> rename `index.html`

export options:
- export format: html
- include content: everything
- include subpages: true

### add favicon

in the `<head>` tag, add this:

```html
<html><head><meta http-equiv="Content-Type" content="text/html; charset=utf-8"/><title>pay-api</title><style>
```
note added favicon:

```html
<html><head><meta http-equiv="Content-Type" content="text/html; charset=utf-8"/><title>pay-api</title><link rel="icon" type="image/png" href="favicon.png"><style>
```

### links
- favicon generator: <https://favicon.io/favicon-converter/>
