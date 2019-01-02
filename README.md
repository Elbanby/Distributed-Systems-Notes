# Distributed Systems notes 

## About
In this Repo, I will be posting notes about distributed systems. I am self learning and currently exploring the topic.

So feel free to comment and correct me, would be highly appreciated! 

## Topics 

### Scalability

- Size scalability:  
adding more nodes should make the system linearly faster; growing the dataset should not increase latency

- Geographic scalability:  
it should be possible to use multiple data centers to reduce the time it takes to respond to user queries, while dealing with cross-data center latency in some sensible manner.

- Administrative scalability:  
adding more nodes should not increase the administrative costs of the system (e.g. the administrators-to-machines ratio).

#### Important aspects
##

##### Performance (latency):  
The amount of useful work done compared to time and resources used.

* Short response time/low latency for a given piece of work 
* High throughput (rate of processing work)
* Low utilization of computing resource(s) 

You can have 2 of the three. The three don't really exist at the same time <i>CAP theorem</i>

##### availability 

The amount of time a system is available. If a user can't access the system, that means to be unavailable. 
`Availability = uptime / (uptime + downtime)`

##### Design techniques 

1- Partition and replicate 

##
## <a href="https://en.wikipedia.org/wiki/Fallacies_of_distributed_computing">Fallacies of distributed computing</a>

1- The network is reliable 

2- The network is secure
 
3- The network is homogeneous 

4- The typology doesn't change 

5- There is one administrator

6- The latency is zero

7- Bandwidth is infinite 

8- Transportation cost is zero  

### Effects of Fallacies

1- Software is written with minimum error handling. Which may lead to permantly unrecieveing a packet and a
hard restart will be needed. 

2- Ignorance of network latency, and packet loss will lead to allowing unbounded traffic and wasting bandwidth

3- Ignorance of bandwidth can cause a bottlenecks 

4- Ignoring security can cause malicious users and programs.

5- Network typology change can lead to slower bandwidth and latency issues 

6- Multiple comapnes can institute conflicting policies of which senders of network traffic must be aware in order 
to complete their desired paths.     


7- The "hidden" costs of building and maintaining a network or subnet are non-negligible and must consequently be 
noted in budgets to avoid vast shortfalls.

8- If a system assumes a homogeneous network, then it can lead to the same problems that result from the first 
three fallacies.

## <a href="https://www.somethingsimilar.com/2013/01/14/notes-on-distributed-systems-for-young-bloods/"> Notes on Distributed Systems for Young Bloods</a> - Jeff Hodges
* Distributed systems are different because they fail often

### Design for failure 

* Writing robust distributed system is more expensive than robust single-machine system 

* Robust open source distributed system are much less common than robust single-machine systems 

* Coordination is very hard 

<b>I have to quote this paragraph here cause I think it is really important</b>

> Avoid coordinating machines wherever possible. This is often described as “horizontal scalability”. The real trick of horizontal scalability is independence – being able to get data to machines such that communication and consensus between those machines is kept to a minimum. Every time two machines have to agree on something, the service becomes harder to implement. Information has an upper limit to the speed it can travel, and networked communication is flakier than you think, and your idea of what constitutes consensus is probably wrong. Learning about the Two Generals and Byzantine Generals problems is useful here. (Oh, and Paxos really is very hard to implement; that’s not grumpy old engineers thinking they know better than you.)

### Two Generals Problem (Also known as: Two Generals Paradox, Or Two Armies Problem)

an unsolvable CS problem. However, there is two pragmatic approaches to decrease the risk of occurance. 

1- Sending many numbered packets to identify how reliable the communication is. For deterministic protocols with a 
fixed number of messages (expensive but fast) 

2- Absence of communication build up confidence of the communication. For nondeterministic and variable-length protocols
   (slow but cheap)


### The Byzantines Fault Tolerance  (BFT)

https://en.wikipedia.org/wiki/Byzantine_fault_tolerance

* If you can fit your problem in memory, it’s probably trivial.

* It’s slow” is the hardest problem you’ll ever debug. 

* Implement backpressure throughout your system.

* Find ways to be partially available.

* Metrics are the only way to get your job done.  

* Use percentiles, not averages. 

* Learn to estimate your capacity.

* Feature flags are how infrastructure is rolled out.  

* Choose id spaces wisely. 

* Exploit data-locality. 

* Writing cached data back to persistent storage is bad 

* Computers can do more than you think they can.

* Use the CAP theorem to critique systems. 

* Extract services.





 

