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

We share our discussions via the site managed using this git repository.

## About this site
  - This is the source for the site; to view the site itself visit [https://rse-sheffield.github.io/team-container/](https://rse-sheffield.github.io/team-container/)
  - The site is built using the [Hugo](https://gohugo.io/) static site generator
  - It is [tested on pushes to / pull-requests](https://github.com/RSE-Sheffield/team-container/actions) against `master` using GitHub Actions
    [![Build and deploy status](https://img.shields.io/github/workflow/status/RSE-Sheffield/team-container/build_and_deploy/master.svg)](https://github.com/RSE-Sheffield/team-container/actions)
  - Rendered content should be deployed to the `gh-pages` branch on pushes to `master` (i.e. when pull requests are merged), again using GitHub Actions
  - The theme is a [git submodule](https://git-scm.com/book/en/v2/Git-Tools-Submodules) so the repo must be cloned as follows before building/deploying:
    ```sh
    git clone --recurse-submodules git@github.com:RSE-Sheffield/team-container.git
    ```
