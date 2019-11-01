## Revisiting Effective Java in 2019
### What it was about?
- Take  latest 'Effective Java' book and read it once again
- Objects.hash, Objects.equals - boxing problem in case of using primitives
- Objects.hash, Objects.equals - array creation
- Abstract methods in enums with lambda expressions or method references
(example: enum with add \ substract \ multiple methods)
- Free book 'Migrating to Microservice Databases'

### How this talk influence to me (or to my teammates \ company)?
- The microservice i am currently working on doesn't care about low-level performance (and will never care).
- For other microservices i was working previously it might be useful to check hashCode\equals implementations
- However, Objects.hash\equals problem is Java as a language\library problem and in ideal world i should not take care about that. In real world, looks like it is better to avoid using those methods by default.
- About book - i was reading this book many-many years ago (previous editions).
Personally, it is nice to have it, but there are so many other useful things (books\topics) and i believe they are more important now.
- Book content is: zero downtime, evolving your relational database, crud\cqrs, integration strategies. Looks like very useful.
PersonalAI: for sure, read it!
TeamAI: read it and share knowledge with teammates or just recommend book