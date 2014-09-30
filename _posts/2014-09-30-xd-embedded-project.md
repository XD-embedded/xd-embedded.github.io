---
title: XD-embedded project launched
layout: post
---
# {{ page.title }}

After much consideration, I figured out that the world is really missing: Yet
another embedded Linux build system XD

Well, perhaps not.  But regardless, I have decided to make one anyway.

I know, I am already guilty of fathering one of these beasts, namely the
[OE-lite](http://oe-lite.org) build system.

So why am I doing this again?  Good question...

1. Because I want to.
2. Because I have some important ideas that I would like to try out, which
   would be quite disruptive to OE-lite.

While the first reason should speak for it self (hint: in my free time, I do
like to reserve my right to do what I want), I would like to elaborate a bit
on the second reason.

The two disruptive ideas for XD-embedded is:

# Run tasks in containers

One of the main reason for the existence of OE-lite, is the design concept of
using a per-recipe staging directory, while otherwise staying quite close to
the design of OpenEmbedded (which was the initial starting point of OE-lite).
There are other areas, such as USE flags, and language syntax, where OE-lite
design has diverged from OpenEmbedded, but that is a different story.

In the meantime, OpenEmbedded has been extended with the sstate concept, which
is partly orthogonal to the per-recipe staging idea.

The first idea for XD-embedded, is to combine the positive features of
OpenEmbedded sstate and the per-recipe staging design of OE-lite, while
improving on both.  The magic for this is the popular
[docker](https://www.docker.com) platform.

Basically: Each task is executed in it's own docker container.  This
effectively gives us the power to do per-task staging, although I expect that
we will mostly use it in a per-recipe staging way.  The other benefit of
running each task in it's own container, is that we will get rid of the
problem of polluting directories shared between multiple tasks.  Just as
OE-lite improves on build reliability compared to OpenEmbedded, by not having
shared state between recipes, we will be able to improve build reliability by
getting rid of shared state between tasks.

# Typed metadata language

Where both OpenEmbedded and OE-lite metadata is basically just strings,
XD-embedded will feature a completely new metadata language with support for
different basic types, such as lists, dictionaries, integers, booleans, and
of-course strings.

The language will be designed to be as close to Python as possible, and should
have a similar and intuitive syntax in both metadata and Python context.

I expect to add a lot of improvements to the developer experience with this
change, but all Python code related to metadata (which is basically all
OE-lite Python code) and all metadata will basically have to be completely
rewritten.

# What does this mean for OE-lite?

For most purposes, I see XD-embedded as a natural successor to OE-lite.
Basically just a next generation OE-lite.

But...

1. I want to take the liberty of developing XD-embedded in a pace where
quality can be kept high in all parts from the start of, and as such, I do not
have a timeline for when it will be in a shape to replace whatever version of
OE-lite is the latest and greatest at that time.

2. And, OE-lite might continue to stay alive for a long time afterwards, as it
is in use in embedded products with long life-times (ie. 20+ years).

3. I don't think it is right to see this next generation as a 'lite' version
of OpenEmbedded (as OE-lite might imply).

For those reasons, XD-embedded has it's own name, and will for now, and
possibly a long time, live side-by-side with OE-lite.

I do hope to see friendly cooperation between XD-embedded and OE-lite
developers, and expect some developers (like me) to work with and on both
projects.
