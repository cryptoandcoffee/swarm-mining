# swarm-mining / Docker Edition
Mine cryptocurrency with Docker Swarm and your cpu

# First :
```
docker swarm init --advertise-address $your_public_ip
```
# Then :
Use the join worker command to add cpu workers
```
docker swarm join --token SWMTKN-1-5m2wkdixfn8wz0vpanbzlk2b5g76ntlm6vs0chhof9v55ywtxp-64ks4odvre1ujn47dxsveaal9 x.x.x.x:2377
```
# Finally :
# Run command below to start mining on all the workers you have added!
```
docker service create -d --mode=global \
  --name miner cryptoandcoffee/cpu-jayddee \
  -a yescrypt \
  -o stratum+tcp://lax.gltminer.com:50028 \
  -u GNosvoyiEhj6E5qtv2GQjnWLLER71ueJ6U \
  -p x

```

# Maintenance Commands :
# View service replicas
```
docker service ls
```
# View nodes and availability
````
docker node ls
````
# Remove a single node from swarm
```
docker node rm $hostname_of_node
```
# Stop the service and all running nodes
```
docker service rm miner
```

# Need more algorithm support?  
Browse the largest collection of Docker mining images on https://hub.docker.com/r/cryptoandcoffee/

Today's message is brought to you by https://cryptoandcoffee.com
