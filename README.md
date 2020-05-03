# Team Container @ TUOS

## Overview

Team Container is a meetup for researchers and research software engineers at the University of Sheffield with an interest in [containers](https://en.wikipedia.org/wiki/OS-level_virtualization) inc:
 - Why bother - the value to reproducible research
 - The nuts and bolts (cgroups, Linux namespaces, Linux capabilities, overlay filesystems)
 - Container runtimes and image formats (Docker, Singularity, Podman, lxc)
 - Image registries
 - container orchestration (Docker Compose/Swarm, Hashicorp Nomad, Kubernetes)
 - Best practices for building containers
 - Security inc. managing secrets and audits

We share our discussions via this site.

## This site

- Is built using the [Hugo](https://gohugo.io/) static site generator;
- Is tested on pushes to / pull-requests against `master` using GitHub actions;
- Rendered content is deployed to the `gh-pages` branch on pushes to `master` (i.e. when pull requests are merged).
