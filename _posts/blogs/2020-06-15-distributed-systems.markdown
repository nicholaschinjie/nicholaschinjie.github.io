# To build a modern backend 
not something I can learn on local projects, this is amazing 

## microservices vs monolithic
Monolithic code need to migrate everything (bad) 
- Multiple people working hard
- Scalability hard - need to migrate entire databases 
- Downtime means everything go offline (only one instance running)
- Failed handle exception = server crashes bc of one user (entire system offline)

- Microservices 
- distributed, scalable? (what does this mean)
- debugging while servers running = some instances can go offline while fixing, others still live (then rotate) - fix in increments

## gateway vs service
- service has all functionality (just do what you need to do)
- let gateway do validation / filtering / restriction / require / oauth (protection)

## mysql vs mongodb
mysql
- good for writing but not good for reading
- Youtube uses Vittess (to horizontally scale mysql) = database clustering 
mongodb
- has default sharding (storing data across multiple servers + distributed model = distribute CPU processing = better performance)
- e.g Alipay/AWS cloud will do this for you (just choose how many servers you wanna shard)
    - good for handling MASSIVE traffic (11/11)
- Regional scaling = Google Cloud Spanner vs Alibaba (distributing their servers by region)
    - both for relational and non-relational
    - horizontal scaling
    - good for migration 

## grpc (+ protobuf lighter)

### Protobuf (faster payload) vs JSON

- protobuf is easier to bind to objects 
- protobuf (protocol buffers) mechanism for serializing structured data into binaries (send out as binary = lighter faster)
- JSON is text based, integers and floats are slower to encode and decode 
- JSON better when data is human readable + if javascript
- https://www.bizety.com/2018/11/12/protocol-buffers-vs-json/


## go 

## Links 

https://www.infoq.com/news/2019/12/network-isolation-kubernetes/ 
https://monzo.com/blog/2016/09/19/building-a-modern-bank-backend 
RIOT BLOG

Force myself to write, so I read 


HashiCorp - Consistent workflows to provision, secure, connect, and run any infrastructure for any application. 
Sonarqube vs Jenkins 
CloudOps 

There's so much, what do I want to specialize in? 

Robert
- logging / code visibility / tracking / metrics 
- deployment / hosting
- scaling 

Me
- distributed systems 
- microservices 
- deployment devops 

AT REV MON I WANT TO ACTUALLY HAVE HANDS ON EXPERIENCE AND DEPLOY AND SEE IT FOR MYSELF
can i see when and how it goes live? 
product doesn't have to be impressive, what I want to see is the stack art 

no sir no web dev for me
all about deploying and scaling 
I want to be able to architect for my own company one day 

- not all about code, rather, about getting it out there 