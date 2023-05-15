---
title: "Container"
---
A container is a cordoned off computational construct. When a program runs within a container, all [[notes/operating-system]] [[API]] calls are handled by the container's virtualization tools rather than the actual [[notes/operating-system]]. This has many advantages. These features are commonly used for allowing multi-tenant computational workloads to share resources without risk of illegal access to resources they weren't meant to manipulate.