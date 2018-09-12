# ai-cache [Draft]

Invalidating cache using AI models


## High Level Description
Right now Cache is invalidated based on hard coded settings. Inavlidate time is constant in all conditions.

#### Improvement:
    Dynamically allocate TTL. 
Allocating dynamic TTL will reduce overall hits to DB while storing less data in CACHE Service.


### What to do?
A process to generate Dynamic TTL using cache access patterns as input to machine learning model

 
Everytime a key is accessed in cache we store key and timestamp. 

* Input:
  1. time of day
  2. accessed key
  

V1:
* A wrapper around aerospike library to access aerospike cache 
* Monitor only a specific percentage of data
* Train and deploy model to library

Requirements
* A backend to store access patterns (like mongodb, elasticsearch or any other)
* A task service to train model (like Celery)
* Trigger for Updating library with model 
   1. On first time load
   2. Every hour
