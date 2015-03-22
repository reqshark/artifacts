# Unix Philosophy and Node.js

At TxJS the other day, I gave a talk where I mentioned that the Unix Philosophy is a crucial part of the patterns, opinions, and culture of Node.js. As usual, I made my slides available online well in advance of the talk video being available.
For some reason, this brief mention of “Unix Philosophy” set off a few peoples’ ire. Since I had only 25 minutes, and every slide could probably be its own talk entirely, I was rather light on elaboration. Chances are, the video won’t add all that much context. But the goal was to pique conversation, so maybe that’s a success if it invites criticism. After all, uninformed trolling is just an invitation for education, so I thought I’d explain.
Eric S. Raymond collected a few of the best explanations of the Unix Philosophy in his book, The Art Of Unix Programming. He elaborates on 17 specific principles, but my favorite formulation of the Unix Philosophy is the terse explanation from Doug McIlroy as quoted by Salus in A Quarter Century of Unix:

### This is the Unix philosophy:
* Write programs that do one thing and do it well.
* Write programs to work together.
* Write programs to handle text streams, because that is a universal interface.
* McIlroy’s slightly longer original 4-point formulation is this:
  - Make each program do one thing well. To do a new job, build afresh rather than complicate old programs by adding new features.
  - Expect the output of every program to become the input to another, as yet unknown, program. Don’t clutter output with extraneous information. Avoid stringently columnar or binary input formats. Don’t insist on interactive input.
  - Design and build software, even operating systems, to be tried early, ideally within weeks. Don’t hesitate to throw away the clumsy parts and rebuild them.
  - Use tools in preference to unskilled help to lighten a programming task, even if you have to detour to build the tools and expect to throw some of them out after you’ve finished using them.

Mike Gancarz, who worked on the X Window System, summed up the Unix Philosophy in 9 points:
* Small is beautiful.
* Make each program do one thing well.
* Build a prototype as soon as possible.
* Choose portability over efficiency.
* Store data in flat text files.
* Use software leverage to your advantage.
* Use shell scripts to increase leverage and portability.
* Avoid captive user interfaces.
* Make every program a filter.

That last point really resonates with something that Ryan Dahl has often said, “Every program is a proxy.” The first 3 are basically James Halliday's rules for living.

All too often, people get hung up on the wrong aspects of the Unix Philosophy, and miss the forest for the trees. The Unix Philosophy is not about a specific implementation, or anything that is necessarily unique to any Unix operating system or program. It’s not about file descriptors, pipes, sockets, or signals. Those sorts of complaints are like saying that someone is not a buddhist unless they speak Pali.

Unix Philosophy is an outlook for software development, not any specific technical development in software. It is an ideal to reach for, and perhaps ironically, it is an ideal that instructs us to occasionally eschew idealism in favor of practicality.

In Node, the basic building block that people share and interact with is not a binary on the command line, but rather a module loaded in by require(). The universal interface is a text stream, but it’s a JavaScript Stream object, rather than a stdio pipe. (The stdio pipes are of course represented by JavaScript streams, because that is our universal interface, so what else would we use?)

So, in terms of Node.js, here’s how I’d express the Unix Philosophy. Alas, I am no McIlroy, and I lack the time or skill to write this any shorter.
* Write modules that do one thing well. Write a new module rather than complicate an old one.
* Write modules that encourage composition rather than extension.
* Write modules that handle data Streams, because that is the universal interface.
* Write modules that are agnostic about the source of their input or the destination of their output.
* Write modules that solve a problem you know, so you can learn about the ones you don’t.
* Write modules that are small. Iterate quickly. Refactor ruthlessly. Rewrite bravely.
* Write modules quickly, to meet your needs, with just a few tests for compliance. Avoid extensive specifications. Add a test for each bug you fix.
* Write modules for publication, even if you only use them privately. You will appreciate documentation in the future.
* Working is better than perfect.
* Focus is better than features.
* Compatibility is better than purity.
* Simplicity is better than anything.

The Unix Philosophy is an ideology of pragmatism. It is about balancing the twin needs of writing good software, and writing any software at all. It’s a practical set of advice for trading a moderate increase in development cost for a much larger reduction in maintenance costs.

In the real world, we are faced with the completely unfair constraint of being human while writing programs and while debugging them, and none of these costs can ever be reduced to zero. This ideology is contextual, and can be applied at all levels of the stack. It is an open acknowledgement that we are actually not smart enough to know how to write the software we need the first time around, because we usually can only fully understand our problems once we have finished solving them.

None of these rules are sacrosanct! In fact, in many cases, they can be at odds, or even completely contradictory. However, if we keep our units of programming small, with simple universal interfaces, we can find leverage the piecemeal structure as a quality ratchet, swapping out clumsy parts as we go along.

Nothing about the Unix Philosophy explicitly relates to a culture of software sharing. However, it should be no mystery that it comes from the software community where we argue at length about the best way to make our programs properly Free. Software that is developed according to these principles is easier to share, reuse, repurpose, and maintain.

-- Isaac Z. Schlueter, http://blog.izs.me/post/48281998870/unix-philosophy-and-node-js
