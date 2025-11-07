<div align="center">

# Camoufox Python Interface

#### Lightweight wrapper around the Playwright API to help launch Camoufox.

</div>

> [!NOTE]
> All the the latest documentation is avaliable [here](https://camoufox.com/python).

---

## What is this?

This Python library wraps around Playwright's API to help automatically generate & inject unique device characteristics (OS, CPU info, navigator, fonts, headers, screen dimensions, viewport size, WebGL, addons, etc.) into Camoufox.

It uses [BrowserForge](https://github.com/daijro/browserforge) under the hood to generate fingerprints that mimic the statistical distribution of device characteristics in real-world traffic.

In addition, it will also calculate your target geolocation, timezone, and locale to avoid proxy protection ([see demo](https://i.imgur.com/UhSHfaV.png)).

---

## Installation

First, install the `camoufox` package:

```bash
pip install -U camoufox[geoip]
```

The `geoip` parameter is optional, but heavily recommended if you are using proxies. It will download an extra dataset to determine the user's longitude, latitude, timezone, country, & locale.

Next, download the Camoufox browser:

**Windows**

```bash
camoufox fetch
```

**MacOS & Linux**

```bash
python3 -m camoufox fetch
```

To uninstall, run `camoufox remove`.

---

## Troubleshooting

### GitHub API Rate Limits

If you see errors when running `camoufox fetch` or `python3 -m camoufox fetch`, you may be hitting GitHub's [API rate limits](https://docs.github.com/en/rest/using-the-rest-api/rate-limits-for-the-rest-api) (60 requests/hour without authentication).

**Solution:** Authenticate with a GitHub token to increase your rate limit to 5,000 requests/hour:

```bash
# Using GitHub CLI (recommended)
export GITHUB_TOKEN=$(gh auth token)
python3 -m camoufox fetch

# Or set permanently in your shell profile (~/.bashrc or ~/.zshrc)
export GITHUB_TOKEN=$(gh auth token)
```

For more details, see GitHub's documentation on [authenticating to the REST API](https://docs.github.com/en/rest/authentication/authenticating-to-the-rest-api).

---

<details>
<summary>CLI options</summary>

```
Usage: python -m camoufox [OPTIONS] COMMAND [ARGS]...

Options:
  --help  Show this message and exit.

Commands:
  fetch    Fetch the latest version of Camoufox
  path     Display the path to the Camoufox executable
  remove   Remove all downloaded files
  server   Launch a Playwright server
  test     Open the Playwright inspector
  version  Display the current version
```

</details>

<hr width=50>

## Usage

All of the latest documentation is avaliable at [camoufox.com/python](https://camoufox.com/python).
