# Module 1 Exercises

## Part A - Definitions:

1. Define scalability in your own words, and give a real-world example outside of tech.
   - Scalability is a system's ability to handle increased workload or demand by adding resources. An example of scalability would be hiring more sales associates in a retail store. More associates means more customers being handled at the same time instead of waiting for an associate to be available.
2. What's the difference between latency and throughput? Give an anology.

   - Latency is the delay before the first piece of data arrives. Throughput is the amount of data transferred per unit of time.  
     Latency is how long it takes for your pizza to arrive after your order. Throughput is how many pizzas the driver can deliver in an hour once they're going.

3. Explain availability and reliability, and why they're not the same thing.
   - Availability is the percentage of time a system is up and accessible. Reliability is the system's ability to perform correctly and consistently without failures.  
     **Example**: A website that's online 99.99% of the time is highly available. If it always loads the correct pages without errors, it's also reliable.

## Part B - Apply

4. Your video streaming platform is slow for users in another country. Which core concept(s) do you investigate first, and why?

   - The concepts I'd investigate in order would be latency and throughput.  
     **Latency** because the users are geographically far from the server, the physical distacne increases the round-trip time for data to travel, which can cause delays in starting or buffering the stream.  
     **Throughput** because large video files require a steady, high data transfer rate. If network throughput is limited due to congestion, bandwidth caps, or poor routing, video quality will drop or buffering will increase.

5. A shopping app crashes every Black Friday when traffic spikes. Which type of scaling should you consider, and what's the trade-off?
   - I would consider **horizontal scaling** by adding more server to handle the increased traffic to improve **avaialbility** during peak demand. The trade-offs would be Horizontally scaling adds infrastructure and operational complexity, requires code that can work across multiple servers, and increases cost for hardware, cloud resources, and maintenance.

## Part C - Stretch

6. Think of a system you use daily (e.g., WhatsApp, Gmail, Uber). For each core concept (scalability, latency, throughput, availability, reliability, consistency), write one sentence on how it applies to that system.
   - I choose instagram
     - **Scalability**: Instagram can add more servers and resources to support millions of users posting, liking, and messaging at the same time without slowing down.
     - **Latency**: The time it takes for a photo you post to appear on your friend’s feed after you tap “Share.”
     - **Throughput**: The volume of photos, videos, and messages Instagram can deliver to users every second.
     - **Availability**: Instagram remains accessible to users worldwide nearly all the time, even during peak hours.
     - **Relaibility**: Posts, messages, and notifications are delivered correctly and consistently without errors or loss.
     - **Consistency**: If two users open the same post at the same time, they both see the same content, likes, and comments.
