# mu-elasticache

Mu-elasticache is an extension [for the devops tool mu](https://github.com/stelligent/mu) 

This extension automatically creates an elasticache redis cluster in all of
your specified environments

## Using this Extension

copy these files into your project repo, I like to place these extensions under
the folder "mu", so you would create a new directory called mu/elasticache
to hold these files

then place the following at the bottom of your mu.yml file
```
extensions:
    - url: mu/elasticache
```

This is all you need to do to get started.

The following environmental variables can be passed to your application 
via mu.yml

```
environment:
  REDIS_HOST: ${ElasticacheCluster.PrimaryEndPoint.Address}
  REDIS_PORT: ${ElasticacheCluster.PrimaryEndPoint.Port}
```

The following parameters are configurable
NumCacheNodes (default is 2 for Multi AZ failover)
CacheNodeType (default is cache.t2.micro)
AutomaticFailoverEnabled (default is true)
