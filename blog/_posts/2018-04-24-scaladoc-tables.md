---
layout: blog-detail
post-type: blog
by: Janek Bogucki
title: "Introducing Scaladoc Tables: Part One"
---

Scala 2.12.TODO?? added support for defining tables in Scaladoc comments.

### A Simple Example

TODO: Add full Scaladoc comment including a simple table.
TODO: Add image of rendered table.


### Header Cells, Content Cells

TODO

### Table Captions

TODO


### Multiline Content

TODO


### What's Next?

In part two we will take a look at some more advanced aspects including

 - Allowing table markdown as content, for example |
 - Cell content limitations
 - Areas for improvement

### How can I help?

Try using tables and share your feedback on this issue: TODO: Add issue

TODO: Delete the following:

Now that Scala 2.13 is only a few months away, it's time to consider the
roadmap beyond it. It's been no secret that the work on [Dotty](https://github.com/lampepfl/dotty) over the
last 5 years was intended to explore what a new Scala could look
like. We are now at a stage where we can commit: Dotty will become
Scala 3.0.

Of course, this statement invites many follow-up questions. Here are
some answers we can already give today. We expect there will be more
questions and answers as things shape up.

### When will it come out?

The intent is to publish the final Scala 3.0 soon after Scala 2.14. At the
current release schedule (which might still change), that means early 2020.

### What is Scala 2.14 for?

Scala 2.14's main focus will be on smoothing the migration to Scala 3.
It will do this by defining migration tools, shim libraries, and
targeted deprecations, among others.

### What's new in Scala 3?

Scala has pioneered the fusion of object-oriented and functional
programming in a typed setting. Scala 3 will be a big step towards
realizing the full potential of these ideas. Its main objectives are
to

 - become more opinionated by promoting programming idioms we found
to work well,
 - simplify where possible,
 - eliminate inconsistencies and surprising behavior,
 - build on strong foundations to ensure the design hangs well together,
 - consolidate language constructs to improve the language’s consistency, safety, ergonomics, and performance.

The main language changes, either implemented or projected, are listed
in the [Reference section on the Dotty website](http://dotty.epfl.ch/docs/reference/overview.html).
Many of the new features will be submitted to the [SIP](https://docs.scala-lang.org/sips) process, subject to approval.

It's worth emphasizing that Scala 2 and Scala 3 are fundamentally the
same language. The compiler is new, but nearly everything Scala
programmers already know about Scala 2 applies to Scala 3 as well, and
most ordinary Scala 2 code will also work on Scala 3 with only minor
changes.

### What about migration?

As with previous Scala upgrades, Scala 3 is not binary compatible with Scala 2.
They are mostly source compatible, but differences exist. However:

 - Scala 3 code can use Scala 2 artifacts because the Scala 3 compiler
   understands the classfile format for sources compiled with Scala 2.12 and upwards.
 - Scala 3 and Scala 2 share the same standard library.
 - With some small tweaks it is possible to cross-build code for both Scala 2 and 3.
   We will provide a guide defining the shared language subset that can be compiled under both versions.
 - The Scala 3 compiler has a `-language:Scala2` option that lets it compile most Scala 2 code
   and at the same time highlights necessary rewritings as migration warnings.
 - The compiler can perform many of the rewritings automatically using a `-rewrite` option.
 - Migration through automatic rewriting will also be offered through the [scalafix](https://github.com/scalacenter/scalafix) tool, which can convert sources to the cross-buildable language subset without requiring Scala 3 to be installed.

### What’s the expected state of tool support?

 - Compiler: The Scala 3 compiler `dotc` has been used to compile itself and a growing set of libraries for a number of years now.
 - IDEs: IDE support is provided by having `dotc` implement LSP, the [Language Server Protocol](https://langserver.org),
   including standard operations such as completion and hyperlinking and more advanced ones
    such as find references or rename. There’s a [VS Code plugin](http://dotty.epfl.ch/docs/usage/ide-support.html) incorporating these operations.
   JetBrains has also released a first version of Scala 3 support in their [Scala IntelliJ plugin](https://blog.jetbrains.com/scala/2017/03/23/scala-plugin-for-intellij-idea-2017-1-cleaner-ui-sbt-shell-repl-worksheet-akka-support-and-more), and we intend to work with them on further improvements.
 - REPL: A friendly REPL is supported by the compiler
 - Docs: A revamped Scaladoc tool generates docs for viewing in a browser and (in the future) also in the IDE..
 - Build tools: There is a Dotty/Scala 3 plugin for [sbt](https://www.scala-sbt.org), and we will also work on Scala 3 integration in other build tools.

### What about stability?

 - A [community build](https://github.com/lampepfl/dotty-community-build) contains some [initial open source projects](https://github.com/lampepfl/dotty-community-build/blob/master/src/test/scala/dotty/communitybuild/CommunityBuildTest.scala) that are compiled nightly using Scala 3. We plan to add a lot more projects to the build between now and the final release.
 - We plan to use the period of developer previews to ensure that core projects are published for Scala 3.
 - We have incorporated most of the Scala 2 regression tests in the Scala 3 test suite and will keep including new tests.
 - In the near future we plan to build all Scala 3 tools using a previous version of the `dotc` compiler itself.
   So far all tools are built first with the current Scala compiler and then again with `dotc`.
   Basing the build exclusively on Scala 3 has the advantage that it lets us “eat our own dog food”
   and try out the usability of Scala 3’s new language feature on a larger scale.

### When can I try it out?

You can start working with Dotty now. See the [getting
started](http://dotty.epfl.ch/docs/contributing/getting-started.html)
guide. Dotty releases are published every 6 weeks. We expect to be in
feature-freeze and to release developer previews for Scala 3.0 in the
first half of 2019.

### What about macros?

Stay tuned! We are about to release another blog post specifically
about that issue.

### How can I help?

Scala 3 is developed completely in the open at
[https://github.com/lampepfl/dotty](https://github.com/lampepfl/dotty).
Get involved there, by fixing and
opening issues, making pull requests, and participating in the
discussions.
