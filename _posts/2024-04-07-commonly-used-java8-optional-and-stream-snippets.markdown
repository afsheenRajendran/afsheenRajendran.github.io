---
layout: post
title:  "Commonly Used Optional and Stream Snippets in Java"
date:   2024-04-08 22:02:01 -0500
---


### Going from one type to another in an Optional chain

```java
Optional<Other> result = things.stream()
        .map(this::resolve)          // maps thing to Optional<OtherThing>
        .flatMap(Optional::stream)   // equivalent to get if value is present
        .findFirst();

```

### When collection-typed field could be null

```java
String itemTile = Optional.ofNullable(catalog.getItems())
        .stream()
        .flatMap(Collection::stream)
        .findFirst()
        .map(Item::getTitle)
        .orElse(null);
```


