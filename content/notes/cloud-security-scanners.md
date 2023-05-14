---
title: "Cloud Security Scanners"
---
To understand Cloud Security Scanners, there are some important pieces of prerequisite knowledge you must have

- [[cloud architecture]]
- [[design patterns]]
- [[anti-patterns]]

Please review those and come back when you are ready. I can wait!

![[waiting-cookie-monster.gif]]

# Okay, you're done?

Welcome back. So, here's the deal with cloud security scanners. They analyze your architecture and software for antipatterns and flaws. The two most common ways of doing this are scanning your live infrastructure running in your cloud provider account or scanning your [[notes/infrastructure-as-code|Infrastructure as Code]] in your repository. The advantage of the former is that it can find issues you've already put into the world and exposed yourself to. The advantage of the latter is that it can prevent proposed flaws from introducing business risk to your product,