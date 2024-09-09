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

In earlier java versions that didn't have `Optional::stream`,
the above snippet might have looked like
```java
Optional<Other> result = things.stream()
        .map(this::resolve)          // maps thing to Optional<OtherThing>
        .filter(Optional::isPresent)
        .map(Optional::get)
        .findFirst();

```

### When collection-typed field could be null

```java
String itemTile = Optional.ofNullable(catalog.getItems())
        .stream()  // maps to stream of one object if optional exists, stream.empty otherwise
        .flatMap(Collection::stream) // converts stream of itemList to stream of individual items
        .findFirst()
        .map(Item::getTitle)
        .orElse(null);
```


