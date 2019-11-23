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
- something was about replicas

### Other
- they have ~20M users monthly. how many events do they have daily \ in a peak?
- Consistency - eventual
- Data Migration?
- Versioning - new kafka topics? for new versions (without details, it was a answer to question)
- Backward compatibility (versioning) was resolved in application.
- Tracing - no common approach
- Availability - replicas of aggregate service for reads?
- Reliability?
- Event duplication? not needed?
- Locking Strategy?

### How this talk influence to me (or to my teammates \ company)?
- You can see that it is not very clear for me what they got. 
- I believe it is required to redevelop their presentation and talk - start from the problem first and on each new step describe problem
- Definitely, i would like to listen to their updated talk. Maybe i should find speakers and ask additional questions.
- In compare, here is great talk about another architecture - https://jokerconf.com/2019/talks/4wj9og0tij3wpxe3ourovr/ (in russian)
