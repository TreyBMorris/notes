# Chapter 1 - Reliable, Scalable, and Maintainable Applications

- CPU power is rarely a limiting factory, but the bigger problems are usually
  the size, complexity of data along with the speed that it changes.
- Many applications need to:
  - Store data (databases)
  - Remember the result of an operation (caches)
  - Allow users to search data by filter (search indexes)
  - Send a message to another process to be handles async (stream processing)
  - Periodically crunch a large amount of accumulated data (batch processing)
- Data systems is an umbrella of things like message queues and databases
  - Some data stores also can be used as message queues
  - Work is broken down into tasks can can be performed on a single tool.

## Three important concerns in most software systems

1. Reliability
   System should work correctly continuously even in the case of human errors
   and hardware/software failure.

2. Scalability
   As the system grows in volume, traffic, complexity,
   the application should be able to deal with said growth.

3. Maintainability
   Many people will work on the system overtime, so maintaining and adapting the
   system to new cases should allow them to work on it productively.

## Reliability

Typical expectations of reliable software include:

- Performs the functions a user expects
- Tolerate the user making mistakes or using the software in unexpected ways
- Good performance for required used case under expected load and volume
- Prevents unauthorized access and abuse.

A fault != failure.

### Hardware Faults

- Faulty RAM, hard disk crash, blackout, unplugging wrong cable, etc.

A response to something like a HDD crash is to add redundancy to the individual
components, such as a RAID configuration. When one component dies another
can take its place.

AWS for example, makes it so that your application is using multiple virtual
machine instances.This is to prioritize flexibility and elasticity over
single-machine reliability.

### Software Errors

Unlike hardware faults, these can be harder to anticipate such as a systematic error.
Ex: Runaway process that uses up some shared resource.

Bugs can cause software faults and can often lie dormant for a long time
until they are triggered by an unusual set of circumstances.

There is no quick solution to the problem, lots of small things can help
such as carefully thinking about assumptions, testing, monitoring, etc.

### Human Errors

Humans design and build software, and the operators who keep it running are also
human. Even with the best intentions, humans are known to be unreliable.

To curb human error we can:

- Design systems in a way that minimizes opportunities for errors.
- Decouple the places where people make the most mistakes from the places where
  they can cause failures.
- Test thoroughly at all levels. Unit tests to integration tests and manual.

We want to allow quick and easy recovery from human errors.
We want to set up clear and detailed monitoring for metrics and error rates.
Implement good management practices and training.

## Scalability

Even if a system is working reliably right now, it doesn't mean it will work
100% in the future.

Scalability is a term to describe a system's ability to cope with
an increased load.

### Describing Load

Load can be described with a few numbers which we call load parameters.
This can be requests per second to a server, hit rate on cache, etc.

### Describing Performance

We can look at performance in two ways:

- When we increase a load parameter and keep the system resources unchanged,
  how is the performance of the system affected?
- When we increase a load parameter, how much do you need to increase the
  resources available if you want to keep performance unchanged?

Latency and response time are often used synonymously, but they are
not the same. The response time is what the client sees. Latency
is the duration that a request is waiting to be handled.

### Approaches for coping with Load

Scaling up: Vertical scaling, moving to a more powerful machine
Scaling out: Horizontal, distributing the load across smaller machines.

Some systems are elastic meaning they can automatically add computing resources
when they detect a load increase, while others scale manually.

There is no magic scaling sauce.

Even though they are specific to a particular application, scalable
architectures are usually built from general purpose building blocks.

## Maintainability

The majority of software cost is not in its initial development
but in adding to it, fixing bugs, keeping it operational, tech debt,
new use cases, etc.

People hate working on legacy systems.

Three design principles for software systems:

- Operability: Make it easy for operations teams to keep the system
  running smoothly.
- Simplicity: Make it easy for new engineers to understand the system.
- Evolvability: Make it easy for engineers to make changes to the system
  in the future, adapting it for unanticipated use cases.

## Summary

This chapter explores fundamental ways of thinking about data-intensive
applications that will guide us through the rest of the book.
