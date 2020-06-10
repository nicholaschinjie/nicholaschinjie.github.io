I try to learn something everyday

1/6 
- REST vs RPC 
- MVC vs DDD 
- Go Micro
- 

keywords
- backward compatible 

fun facts
- Grab uses GoKit (writes their own specific libraries)
- gRPC mostly for server, client side REST 

payment goes through 3-4 microservices = but still runs very fast! 
- latency is an issue 

local can be improved
- everything should work locally, but need to set up yourself 
- docker compose = pull image, up the service (if local works, do need to pull entire source code, no need realize stack) - but each dev have to launch their own local instance 
- better: host something remotely, eveyrbody can use