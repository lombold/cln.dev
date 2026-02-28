+++
title = 'Mocking Dates in Java'
date = 2026-06-15T18:33:11+02:00
draft = true
version = 1
author = 'Colin'
categories = ['Java', 'Testing', 'Mockito']
+++

# How to Mock Dates in Java in existing lagecy codebases

=> Most legacy codebases rely heavily on `new Date()`, `System.currentTimeMillis()`, or `LocalDate.now()` to get the current date and time. This makes it difficult to write tests that depend on specific dates or times, as you cannot easily control the output of these methods.

=> Let's statically mock them within your test with this helper:

```java


```