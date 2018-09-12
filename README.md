# ai-cache [Draft]
Invalidating cache using AI models


## High Level Description
Right now Cache is invalidated based on the settings and inavlidate time is same in all conditions.

#### Improvement:
    Dynamically allocate TTL to each key. 
Allocating dynamic TTL will reduce overall hits to DB while storing less data in CACHE Service.


### How to do?
Dynamic TTL is generted by using cache access patterns as input to machine learning model

 
  

Everytime a key is accessed in cache we store key and timestamp. 
Input:
  time of day
  accessed key
  

V1:
A wrapper aroung aerospike library to access aerospike cache 
Monitor only a specific percentage of data
Train and deploy model 
A backend to store access patterns
Train model and update model in cache service or backend
Every time Library is initialized, picks up trained model from cache service / backend and In every hour wrapper refreshes model parameter from cache service / backend
