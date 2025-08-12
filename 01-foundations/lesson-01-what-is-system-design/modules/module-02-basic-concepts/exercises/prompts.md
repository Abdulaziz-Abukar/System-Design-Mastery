# Module 2 Exercises

## Part A - Recall

1. List 5 common system components and describe each in one sentence.

   - **Client**: The part of the system the end-user interacts with.
   - **Server**: A machine that recieves client requests, processes them, and returns a response.
   - **Database**: Stores and retrieves data.
   - **API**: defines how clients talk to servers.
   - **Cache**: Stores frequently accessed data in a fast-access location.

2. What's the main difference between SQL and NoSQL database

   - **SQL** is a relational database that is structured. it has strong consistency but has trade-offs, them being it has complex queries, and its harder to scale horizontally.
   - **NoSQL** is a non-relational database that has flexible schemas, designed for fast scaling. It can easily scale horizontally and has high availability. Trade-off for this is that it has weaker consistency compared to a relational database.

3. Why might you use a cache in front of your database?
   - Because whenever clients keep requests the same data over and over again, it can cause the database to have increased loads and affect latency. With caching, it helps keep the database focus on tasks that are not commonly requested, reducing latency and also reducing load on databases.

## Part B - Apply

4. Your e-commerce app is slow during checkout. Which component(s) could you upgrade or add to improve performance, and why?

   - I'd start by profiling to locate the bottleneck. If app servers are saturated, i'd **add autoscaling behind a load balancer**. I'd **introduce caching** for cart, product, shipping, and tax lookups to cut DB round trips, and **optimize the database** (indexes, slow queries, connection pool). For work that doesn't need to block the user (email, receipts, analytics, ERP sync), I'd **add a message queue + workers**. If latency involves payment provider, i'd use **idempotency keys**, safe **retries**, and **parallelize non-dependent calls**. Finally, I'd push static assets/config to a **CDN** to reduce end-to-end latency.

5. A social media app wants to process image uploads without making users wait. Which component would help, and where would it fit in the flow?
   - I'd use a **Message Queue** (e.g., RabbitMQ, Kafka, or AWS SQS) between the application server and the image processing service.  
     When the user uploads an image, the server would quickly store the raw file in object storage (e.g., AWS S3) and then place a processing task into the queue.  
     Worker services subscribed to the queue would process the image (resizing, compression, thumbnail generation) in the background.  
     This lets the app immediately respond to the user and avoids blocking them while the heavy work is being done.
