## Backend For Frontend: The Missing Manual
### What it was about?
- it was short notes what should be used, mostly without details
- use gzip
- use http2
- count of parallel connections is limited to 4 in case of usage http1.1?
- swagger and open specification
- api first principle
- [event source](https://developer.mozilla.org/en-US/docs/Web/API/Server-sent_events/Using_server-sent_events) protocol with http2
- check [brotli](https://github.com/google/brotli) compression algorithm
- use [Etag](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/ETag)
- rest or websockets - use one approach to avoid race conditions
(read all through rest and then get events by websockets)
- [dredd](https://dredd.org) - HTTP API Testing Framework

### How this talk influence to me (or to my teammates \ company)?
- gzip - don't hurry with gzip for all requests, even for client-server communication. 
Just measure response time with and without.
Don't forget to check cpu usage for zip\unzip at least on server side.
Take into consideration that client device cpu can be slow (however i didn't measure client side unzip\zip time). 
For web application i was working on (with our specific payload) gzip was not turned on cause of higher response time.
It was higher in few times.

- http2 - it is not clear how much it increase performance. 
PersonalAI: investigate it, find measurement. On the moment I am interested in http2 for rest apis for interprocess 
communication between microservices.
As well it could be one of the reason to use java11 with their new http client.
(IMHO, Spring's RestTemplate syntax is ugly,
WebClient has nice syntax, but it is better for reactive applications - we got in trouble with it in blocking application)

- about count of parallel connections - it is possible to use different domain names. 
As well i believe that for different browsers the limit is different, they don't follow the standard. 
I came up to this conclusion few years ago. 
Currently, i am not working with client-server communication with images\css and other resources. 

- swagger and open specification - yes, i am using it with many details.
TeamAI: Motivate other teams to share more details in open specification

- api first principle - yes, very nice one. 
On the moment i ask in review to show request \ response and all the details. But it is not yet 'api first principle'.

 - event source protocol in browser - read about it or keep in mind when it will be required to implement frontend
 
 - brotli - ok, maybe later i will check
 
 - Etag - it looks like very useful for resources (js\css\images) when they are not changed. 
 Allows to avoid data exchange, which might be big. 
 [Stackoverflow Etag vs Expires](https://stackoverflow.com/questions/499966/etag-vs-header-expires)
 I didn't know about that when i was working on portal performance, just about other caching staff.
 
 - rest or websockets - didn't work on this problem.
 
 - dredd - TBD
 
 `PersonalActionItem`: use 'api first principle' as a practice.
 
 `TeamActionItem`: Share API First Principle with other teams and follow it as a practice, not sometimes.
  