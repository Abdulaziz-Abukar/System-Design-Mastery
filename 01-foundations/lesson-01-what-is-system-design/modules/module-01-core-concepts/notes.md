# Module 1: Core Concepts

## 1. Scalability

- **Definition**: The system's ability to handle increased load by adding resources.
- **Two main types**:
  - 1.**Vertical Scaling** (Scale Up) - Adding mroe power to a single machine.
    - ✅ Simple to implement, no changes to application code.
    - ❌ Expensive at high levels, physical limits.
  - 2.**Horizontal Scaling** (Scale Out) - Adding more machines to share the load.
    - ✅ Better long-term grwoth, redundancy
    - ❌ More complex architecture (load balancing, data distirbution).

## 2. Latency

- **Definition**: The time taken for a request to travel from client -> server -> back to client
- Think **speed**: Measured in milliseconds (ms).
- **Low latency** = fast response; **High latency** = slow.
- Example: Sending a text to someone across the street (low) vs on Mars (high).

## 3. Throughput

- **Definition**: How many requests/data units the system can process per unit of time.
- Think **capcity**. Measured in requests per second (RPS), Mbps, etc.
- Example: A road might have low travel time (latency) but still carry few cars at once (throughput)

## 4. Availability

- **Definition**: The percentage of time the system is operational and accessible.
- Often expressed in "nines":
  - **99%** = ~3.65 days downtime/year
  - **99.9%** = ~8.76 hours/year
  - **99.99%** = ~52 minutes/year
- More nines = higher cost & complexity

## 5. Reliability

- **Definition**: How consistently the system performs its intended function without failure.
- **High Availability** ≠ **High Reliability** — a system might be up but returning wrong results.

## 6. Consistency

- **Definition**: All users see the same data at the same time.
- Strong vs Eventual consistency:
  - **Strong** -> Always up-to-date, slower.
  - **Eventual** -> Updates propagate over time, faster but with temporary differences.

## 7. Trade-offs

System design is about balancing these:

- You can lower latency by caching, but that might reduce consistency
- You can scale out for more throughput, but increase complexity
- You can improve availability, but at higher cost

## Visualization

Imagine a busy resturant:

- **Scalability** = hire more chefs/tables for more customers.
- **Latency** = how quickly one dish reaches the table
- **Throughput** = number of dishes served per hour.
- **Availability** = is the resturant open?
- **Reliability** = are the dishes made correctly every time?
- **Consistency** = do all tables get the same quality of food?
