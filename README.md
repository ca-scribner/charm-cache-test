# charm-cache-test

Charmhub package name: operator-template
More information: https://charmhub.io/charm-cache-test

testing how this rebuilds with pip caching


---

Everything appears to work about the caching except for "pack charm from scratch" in build_with_cache.yaml.  I'd expect that to be <1 min, not 4 min.  I wondered if it was using charmcraft's default pip cache in /home/runner/snap/... and i dont see anything there.  But I can't explain why it otherwise wouldn't work