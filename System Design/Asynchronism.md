

**Overview**: Asynchronism allows systems to handle operations that are resource-intensive or time-consuming without blocking the main workflow. By moving such tasks to the background, systems can reduce request times and perform pre-emptive actions like data aggregation.

#### Message Queues

- **Purpose**: Facilitate asynchronous communication between different parts of a system by temporarily holding messages until they can be processed.
- **Workflow**:
  1. An application sends a job to the queue and informs the user of the job status.
  2. A worker retrieves the job from the queue, processes it, and marks it as complete.
- **Benefits**: Prevents user-blocking, allowing background processing and enhancing user experience with immediate feedback (e.g., instant posts on timelines).
- **Tools**:
  - **Redis**: Serves as a simple message broker; however, there's a risk of message loss.
  - **RabbitMQ**: Offers robust features with the need for AMQP protocol adaptation and node management.
  - **Amazon SQS**: Provides hosted service advantages but may introduce latency and duplicate message delivery risks.

#### Task Queues

- **Function**: Manage and execute background tasks along with their associated data, supporting task scheduling for heavy computational jobs.
- **Example Tool**: 
  - **Celery**: Known for scheduling capabilities and Python support.

#### Back Pressure

- **Concept**: A mechanism to control system load by limiting the size of queues to maintain high throughput and good response times for ongoing tasks.
- **Application**: When the queue reaches capacity, new requests are either rejected with an HTTP 503 status code or told to retry later, potentially with exponential backoff.
- **Rationale**: Prevents system overload by managing the queue size, ensuring stable and efficient performance under heavy loads.

#### Disadvantages of Asynchronism

- **Complexity**: Introducing queues adds to system complexity.
- **Delay**: May not be suitable for real-time operations or simple calculations due to inherent delays in processing.
- **Synchronous Suitability**: Direct operations without the need for background processing might be unnecessarily complicated by asynchronism.

#### Applying Back Pressure When Overloaded

**Analogy**: Comparing a system to an art gallery, where limiting visitor numbers ensures a quality experience. Similarly, systems should manage request rates to prevent overloading, maintaining optimal throughput and response times.

**Design Considerations**:
- **Queue Management**: Utilize bounded queues and monitor them to prevent system degradation under sustained high load.
- **Thread Pool Size**: Adjust according to the service quality requirements and the acceptable maximum latency.
- **Response Strategy**: Implement meaningful feedback for rejected requests, such as HTTP 503 status codes, prompting clients to retry after a delay.

#### Summary:
Designing systems to handle heavy loads requires careful consideration of asynchronism, task management, and back pressure techniques. Properly applied, these strategies can ensure systems remain responsive and stable, providing a seamless user experience even under peak demand.