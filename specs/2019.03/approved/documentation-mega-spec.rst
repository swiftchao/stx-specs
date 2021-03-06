
Documentation re-org and user documentation framework
=====================================================

This specification proposes changes to the structure of the StarlingX
documentation to make it easier for new contributors and users to find
the information they need.  We are also proposing a number of new
documents to cover gaps in the current documentation set.  This spec
defines the proposed new structure of the stx.docs repo and includes
links to the Storyboard entries for the new documents proposed.  The
new documents needed have been prioritized by the Docs team to allow for
the implementation to occur over time.

Story board entries for the numerous SB entries proposed here will
be created once the document is close to approval.

Problem description
===================

The StarlingX documentation structure can be improved to provide more
information for new users and contributors, as well as providing additional
reference information for more experienced users.  It can also be
improved to make it easier for users and contributors to navigate the
document hierarchy so they can find what they need.

Use Cases
=========

1. As a new user, I would like to learn the basics about StarlingX
so I can plan and complete an evaluation of the software.
2. As a user, I would like to learn how to deploy, install and run
StarlingX, so I can successfully deploy Starlingx for my Edge Cloud
applications.
3. As a user administering a StarlingX edge cloud deployment, I would like
to learn how to use all of the features of StarlingX and have all of
the API and CLI interfaces documented, so I can manage my
StarlingX Edge Cloud.
4. As a new contributor, I would like to learn about how to contribute
to the StarlingX project, so that my contributions are accepted.
5. As a new contributor, I would like to learn about the process
for accessing the StarlingX source code and building it from source, so
I can make changes and test them.
6. As a contributor, I would like to learn about the architecture of
StarlingX and the project’s development process, so I can contribute to
the project more effectively.

Proposed Change
===============

This section describes the changes to be made to the documentation.  The
changes are broken down into multiple stories each of which has a
priority as proposed by the Docs team.

New landing page
----------------

We propose to change the StarlingX documentation hierarchy on
docs.starlingx.io from this:

- Installation Guide
- Developer Guide
- Project Specifications
- REST API Reference
- Release Notes
- Contribute

To this:

- Introduction to StarlingX
- Deployment Guides
- Installation Guides
- Operation Guides
- Contributor Guides
- Releases and Release Notes
- Developer Resources

Each of the new sections in the document hierarchy is described below.
Note that we are separating Deployment from Installation.  We define
Deployment as all the steps needed starting from empty racks in the
data center to a running StarlingX instance.  Installation is defined
as installing the software and is a subset of Deployment.  Both sets
of documents will leverage content from the existing StarlingX documentation.

SB entry: 2005000
Priority: VH - release gating

Introduction to StarlingX
-------------------------

This new page in the document tree is a landing page is intended
to be a Quick Start for people who are new to StarlingX.  It contains
links to the following documents:

- StarlingX Project Introduction
- StarlingX for Kubernetes Users
- StarlingX for OpenStack Users
- StarlingX in a Box
- StarlingX Software Evaluation Guide
- Roadmap to StarlingX Documentation

SB entry: 2005001
Priority: VH - Release gating

The following documents are included in this section of the documentation.

**StarlingX Project Introduction (NEW)**
This document should start with a project overview with
respect to objectives,
capabilities, basic approaches.  Introduce the concept of base
Kubernetes Cluster + optional OpenStack Cloud Application.  Introduce
the various use cases for StarlingX and the available deployment
options.  The document should include a link to the Release page,
noting that pre-built and tested images are available.
SB entry: 2005002
Priority: VH - release gating

**StarlingX for Kubernetes Users (NEW)**
This document should describe the Kubernetes solution installed
and supported by StarlingX; e.g. what Kubernetes services are
included, what networking options, what container runtime
options, what storage solutions and the local registry. It should
highlight the advantages of the way that StarlingX configures and
uses Kubernetes as opposed to standard Kubernetes.
SB entry: TBD
Priority: H

**StarlingX for OpenStack Users (NEW)**
This document shall describe the OpenStack solution installed and
supported by StarlingX; e.g. what OpenStack Services are supported,
what Neutron backends are supported and what storage backends are
supported. This document shall highlight the advantages of the way
that StarlingX configures and uses OpenStack as opposed to standard
OpenStack.
SB entry: TBD
Priority: H

**StarlingX in a Box (NEW)**
This doc will describe how to boot and run
“StarlingX in a Box” (SIAB).  Once we actually create
it (SB 2004811).  The document should take users through
the process of bringing OpenStack services
up and show them some basic commands
such as create VM, load image into VM, start/stop VM and other
similar commands.  It should cover how to bring up StarlingX
Kubernetes, the basic K8S commands e.g. create a container, create
a service, launching a container application with a helm chart.
The challenge will be to not over document things documented elsewhere
or familiar to experienced OpenStack or K8S users, while
guiding less experienced users to performing real world tasks
in StarlingX.  The team creating StarlingX in a Box may decide
to create an image with both the OpenStack and Kubernetes services
already up and running, in which case we don't need to document
the bring-up process here.
SB entry: 2005003
Priority: VH - release gating

**StarlingX Software Evaluation Guide (NEW)**
This is a new document that describes the key features of StarlingX
that we expect Edge Cloud users to be interested in, and how to
set up and operate a StarlingX system to showcase them.  Without
over-documenting features already covered elsewhere - the goal of
this document is to be an appetizer and not the main course.
It should also describe
basic evaluation use cases and how to implement them in
StarlingX.  The Document can start by directing evaluators to
the "StarlingX in a Box" document and then build off of that
to showcase more advanced features.  It should call out the
open source functional and
performance test suites (once they exist) and how to run them.
The document’s main goal is to show users who are "kicking the tires"
of StarlingX how to use the key
differentiating features of StarlingX and guide them to a
very positive evaluation.
SB entry: TBD
Priority: M

**Roadmap to the StarlingX Documentation (New)**
This new document provides the reader with a brief overview of
the entire documentation set.  It could be based on use cases
listed above  e.g. “if you are a dev looking to contribute, you
should read X, Y and Z.  If you are an operator planning a
deployment read A & B.".  The contents of this spec itself
may be a good starting place for this document.
SB entry: TBD
Priority: H

Deployment Guides
------------------

This is a new landing page in the document hierarchy.  The deployment
options can be defined on the landing page and/or in the Deployment Options
page - a brief version on the landign page with full details in the Options
page is suggested.  The landing page contains
links to the following documents:

- StarlingX Deployment Planning
- StarlingX Deployment Options
- All-in-one Simplex Deployment Guide
- All-in-one Duplex Deployment Guide
- All-in-one Duplex with up to 4 Computes Deployment Guide
- Standard with Controller Storage Deployment Guide
- Standard with Dedicated Storage Deployment Guide
- Standard with Ironic Deployment Guide
- Multi-Region Deployment Guide
- Distributed Cloud Deployment Guide

SB entry: 2005004
Priority: VH - release gating

The following documents are included in this section of the documentation.

**StarlingX Deployment Planning (New)**
This is a new document for how to plan a deployment of StarlingX.
Needs to include references to the Deployment Options (or maybe
just include it).  Discuss why, how and when the various deployment
options should be used.  More focused on how to define what
hardware to buy and how to cable it up.  The existing HW
requirements documents would go here.
SB entry: 2005005
Priority: VH - release gating

**StarlingX Deployment Options (New)**
This is a new document that describes at a high level the different
deployment options for StarlingX.  This could be part of the
Deployment Planning document at the author's discretion.
SB entry: 2005006
Priority: VH - release gating

All of the Deployment Guides below should include Deployment
Diagrams showing the logical topology and networking of each
deployment option, e.g. showing the various node types, the various
network types, the typical gateway routers, etc...  This has been
explicitly requested on our mailing list.

**All-in-one Simplex Deployment Guide (New)**
This is a new document that describes how to deploy StarlingX in
the All-in-one Simplex configuration.
SB entry: 2005007
Priority: VH - release gating

**All-in-one Duplex Deployment Guide (New)**
This is a new document that describes how to deploy StarlingX in
the All-in-one Duplex configuration.
SB entry: 2005008
Priority: VH - release gating

**All-in-one Duplex with up to 4 Computes Deployment Guide (New)**
This is a new document that describes how to deploy StarlingX in
the Duplex with Compute nodes configuration.  Optionally, at the
discretion of the author of the All-in-one Duplex Deployment Guide, this
could be just an additional section of that document.
SB entry: 2005009
Priority: VH - release gating

**Standard with Controller Storage Deployment Guide (New)**
This is a new document that describes how to deploy StarlingX in
the Small Standard (no storage) configuration.
SB entry: 2005010
Priority: VH - release gating

**Standard with Dedicated Storage Deployment Guide (New)**
This is a new document that describes how to deploy StarlingX in
the Standard (with storage nodes) configuration.
SB entry: 2005011
Priority: VH - release gating

**Standard with Ironic Deployment Guide (New)**
This is a new document that describes how to deploy StarlingX in
the Standard configuration with OpenStack Ironic to allow use of
bare metal Compute nodes.  This is basically just the existing
how-to doc on Ironic, updated to deploy it in a Container.  At the
author's discretion, a separate Installation Guide for Ironic could
also be written.
SB entry: TBD
Priority: M

**Multi-Region Deployment Guide (New)**
This is a new document that describes how to deploy StarlingX in
the Multi-Region configuration.
SB entry: 2005012
Priority: VH - release gating

**Distributed Cloud Deployment Guide (New)**
This is a new document that describes how to deploy StarlingX in
the Distributed Cloud configuration.
SB entry: 2005013
Priority: VH - release gating

Installation Guides
-------------------

This is a new landing page in the document hierarchy.  It contains
links to the following documents:

- All-in-one Simplex Installation Guide
- All-in-one Duplex Installation Guide
- All-in-one Duplex with Computes Installation Guide
- Standard with Controller Storage Installation Guide
- Standard with Dedicated Storage Installation Guide
- Multi-Region Installation Guide
- Distributed Cloud Installation Guide
- Additional OpenStack Services Installation Guide

SB entry: 2005174
Priority: VH - release gating

The following documents are included in this section of the documentation.

**All-in-one Simplex Installation Guide (New)**
This is a new document that describes how to install StarlingX in
the All-in-one Simplex configuration.
SB entry: 2005175
Priority: VH - release gating

**All-in-one Duplex Installation Guide (New)**
This is a new document that describes how to install StarlingX in
the All-in-one Duplex configuration.
SB entry: 2005176
Priority: VH - release gating

**All-in-one Duplex with Computes Installation Guide (New)**
This is a new document that describes how to install StarlingX
in the Duplex with Compute nodes configuration.
SB entry: 2005177
Priority: VH - release gating

**Standard with Controller Storage Installation Guide (New)**
This is a new document that describes how to install StarlingX
in the Small Standard (no storage) configuration.
SB entry: 2005178
Priority: VH - release gating

**Standard with Dedicated Storage Installation Guide (New)**
This is a new document that describes how to install StarlingX
in the Standard (with storage nodes) configuration.
SB entry: 2005179
Priority: VH - release gating

**Multi-Region Installation Guide (New)**
This is a new document that describes how to install StarlingX
in the Multi-Region configuration.
SB entry: 2005180
Priority: VH - release gating

**Distributed Cloud Installation Guide (New)**
This is a new document that describes how to install StarlingX
in the Distributed Cloud configuration.
SB entry: 2005181
Priority: VH - release gating

**Additional OpenStack Services Installation Guide (New)**
This is a new document that describes how to install and configure
additional OpenStack services (beyond those supported by StarlingX)
in a StarlingX deployment.  Example services include Octavia,
Trove and Sahara, all of which have been mentioned in the
community as of interest.
SB entry: TBD
Priority: L

Operation Guides
----------------

This is a new landing page in the document hierarchy.  It is intended to
serve as the home page for “how to” documents and user/operator focused
documentation.  The page should contain links to the following documents:

- StarlingX API Reference
- StarlingX CLI Reference
- StarlingX Data Network Configuration
- StarlingX CEPH Storage Configuration
- StarlingX SDN Networking
- StarlingX Kubernetes Cluster Guide
- StarlingX SWIFT Configuration and Management
- StarlingX Fault Management
- StarlingX Patching Guide
- StarlingX Upgrade Guide

SB entry: 2005182
Priority: VH - release gating

**StarlingX API Reference**
This is the existing API Reference documentation.

**StarlingX CLI Reference (New)**
This is a new document the defines all of the CLI commands
accepted by the StarlingX unique services (the Flock).
SB entry: TBD
Priority: M

**StarlingX Data Network Configuration (New)**
This is a new document for how to configure the data networks. At
the author's discretion this can be covered in the deployment guides.
SB entry: TBD
Priority: M

**StarlingX CEPH Storage Configuration (New)**
This is a new document for how to configure CEPH.  At the author's
discretion this could also be a part of the deployment guides.
SB entry: TBD
Priority: M

**StarlingX SDN Networking (New)**
This is a new document for how to configure SDN networking.
SB entry: TBD
Priority: L

**StarlingX Kubernetes Cluster Guide (New)**
This is a new document for how to operate the Kubernetes
within StarlingX.  It should cover a description of how we use
the Armada component, how helm charts are managed within StarlingX,
how overrides for helm charts are configured/saved/edited.
SB entry: TBD
Priority: M

**StarlingX SWIFT Configuration and Management (New)**
This is a new document describing how to configure and use
SWIFT within StarlingX.
SB Entry: TBD
Priority: M

**StarlingX Fault Management (New)**
This is a new document describing the fault management
capabilities of StarlingX and how to use them, how to find and
read logs, etc…  It should call out and provide a link to the SNMP MIB.
SB entry: TBD
Priority: M (H?)


**StarlingX Patching Guide (New)**
This is a new document describing the software patching
capabilities of StarlingX and how to use them.
SB entry: TBD
Priority: L

**StarlingX Upgrade Guide (New)**
This is a new document describing the software upgrade
capabilities of StarlingX and how to use them.
SB entry: TBD
Priority: L

Contributor Guides
------------------

This is a new landing page in the document hierarchy.  It is intended
to serve as the home page for “how to” documents and user/operator
focused documentation.  The page should contain links to the
following documents:
- StarlingX Contributor Guide
- StarlingX Development Process
- StarlingX Build Guide
- StarlingX API Contributor Guide
- StarlingX Release Notes Contributor Guide
- StarlingX Documentation Contributor Guide

SB entry: 2005183
Priority: VH - release gating

**StarlingX Contributor Guide (New)**
This is a new document providing a high level overview of how
to contribute to StarlingX.  It should describe the
communication channels that are used by the project team, the
way we have divided up the project into sub-projects, our
wiki page, our weekly community and sub-project meetings, and
other similar topics.  It should point to the build and
installation documents and describe our expectations for
pre-commit testing needed before changes can be accepted.  It
should point to the project's formal Governance documents
and describe the roles of the TSC members and Core Reviewers
in reviewing and approving code changes.
SB entry: TBD
Priority: H

**StarlingX Development Process (New)**
This is a new document that can leverage existing content from
the wiki.  The document should cover the basic tools used
(git / gerrit / etc…), the feature development and spec
approval process, the bug resolution process, our release
planning process and other similar topics.

Initially this document can be a link to the current
wiki pages that describe
the development process.  Over time, we can consider moving the wiki
content into the git managed formal documentation.
SB entry: TBD
Priority: H
SB entry to fix the wiki content: 2005173
Priority: H

**StarlingX Build Guide**
This is the existing Build documentation, updated as needed to
fit within the new hierarchy and for the Containers changes.  It should
include a description of the build artifacts hosted by the third party and
how to use the build to leverage them.
SB entry: 2005184
Priority: VH - release gating

**StarlingX API Contributor Guide**
This is the existing API Contributor Guide

**StarlingX Release Notes Contributor Guide**
This is the existing Release Notes Contributor Guide

**StarlingX Documentation Contributor Guide**
This is the existing Documentation Contributor Guide

Releases and Release Notes
--------------------------

This should be a landing page with links to the publicly
available pre-built images and the Release
notes for all releases.  Releases that are no longer supported should
be included (for historical reasons) but should be marked as “obsolete”
or “unsupported”.
SB entry: 2995185
Priority: VH - release gating

Developer Resources
-------------------

This is a new landing page within the documentation and will contain
links to the following documents:

- How to Navigate the StarlingX Source Code
- StarlingX Architecture Documents
- StarlingX Specifications

SB entry: 2005186
Priority: VH - release gating

**How to Navigate the StarlingX Source Code (New)**
This is a new document describing the structure, layout and high
level architecture of the StarlingX git repos and source code.
SB entry: TBD
Priority: H

**StarlingX Architecture Documents (New)**
This is a landing page for architecture documents, which do not
yet exist.
SB entry: TBD
Priority: L

**StarlingX Specifications**
This is a link to the existing StarlingX Specifications page.

Alternatives
============

There are many ways to organize the StarlingX document repository.  The
proposal here is the result of multiple discussions, drafts and reviews
within the Docs team.

Data model impact
=================

None

REST API impact
===============

None

Security impact
===============

None
Other end user impact
=====================

End users should find it significantly easier to deploy and manage StarlingX
Edge Clouds.  New contributors should find it significantly easier to
make contributions to the project.

Performance Impact
==================

None

Other deployer impact
=====================

None

Developer impact
================

None

Upgrade impact
==============

None

Implementation
===============

This work will be implemented as a set of related Storyboard entries, as
called out in the Proposed Change.  Each Story has a priority defined
for it so the work can be managed over time.

Assignee(s)
===========

Members of the Docs team will provide guidance and support.  Responsibility
for the Documentation will need to be distributed across the StarlingX
sub-projects, to allow the work to be done by those most familar with the
software and to ensure the effort is scalable and manageable.

Primary assignee:
=================

Several will be needed.

Other contributors:
===================

Many will be needed.

Repos Impacted
==============

Stx.docs and likely the Flock services repos

Work Items
==========

See the SB entries called out in the Proposed Change

Dependencies
============

None significant

Testing
=======

Testing will be needed to ensure that the documents written accurately
describe the software.

Documentation Impact
====================

Lots :)
