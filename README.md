

----------------------------
2024.08.20
----------------------------

jekyll site doesn't look good

- github was not allowing even PRs on `main`, 
so removed the ruleset and all protections




----------------------------
2024.05.22
----------------------------
docs % pwd
/Users/afsheen/Documents/workspace/afsheenRajendran.github.io/docs

```
docs % bundle exec jekyll serve
Configuration file: /Users/afsheen/Documents/workspace/afsheenRajendran.github.io/docs/_config.yml
To use retry middleware with Faraday v2.0+, install `faraday-retry` gem
Source: /Users/afsheen/Documents/workspace/afsheenRajendran.github.io/docs
Destination: /Users/afsheen/Documents/workspace/afsheenRajendran.github.io/docs/_site
Incremental build: disabled. Enable with --incremental
Generating...
Jekyll Feed: Generating feed for posts
GitHub Metadata: No GitHub API authentication could be found. Some fields may be missing or have incorrect data.
Build Warning: Layout 'page' requested in about.markdown does not exist.
Build Warning: Layout 'home' requested in index.markdown does not exist.
done in 0.44 seconds.
Auto-regeneration: enabled for '/Users/afsheen/Documents/workspace/afsheenRajendran.github.io/docs'
Server address: http://127.0.0.1:4000/docs/
Server running... press ctrl-c to stop.
```
----------

then hitting http://127.0.0.1:4000/docs/ worked

