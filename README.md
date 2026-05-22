# braces-for-feet-lander

One-page lander for **Braces for Feet** — custom orthotic insoles, scanned by iPhone LiDAR, refined by feedback, shipped quarterly.

Companion site to [BimRoss/braces-for-feet](https://github.com/BimRoss/braces-for-feet) (the iOS scan app).

## Layout

- `index.html` — the whole site, single file, no framework. Google Fonts (Fraunces / Spectral / JetBrains Mono) via CDN.
- `Dockerfile` — `nginx:1.27-alpine` serving `index.html`.
- `.github/workflows/build.yml` — builds on every push to `main`, pushes `geeemoney/braces-for-feet-lander:{version,latest}` to Docker Hub on `v*` tags.

## Local preview

```sh
open index.html
# or
docker build -t braces-for-feet-lander . && docker run --rm -p 8080:80 braces-for-feet-lander
```

## Release

```sh
git tag v0.1.0 && git push --tags
```

CI builds and publishes the image. Deploy is handled out of cluster manifests.

## Posture

Wellness program. Not a medical device. No FDA claims (Phase 1).
