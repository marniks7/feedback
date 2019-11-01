
## Revisiting Effective Java in 2019
### What it was about?
- Take  latest 'Effective Java' book and read it once again
- Objects.hash, Objects.equals - boxing problem in case of using primitives
- Objects.hash, Objects.equals - array creation
- Abstract methods in enums with lambda expressions or method references
(example: enum with add \ substract \ multiple methods)

### How this talk influence to me (or to my teammates \ company)?
- The microservice i am currently working on doesn't care about low-level performance (and will never care).
- For other microservices i was working previously it might be useful to check hashCode\equals implementations
- However, Objects.hash\equals problem is Java as a language\library problem and in ideal world i should not take care about that. In real world, looks like it is better to avoid using those methods by default.
- About book - i was reading this book many-many years ago (previous editions).
Personally, it is nice to have it, but there are so many other useful things (books\topics) and i believe they are more important now.


## Pain and gain of introducing Kafka in Microservices architecture at eBay
### What it was about?
- architecture patterns they have used to solve some (unknown) problems or how they build there microservices
- business functionality - listings (as example - car selling)
- all interprocess communication (or almost all) between microservices were using kafka topics \ streams
- for different features of the listing they have used different microservices 
- they have used one microservice for aggregation (listings and features of listings)
- aggregation is implemented as left joins in kafka streams
- looks like they have used [CDC](https://en.wikipedia.org/wiki/Change_data_capture) from mysql to kafka cause they still use monolith.
(to avoid problems with consistency).
- in case in processing failure they have used DLQ pattern (new queues - 4hours \ 16 hours \ manual DLQ)
- as well they have described something about different data centers usage with kafka
- somehting was about replicas

### Other staff
- they have ~20M users monthly. how many events do they have daily \ in a peak?
- Migrations?
- Versioning - new kafka streams for new versions (without details, it was a answer to question)
- Backward compatibility (versioning) was resolved in application.
- Tracing - no common approach

### How this talk influence to me (or to my teammates \ company)?
- You can see that it is not very clear for me what they got. 
- I believe it is required to redevelop their presentation and talk - start from the problem first and on each new step describe problem
- Definitely, i would like to listen to their updated talk. Maybe i should find them and ask additional questions.
