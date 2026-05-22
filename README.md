# Web-Proxy
[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)

English | [简体中文](README.zh-CN.md)

## Introduction
Web-Proxy is a lightweight web proxy running on Cloudflare edge nodes.
It supports both Cloudflare Workers and Cloudflare Pages (Advanced Mode).

## Project Structure
- `worker.js`: Worker entry for Cloudflare Workers (Module Worker format)
- `WebProxy/_worker.js`: Worker entry for Cloudflare Pages (Advanced Mode)
- `LICENSE`: Apache License 2.0 text
- `NOTICE`: Attribution notices

## Quick Start
1. Fork or clone this repository.
2. Choose your deployment target:
   - Workers: use `worker.js`
   - Pages: use `WebProxy/_worker.js`
3. Deploy and open your domain.
4. Verify with `/works` and expect `it works`.

## Deploy

### Option A: Cloudflare Workers
1. Open [Cloudflare Workers](https://workers.cloudflare.com).
2. Create a Worker.
3. Copy the content of `worker.js` to the editor.
4. Save and deploy.
5. Open your `*.workers.dev` URL and test `/works`.

### Option B: Cloudflare Pages (Advanced Mode)
1. Create a Pages project from this repository.
2. Set the publish directory to `WebProxy`.
3. Make sure the worker entry is `WebProxy/_worker.js`.
4. Deploy and test `/works`.

## Notes
- This project uses Module Worker format.
- In Pages Advanced Mode, the filename should be `_worker.js` (singular).
- Keep `worker.js` and `WebProxy/_worker.js` behavior aligned when updating logic.

## Troubleshooting
- Deployment succeeds but routing fails: check project root and publish directory settings.
- 400/403 from proxy path: verify request parameters and referer flow.
- Static resources fail: check upstream availability and target URL path.

## License
This project is licensed under the **Apache License, Version 2.0**.

See the [LICENSE](LICENSE) file for the full license text.
For additional attribution notices, please see the [NOTICE](NOTICE) file.
