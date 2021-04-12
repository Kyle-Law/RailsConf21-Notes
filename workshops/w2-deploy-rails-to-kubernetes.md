# w2 Deploying your Rails Application to Kubernetes

### Description
Kubernetes has a lot of DevOps mindshare and is how shops like GitHub and Shopify are deploying their apps. But, what is Kubernetes? What does it mean for deploying your application? Do you need it?

In this workshop, we'll answer by migrating a small Rails application to Kubernetes. We'll build up the deployment tooling necessary to stand the application up on a small Kubernetes cluster.

We'll also explore the core concepts and considerations of adding Kubernetes to your deployment pipeline, including Kubernetes operations, preparing for ephemeral infrastructure, data storage, and more.

### Instructors
- Nathan L. Walls
Nathan L. Walls is a developer who works with and trains up software teams to test well, refactor to clarify intent and improve understanding, separate concerns, and stay adaptive with an emphasis on learning, respect and empathy. Nathan's also a photographer, kung fu student, qigong practitioner, day hiker and cat herder. He writes at http://wallscorp.us.

- Alex Panait
Alex Panait has been writing production-ready software for more than twenty years. He has a Masters in Computer Science and has worked in many technical roles across several industries. Outside of his own development work, he enjoys helping other developers improve their coding skills.

### Links
- https://github.com/base10/deploying-rails-to-kubernetes: GitHub Repo, follow #setup & #initialization

### Questions
- What's Kubernetes?
- What's the differences between deploying rails to docker vs kubernetes?
- Is it much cost effective to deploy in AWS vs Heroku?

### What is K8 good for?
- Fast scaling
- Safe(r) deployments with readiness checks
- Fast (practically instant) rollbacks
- Ephemeral infrastructure, no machine drift w/in or b/w environments
- Splitting parallelizable worklaods
