# Event-Driven Architecture

This architecture principal is built around the idea that at some times, data is needed to be processed, whilst other times it is not. Here, a central unit does initial processing before delegating the data to relevant modules.

They are considered highly efficient because, rather than passing through all levels, the data will only be sent to appropriate locations. It is also highly scalable if new event types are used.

The down-side is that error handling can be challenging unless modules are independent of each other.

![image](https://user-images.githubusercontent.com/54938676/210367818-28f5d64c-3ae8-4be0-bc0e-65f03748a8f6.png)
