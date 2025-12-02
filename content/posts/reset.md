+++
title = 'Reset'
date = 2025-12-02T10:00:00+05:30
description = 'Time is running out'
featured_image = 'images/reset.webp'
images =  ["/images/reset.webp"]
+++

As the year is coming to an end, I am coming to the realisation that Stream-Pi has been dead for more years than it was alive. 

In the past, I have announced a complete re-write half a dozen times. But every single one of them ended up in a brief period of full time work, followed by an abrupt stop due to exams/personal issues. By the time I am free again, I lose the motivation to work because usually I forget which component or part I was working on.

As a way to keep myself motivated, I start this blog today as a way to share progress regarding the state of SPNG "Stream-Pi Next Generation". 

Yes, this name is just a placeholder, as I am in search for a nice name for this. It _will_ be opensourced once ready and named.

# Note

This and all future posts will be mostly ramblings and un-edited. A lot of these things may (and will) change.

# Technology

- SPNG will be follow a Host-Device architecture. The Host will be the main system of the user. Device is the input device. A host may have multiple devices connected to it. Each device can talk to each other via the host.

- It will be designed with latency in mind, so that we can also pair QMK/VIA into the same ecosystem.

- The primary goal is to keep everything as abstracted and modifiable. The only thing I fear for is, too much complexity will drive users away and make it hell to add new features. Technical debt is also real, hence I wish to keep it simple as possible.

- On the host side, I will primarily use C++ with Qt Quick for the user interface
    - I have contemplated about Rust, but at the time of writing, I just cannot find myself writing rust code that i will gut out and re-write half a dozen times. I am more of a "prototyper" than someone who first thinks of an elaborate plan, then slowly implement it. I would still chalk it up to my lack of experience to Rust
    - I considered Java, Kotlin, Go, but truth be told none of these languages have a proper UI framework for the desktop. Moreover, since I want this to also have as low latency as possible, I wish to avoid using any VM managed system. 
    - I do not like C++. That is why I will be writing a document or atleast refer to a styling/coding guide to use.
    - Qt Quick is perhaps the most feature rich and easy to use UI framework for the desktop, full stop. There is slint, but it does not support dynamic loading of `.slint` files QML does. There is some activity, and IIRC, their Rust version actually has some level of support for that.
    - Neither C++/Qt Quick is really ideal, both of them are "heavy", full of crust and crumbs, but the sheer amount of resources and ecosystem around them want me to stick more them.

- Client side is mostly left up to the programmer to implement. I will still be working on "official" android/iOS/etc. implementations. I would use the same Qt/C++ approach there or the native one, whichever seems easy for me.

- Due to the "pluginification" of the Device - Host connection, we can now have custom clients including ones powered by MCUs. I want to provide first class support for this, so I will be putting huge emphasis on this

# Milestone Zero

- Create and document the basic structs, classes, the "core" of the system that can be expanded upon.
- Create very basic UI with theme based on letterboxd

![ui-inspiration](../../images/ui-inspiration.png)