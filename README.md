# Life-Skills

## Introduction
Event Sourcing is an architectural design pattern where changes that occur in a domain are immutably stored as events in an append-only log. This provides a business with richer data, as each change within the domain is stored as a sequence of events that can be replayed in the order they occurred. Thus, you can see more than just the current state of your domain you can see what led up to it.

## Key components 
### Event Store
A storage mechanism that persistently saves all events in the order they were applied. This log serves as the authoritative source of truth for the system's state.
### Event Consumer
The component is responsible for detecting and recording state changes as events. It ensures that every significant change is captured and stored. 
### Event Producer
A component that reacts to events, often by updating materialized views or triggering side effects. Consumers can subscribe to specific events and process them as needed.

## Benefits
### Auditability
Since all state changes are recorded as events, it's straightforward to trace how the current state was derived, providing a clear audit trail.  
### Flexibility
The event log can be replayed to reconstruct past states or to populate new read models, facilitating tasks like debugging or migrating to new storage systems. 
### Scalability
By decoupling the write and read sides, event sourcing can enhance scalability. For instance, different consumers can process events independently, allowing the system to handle increased load more effectively.

## Challenges
### Complexity 
Implementing an event-sourced system requires careful design, especially in defining the granularity of events and managing their evolution over time. Ensuring that events remain backward compatible is crucial to prevent issues during event replay. 
### Consistency
Maintaining eventual consistency across different read models can be challenging, particularly in distributed systems where network partitions or delays may occur. Strategies like idempotent event handlers and versioning can help mitigate these issues.
## References
*https://www.kurrent.io/event-sourcing#:~:text=Event%20Sourcing%20is%20an%20architectural,in%20the%20order%20they%20occurred.
*https://learn.microsoft.com/en-us/azure/architecture/patterns/event-sourcing
*https://en.wikipedia.org/wiki/Event-driven_architecture
*https://arxiv.org/abs/2104.01146
