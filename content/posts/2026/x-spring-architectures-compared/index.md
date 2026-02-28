+++
title = 'Spring Archtitectures Compared'
date = 2025-06-15T18:33:11+02:00
draft = true
version = 1
author = 'Colin'
categories = ['Spring', 'Architecture', 'Clean Architecture', 'Hexagonal Architecture', 'Onion Architecture']
+++

Why
* separation of concerns => domain logic independent of framework
* testability => easier to write unit tests for domain logic
* maintainability => easier to modify and extend the application over time
* (flexibility => easier to switch frameworks or technologies without affecting domain logic)

Common Principles
* Dependency Rule
* Policies vs. Details "UI is a detail"

(data-access changes every 3 years Palermo2008) => not applicable today

Alistair Cockburn has written a bit about Hexagonal architecture.  Hexagonal architecture and Onion Architecture share the following premise:  Externalize infrastructure and write adapter code so that the infrastructure does not become tightly coupled.

Comparison Timeline
1970s - Layered Architecture - e.g., Presentation, Business Logic, Data Access
2003 - Domain-Driven Design - Eric Evans - emphasized the importance of focusing on the core domain and domain logic.
2005 - Hexagonal Architecture - Alistair Cockburn
2008 - Onion Architecture - Jeffrey Palermo
2012 - Clean Architecture - Robert C. Martin
