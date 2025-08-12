# Module 2: Basic Components

We'll cover the main building blocks in most modern systems, what they do, and when you'd pick one over another.

## 1. Client

- **What it is**: The part of the system the end-user interacts with.
- Examples: Web browser, mobile app, IoT device.
- **Job**: Sends requests to the server and displays responses to the user.
- **Considerations**:
  - UI/UX responsiveness.
  - Device capabilities (slow phones need lighter payloads).

## 2. Server

- **What it is**: A machine (or cluster) that recieves client requests, processes them, and returns a response.
- Types:
  - **Application Server**: Runs the business logic (Node.js, Java Spring Boot, etc.).
  - **Web Server**: Handles HTTP requests (Ngnix, Apache).
- Trade-offs:
  - Verical scaling is simpler but limited.
  - Horizontal scaling needs load balancing.

## 3. Database

- **Purpose**: Stores and retrieves data.
  - Two main types:
    1. **SQL (Relational)** - Structured, supports ACID transactions
       - ✅ Strong consistency, complex queries.
       - ❌ Harder to scale horizontally.
       - Examples: PostgreSQL, MySQL.
    2. **NoSQL (Non-Relational)** - Flexible schema, designed for scaling.
       - ✅ Easy horizontal scaling, high availability.
       - ❌ Weaker consistency guarantees.
       - Examples: MongoDB, Cassandra.

## 4. API (Application Programming Interface)

- **Purpose**: Defines how clients talk to servers.
- Common types:
  - **REST** - Simple, resource-based
  - **GraphQL** - Flexible queries, fewer round-trips.
  - **gRPC** - Binary, high performance.
- **Trade-offs**:
  - REST is easier to learn and debug
  - GraphQL reduces overfetching but adds complexity
  - gRPC is super fast but harder for browsers without adapters

## 5. Cache

- **Purpose**: Store frequently accesssed data in a fast-access location (usually memory)
- Examples: Redix, Memcached, CDN edge caches.
- **Benefits**:
  - Lower latency
  - Reduce load on databases
- **Trade-offs**:
  - Data can be stale (consistency issue)
  - Needs eviction strategy (LRU, TTL)

## 6. Load Balancer

- **Purpose**: Distributes incoming requests among multiple servers.
- Examples: AWS ELB, Nginx, HAProxy
- **Benefits**:
  - Prevents any one server from overloading
  - Enables horizontal scaling
- **Trade-offs**:
  - Adds another point of failure (mitigated by redundancy)
  - Needs session management strategy

## 7. Message Queue / Stream

- **Purpose**: Enables asynchronous communication between services.
- Examples: RabbitMQ, Kafka, AWS SQS.
- **Benefits**:
  - Smooth out traffic spikes
  - Decouple services for better resilience
- **Trade-offs**:
  - Added complexity
  - Messages can be delayed or out of order

## 8. Storage System

- **Purpose**: Store large objects (images, videos, backups)
- Types:
  - **Object Storage** (e.g., AWS S3) - Best for unstructured data.
  - **Block Storage** - raw volumes for databases or VMs
  - **File Storage** - traditional shared folders
- **Trade-offs**:
  - Object storage is cheap & scalable but slower
  - Block storage is fast but costly

### How they fit together (simple flow)

```css
[Client] → [Load Balancer] → [Server] → [Database]
                       ↘→ [Cache]
                       ↘→ [Message Queue] → [Worker Services]

```
