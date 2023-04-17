# 6.824 Intro to Distributed Systems

> A set of cooperating computers to perform a task

- Storage for websites
- Data-intensive operations (MapReduce)
- Peer to peer file sharing

### Why use them?

- Performance
- Parallelism
- Fault tolerance
- Physical locations
- Split computations (security)

### Challenges:

- Concurrency
- Partial failures
- Performance

 ### Infrastructure
 
 Abstractions are a plus for storage and/or computation
 
 - Storage
 - Communication
 - Computation
 
 ### Implementation
 
 - Remote Procedure Call (RPC)
 - Threads (structuring concurrent operations)
 - Concurrency control

### Performance

Scalability (scalable speedup) 2x resources -> 2x performance (throughput)

### Fault tolerance

- Availability (service still operates even with fault)
 - Can be recoverable as well
- Recoverability (service can recover with fault)
- Non-volatile storage: hard-drives, c drive, logs
- Replication (as independent in failure as possible)

### Consistency

put(k, v)
get(k) -> v

key/value services

- Strong consistent systems (a get guarantees latest data across system, very expensive)
- Weakly consistent systems (a put does not guarantee all gets to have latest data)
 
### MapReduce

`map` function will run on each input

Result of `map` is stored on the disk of the machine (worker) of which runs it

input 1 -> map a,1  b,1
input 2 -> map      b,1
input 3 -> map a,1     c,1

-> reduce -> a,2
-> reduce -> b,2
-> reduce -> c,1

Map(k,v)
// split v (values) into words
  for each word w 
    emit(w, "1")

Reduce(k, v)
  emit(length(v))
