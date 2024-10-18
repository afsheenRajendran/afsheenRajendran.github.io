---
layout: post
title:  "UNIX Snippets"
date:   2024-01-03 22:02:01 -0500
---


- using `find` command to find files that contain both given strings
```
  find . -type f -exec grep -l 'string1' '{}' \; | xargs -d '\n' grep -l 'string2’
```

- to count occurrences
```
  find . -type f -name "*.java" | xargs grep -c Assert.assert | grep -v :0
```

- sed (from grymoire) -E ensures that '+' is considered as extended regexp 
```
  sed -E 's/([a-z]+) ([a-z]+)/\2 \1/'` # Using Apple Mac OS X
```

- One method of combining multiple commands is to use a -e before each command:
```
  sed -e 's/a/A/' -e 's/b/B/' <old >new
```

- jq (for json wrangling)
  sorts json blocks based on `key` variable
```
  jq '.values|=sort_by(.key)' local.postman_environment.json > local_updated
```



## Useful GIT Commands

- to restore file to version in master
```
git restore --source origin/master OnlyCashService.java
```

- to copy single file from some other branch to current working directory
```
git restore --source some-other-branch service-client/src/test/java/com/afsheen/some.java
```

- to revert last un-pushed commit
```
git reset --soft HEAD~1
```

- to revert last pushed commit
```
git reset --hard HEAD~1
```

- to compare file across two commits
```
git diff f04082f6..2b5282cc ExternalServiceIntegration.java
```
