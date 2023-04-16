# MapReduce notes

> Programming model and implementation for processing and generating large datasets

To use:

A user specifies a map function:
- Processes a key/value pair
- Which generates a set of intermediate values associated with the same key

And a reduce function:
- merges all values associated with the same key

- Automatically parallelized and executed on a large cluster of commodity machines

The run time system handles:
- Partitioning the input data
- Scheduling the program’s execution across a set of machines
- Machine failures
- Managing the inter-machine communication

Inspired by the map and reduce primitives found in Lisp, among other functional programming languages

The goal: handle processing large sets of data at Google, while hiding parallelization, fault-tolerance, data distribution and load balancing.

The computation takes a set of input key/value pairs and returns a set out output key/value pairs.

MapReduce library is written in C++