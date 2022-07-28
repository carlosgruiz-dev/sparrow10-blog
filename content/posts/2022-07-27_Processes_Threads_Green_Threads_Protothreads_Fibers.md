---
title: "Processes, threads, green threads, protothreads, fibers, coroutines: what's the difference?"
date: 2022-07-27T21:45:22Z
draft: false
tags: ["concurrency"]
---

I found this answer on [StackOverflow][1] that is worth saving and revisiting in the future.
Concurrency is a broad topic, having a lot of options and layers of implementation. Well, let's
make this a starting point.

> OK, I'm going to do my best. There are caveats everywhere, but I'm going to do my best to
> give my understanding of these terms and references to something that approximates the
> definition I've given.
>
> - [Process][2]: OS-managed (possibly) truly concurrent, at least in the presence of suitable
>   hardware support. Exist within their own address space.
> - [Thread][3]: OS-managed, within the same address space as the parent and all its other threads.
>   Possibly truly concurrent, and multi-tasking is pre-emptive.
> - [Green Thread][4]: These are user-space projections of the same concept as threads, but are
>   not OS-managed. Probably not truly concurrent, except in the sense that there may be multiple
>   worker threads or processes giving them CPU time concurrently, so probably best to consider this
>   as interleaved or multiplexed.
> - [Protothreads][5]: I couldn't really tease a definition out of these. I think they are
>   interleaved and program-managed, but don't take my word for it. My sense was that they are
>   essentially an application-specific implementation of the same kind of "green threads" model,
>   with appropriate modification for the application domain.
> - [Fibers][6]: OS-managed. Exactly threads, except co-operatively multitasking, and hence not
>   truly concurrent.
> - [Coroutines][7]: Exactly fibers, except not OS-managed.
> - [Goroutines][8]: They claim to be unlike anything else, but they seem to be exactly green
>   threads, as in, process-managed in a single address space and multiplexed onto system threads.
>   Perhaps somebody with more knowledge of Go can cut through the marketing material.
>
> It's also worth noting that there are other understandings in concurrency theory of the term
> "process", in the [process calculus][9] sense. This definition is orthogonal to those above, but
> I just thought it worth mentioning so that no confusion arises should you see process used in
> that sense somewhere.
>
> Also, be aware of the difference between [parallel][10] and [concurrent][11]. It's possible you
> were using the former in your question where I think you meant the latter.

[(source)][1]

[1]: https://stackoverflow.com/a/3325985
[2]: http://en.wikipedia.org/wiki/Process_(computing)
[3]: http://en.wikipedia.org/wiki/Thread_(computer_science)
[4]: http://en.wikipedia.org/wiki/Green_threads
[5]: http://www.sics.se/~adam/pt/
[6]: http://en.wikipedia.org/wiki/Fiber_(computer_science)
[7]: http://en.wikipedia.org/wiki/Coroutine
[8]: http://www.go-program.com/goroutines/
[9]: http://en.wikipedia.org/wiki/Process_calculus
[10]: http://en.wikipedia.org/wiki/Parallel_computing
[11]: http://en.wikipedia.org/wiki/Concurrency_(computer_science)
