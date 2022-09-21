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