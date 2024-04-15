# charm-cache-test

Charmhub package name: operator-template
More information: https://charmhub.io/charm-cache-test

testing how this rebuilds with pip caching


---

Everything appears to work about the caching except for "pack charm from scratch" in build_with_cache.yaml.  I'd expect that to be <1 min, not 4 min.  I wondered if it was using charmcraft's default pip cache in /home/runner/snap/... and i dont see anything there.  But I can't explain why it otherwise wouldn't work

Next steps are maybe going via tmate to look for the cache dir and figure out why charmcraft isn't hitting the right one?  could be the environment variable isn't exporting right, or something else?
* could try `ENV_VAR=path charmcraft pack ...`

Strangely, when I changed the requirements.txt file [for this run](https://github.com/ca-scribner/charm-cache-test/actions/runs/8695225973/job/23845823082) I thought it would give me a new cache but it did not (still got a cache hit).  I thought it made a SHA from the requirements file.  what happened here?  
	* they did mention requirements.txt or pyproject.toml.  maybe it takes pyproject first?  ill try that