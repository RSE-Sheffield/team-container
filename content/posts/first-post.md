+++
title = "Meeting #0 write-up: what is Team Container?"
date = "2020-05-04"
author = "Will Furnass"
authorTwitter = "willfurnass"
cover = ""
tags = []
keywords = ["containers", "intro"]
description = "Introducing Team Container: a discussion group at the University of Sheffield on all things relating to containers (Docker, Singularity etc)"
showFullContent = false
+++

This group was set up to help researcher, research software engineers and IT Services staff discuss and demo *how to do containers*. 

The first meeting, held today, wasn't widely advertised (sorry).
Here's a summary of what we discussed:

## Motivation for setting up this group

There are a number of good reasons why in 2020 folks doing research using computer should care about containers:
 - Reproducible environments and computational results
 - Instantiating/managing complex heterogeneous software stacks (e.g. Deep Learning stacks)
 - Creating/maintaining web services around research workflows
 - Deploying batch workflows or services in remote environments

However, there are several things holding folks back:

 - How to use container images built by others?
 - How to build your own images?
 - How to share images?
 - How to use containers in CI/CD pipelines?
 - How to create/use images/containers securely and audit images?
 - How to use multiple containers in batch workflows or to provide a service?
 - How to handle data (files and databases)?
 - What tech to use for a given purpose?
 - What are our options at the University of Sheffield?

## Prior experiences

These varied widely between the ~8 people in attendance and included:

 - using the [rrtools](https://github.com/benmarwick/rrtools) framework to automate the building of papers containing computed results.  
   Successful CD builds result in a Docker image containing the paper being pushed to DockerHub.
 - using Docker and, prior to its advent, [LXC](https://linuxcontainers.org/lxc/introduction/), to wrap services.
 - Building and serving Jupyter or RStudio environments using [BinderHub](https://binderhub.readthedocs.io/en/latest/).
 - Deploying sea-ice-tracking workflows on the European Space Agency's (ESA) [Polar Thematic Exploitation Platform (Polar TEP)](https://portal.polartep.io/ssoportal/pages/login.jsf) 
   using Docker and a private image registry.
 - Having used Python virtualenvs and VMs but not containers.
 - Deploying containerised NLP workflows on Kubernetes as part of the [European Language Grid](https://www.european-language-grid.eu/) project.
 - Containerising HPC workflows (e.g. [FLAME GPU](http://www.flamegpu.com/) agent-based models) using Singularity to make them easier to run on various HPC systems.
 - Using Docker with [InstanceHub](https://www.instancehub.com/) to provide teaching environments on AWS.
 - (Attempting to) convert Ansible config for managing database-backed web apps to Docker Compose/Swarm to hopefully make it easier to manage state over time.

## Discussion

We reviewed a list of discussion topics and ideas for demos that we can explore in future meetings - see [this GitHub Project board][contact].

Notes on the discussion that followed:

- Q: what are researchers' current options for running services at the University of Sheffield?
  - Current options are (bare) [VMWare VM](https://www.sheffield.ac.uk/it-services/storage/servers) or (PHP-only) [CPanel](https://www.sheffield.ac.uk/it-services/cpanel).
  - A higher-level platform (similar to [Heroku](https://www.sheffield.ac.uk/it-services/storage/servers) or [PythonAnywhere](https://www.pythonanywhere.com/))
    could have a lower barrier to entry and be more secure by being more auditable, 
    particularly if base container images and orchestration templates could be provided/signposted.
  - There are currently no TUOS CI/CD services or image registries at TUOS.
  - A standardised way of auditing container images would help with adoption/support at TUOS.
- Q: Can/should we double-down on Docker as the foundation of a containerised world?
  - Probably, yes, as the [Open Containers Initiative](https://www.opencontainers.org/) have created standards for runtimes and images, 
    and Docker images and Docker's bundled runtimes (`runc`/`containered`) are OCI-compliant. 
    There are now [various OCI-compliant runtimes](https://medium.com/@avijitsarkar123/docker-and-oci-runtimes-a9c23a5646d6) and 
    therefore there's little risk of vendor lock-in.  For example, Podman and Singularity can both work with OCI images.
- Q: How could TUOS support both containerised services and legacy VM-based services?
    - RedHat [OpenShift](https://www.openshift.com/), 
      their Kubernetes-based container platform, 
      allows VMs to be [imported to OpenShift i.e. converted to containers](https://docs.openshift.com/container-platform/4.3/cnv/cnv_virtual_machines/cnv_importing_vms/cnv-importing-vmware-vm.html).
- Q: Should TUOS have a private image registry?
  - The RSE team could set one up for testing.
  - Q: How would/could identity management work?
    - One possible option: GitLab can provide image registries and supports SAML (single-sign on) for authentication, which would allow folks to access it via their TUOS accounts.

## What next?

If you want to get/remain involved:

 - Suggest/offer discussion points and/or demos via [this GitHub Project board][contact].
 - Upvote existing discussion points / demo suggestions via that board
 - Join [the Google Group][contact] to be notified of future meetups.

[contact]: {{< ref "/contact" >}}
