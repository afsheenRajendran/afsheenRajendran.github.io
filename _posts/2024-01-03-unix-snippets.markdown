---
layout: post
title:  "UNIX Snippets"
date:   2024-01-03 22:02:01 -0500
---


- using `find` command to find files that contain both given strings
  `find . -type f -exec grep -l 'string1' '{}' \; | xargs -d '\n' grep -l 'string2’`

- to count occurrences
  `find . -type f -name "*.java" | xargs grep -c Assert.assert | grep -v :0`

- sed (from grymoire) -E ensures that '+' is considered as extended regexp
  `sed -E 's/([a-z]+) ([a-z]+)/\2 \1/'` # Using Apple Mac OS X

- One method of combining multiple commands is to use a -e before each command:
  `sed -e 's/a/A/' -e 's/b/B/' <old >new`

