# Distributed Applications

> A distributed system is a system whose components are located on different networked computers, which communicate and coordinate their actions by passing messages to one another from any system.

Many ways of building Distributed Applications:
- Via REST, messages,..
- Many design patterns
    - Microservices
    - Service Oriented Architecture (**SOA**)
    - Message driven architecture
    - CQRS / Event Sourcing
    - ...

## Distributed Computing Fallacies

1. The network is reliable &rarr; Packet loss
2. Latency is zero &rarr; Requests arriving out of order
3. Bandwith is infinite &rarr; A bottleneck in the internal network leads to weird errors
4. The network is secure &rarr; Drive-by hacking with wifi leads to data loss
5. Topology doesn’t change &rarr; Suddenly your site loads slow
6. There is one administrator &rarr; No-one understands everything, it is not enough to hold all secrets in a file on your disk
7. Transport cost is zero &rarr; A user in China has a different experience then one in Belgium
8. The network is homogeneous &rarr; Different protocols and technologies are used everywhere, you need compatiblity with a lot of things

---

### Reading material on how to design "traditional" distributed applications
- [Patterns of Distributed Systems](https://martinfowler.com/articles/patterns-of-distributed-systems/)
- [Service-Oriented Composition (with video)](https://udidahan.com/)
- [Running Online Services at Riot: Part I | Riot Games Technology](https://technology.riotgames.com/news/running-online-services-riot-part-i)

### References
- Jurić, S 2019, Elixir in Action, Second Edition, Manning
- [GitHub - WannesFransen1994/elixir-learning-materials: repository that contains multiple learning materials with code examples.](https://github.com/WannesFransen1994/elixir-learning-materials)


## Erlang - Elixir

- Elixir built on top of Erlang
    - Built to power telecom systems
    - Built for reliability, responsiveness, scalability and constant availability
    - General purpose
    - Focus on concurrency

- Elixir = dynamic language
    - Variables not typed at compile time
    - All checking done during execution
- Functional language
    - Building blocks &rarr; functions
    - Data is immutable
        - Cannot be modified after creation


## Concurrent Applications

### Distributed vs Concurrent
- Distributed: running on different computers
- Concurrent: computations are running during overlapping time periods
- Parallel: computations are running simultaneously

### Concurrency
- **Operating System Level**
    - OS allows multiple processes to run concurrently
    - Every process has private memory (independent execution context)
    - Every process:
        - Multiple threads
            - Share memory
            - Unit of execution and scheduled on cpu cores
                - Scheduled on a core, by reserving time-slot
                - Thread ended? &rarr; different thread
            
- **Language Level**
    - Java:
        - Based on OS
        - Java thread corresponds with OS thread
        - OS concurrency issues &rarr; inherited by Java
            - Number of threads can scale, but limited
            - Threads can acces shared memory &rarr; Ecpensive mechanisms
            - Every time a new thread needs to be scheduled &rarr; context switch
    - Elixir:
        - Unit of Concurrency is called a *Process* &ne; *OS process*
        - BEAM instance runs on single OS Process
            - &rarr; schedules runtime of Processes internally
                - OS pov &rarr; single process running
                    - In that process &rarr; Elixir processes scheduled by BEAM

### Language Level Concurrency in Elixir
- An Elixir process = completely isolated from other processes
    - No memory sharing allowed, communication &rarr; messages
    - No need for memory synchronization between processes
- Fault tolerant by default
    - Crash in one process? &rarr; no impact on other processes
- Scalable by default
    - Distributing processes: can use multiple BEAM instances
    - No special code required



## Installing Elixir

### Set-Up

- Installing
    - [Installing Elixir - The Elixir programming language](https://elixir-lang.org/install.html)
    - [Fly - Setup VSCode for Elixir Dev](https://fly.io/phoenix-files/setup-vscode-for-elixir-development/)
- Code setup
    - VS Code (with ElixirLS extension)
    - Elixir/Erlang OTP installed in WSL
    - WSL terminal in VS Code

