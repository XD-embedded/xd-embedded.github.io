---
title: XD-embedded
author: Esben Haabendal
---

# What is XD-embedded

XD-embedded is a project, with the goal of developing tools for building
and maintaining embedded Linux systems and products.

The overall idea is to always keep the developers needs in focus.  Tools and
the procedures needed to use these tools should be designed and implemented
with a strong focus on keeping the developers happy.  When developers are
strugling with tools, they get unhappy (and inefficient).

XD-embedded tools therefore must be easy to use, intuitive (obey principle of
least suprise), and efficient.


## Software components

The software components that are currently being developed under the
XD-embedded umbrella is:

* XD-tool, the front-end tool for working with XD-embedded manifests.
* XD-build, a build and integration system for building embedded system
  firmware and SDK images.
* XD-req, a requirement management system.

Other possible additions, although no actual work is planned for them are:

* XD-test, a test system for automatic execution of on-target tests.


## Focus on developers

In this phase of the project, the focus is to serve the need of XD-embedded
developers, ie. those working on developing the XD-embedded software
components.  This includes both developers wanting to help develop the
XD-build system, and those wanting to help develop recipes for XD-build.

As a consequence, we must focus on:

* Developer documentation, both source-code and design documentation
* Code quality
* Developer friendly features, fx. debug features

Later on, focus will be extended to developers wanting to help write and
maintain XD-build recipes, and finally also those doing system and product
development with XD-build.


# What does XD stand for?

The name XD-embedded were chosen because:

* 'X' for cross, 'D' for docker, main concepts for the build system
* although usable for other purposes, the main goal use-case is embedded Linux
  system development
* you will have so much fun working with XD-embedded
* a lot of other possible names were already spoken for
