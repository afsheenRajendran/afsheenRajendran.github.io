---
layout: post
title:  "Spring Snippets"
date:   2025-04-10 18:02:01 -0500
---

- to get value of a property from application.properties and default to null
@Value("${primary.email:null}")

- to get value of a property from application.properties and default to empty list
@Value("#{${valid.stores} ?: T(java.util.Collections).emptyList()}")

- to get value of a property from application.properties and default to empty string
@Value("${banner.text} ?: T(org.apache.commons.lang3.StringUtils).EMPTY")

- Using Ternary
```
@Value("#{${valid.stores:null} ?: T(java.util.Collections).emptyList()}")
private List<String> validStores;
```

- Using @ConfigurationProperties
```
@ConfigurationProperties(prefix = "valid")
public class StoreConfig {
    private List<String> stores = Collections.emptyList();
}
```
