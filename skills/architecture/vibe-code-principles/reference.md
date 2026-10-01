# System design laws and resilience patterns

## Scaling and performance

| Principle | What it says | When it matters |
|-----------|-------------|-----------------|
| CAP theorem | Pick two of consistency, availability, and partition tolerance in distributed stores | Database selection and replication topology |
| Amdahl's law | System speedup is bounded by the sequential portion of the task | Deciding what code paths to parallelize |
| Gustafson's law | Additional computing resources allow larger problem sizes (counter to Amdahl) | Horizontal scaling strategies |
| Little's law | Queue depth equals arrival rate multiplied by latency ($L = \lambda W$) | Sizing queues, connection pools, and worker counts |
| Universal scalability law | Contention and coherence delay together set the ceiling on scalability | Shared state and locking across nodes |
| Wirth's law | Software slows down faster than hardware speeds up | Enforcing performance and bundle budgets |
| CQRS | Separate read and write data models to scale both paths independently | Workloads with asymmetric read and write volume |

## Architecture and design

| Principle | What it says | When it matters |
|-----------|-------------|-----------------|
| Conway's law | System architecture mirrors team communication structure | Aligning team boundaries with service boundaries |
| Gall's law | Working complex systems always evolve from working simple systems | Starting with a modular monolith before microservices |
| Postel's law | Be liberal in what you accept, conservative in what you send | Public API contracts and input parsing |
| Law of leaky abstractions | Every non-trivial abstraction leaks details of its underlying implementation | Debugging ORMs, frameworks, and virtualized runtimes |
| Zawinski's law | Every application expands until it can read email | Detecting scope creep early |
| Law of Demeter | An object should only call methods on its immediate collaborators | Decoupling modules and making components testable |
| Principle of least astonishment | A component should behave in the way that surprises users and callers least | Designing public APIs, SDKs, and CLI flags |

## Dependencies and networks

| Principle | What it says | When it matters |
|-----------|-------------|-----------------|
| Hyrum's law | With enough users, all observable system behaviors will be depended upon | Deprecation schedules and minor version updates |
| Metcalfe's law | The value of a network scales proportionally to the square of connected nodes | Evaluating marketplace and multiplayer features |
| Reed's law | Networks that support subgroup formation grow in utility exponentially | Community platforms and collaboration tools |
| Zipf's law | A small number of items will account for the majority of access requests | Sizing cache layers and identifying hot keys |
| Fallacies of distributed computing | The network is reliable, latency is zero, bandwidth is infinite, all false | Any network boundary, RPC call, or webhook |

## Human and operational process

| Principle | What it says | When it matters |
|-----------|-------------|-----------------|
| Murphy's law | Anything that can fail will eventually fail | Designing fallback states and circuit breaks |
| Brooks's law | Adding developers to a late software project makes it later | Staffing projects already behind schedule |
| Pareto principle | 80% of consequences come from 20% of causes | Focusing optimization on the critical paths |
| Parkinson's law | Work expands to fill the time allotted for its completion | Setting scope limits and release milestones |

## Resilience patterns

| Pattern | What it does | When it matters |
|---------|-------------|-----------------|
| Circuit breaker | Halts outbound requests to a failing dependency to prevent cascade failures ([source](https://newsletter.systemdesigncodex.com/p/8-must-know-distributed-system-design)) | Inter-service network calls and third-party APIs |
| Saga pattern | Coordinates distributed transactions using a sequence of compensating rollbacks ([source](https://oboe.com/learn/distributed-system-design-principles-3b3y8c/design-patterns-in-distributed-systems-4)) | Multi-step workflows spanning independent databases |
| Exponential backoff with jitter | Adds randomized delay intervals to retry attempts to avoid thundering herds ([source](https://www.educative.io/courses/grokking-the-system-design-interview/distributed-system-design-patterns)) | Network retries against congested backends |
| Ambassador pattern | Deploys out-of-process proxies to manage cross-cutting concerns like logging and mTLS ([source](https://newsletter.systemdesigncodex.com/p/8-must-know-distributed-system-design)) | Containerized services in Kubernetes and ECS |
