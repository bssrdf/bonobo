F.A.Q.
======

List of questions that went up about the project, in no particuliar order.

Too long; didn't read.
----------------------

Bonobo is an extract-transform-load toolkit for python 3.5+, that use regular python functions, generators and iterators
as input.

By default, it uses a thread pool to execute all code, and pass outputs to the next callable in the graph using a FIFO
queue, allowing the user to forget about what is blocking, not blocking, long, etc. It's lean manufacturing for data.

Can a graph contain another graph?
----------------------------------

No, not for now. There are no tools today in bonobo to insert a graph as a subgraph.

It would be great to allow it, but there is a few design questions behind this, like what node you use as input and
output of the subgraph, etc.

It is something to be seriously considered post 1.0 (probably way post 1.0).

How would one access contextual data from a transformation? Are there parameter injections like pytest's fixtures?
------------------------------------------------------------------------------------------------------------------

There are indeed parameter injections that work much like pytest's fixtures, and it's the way to go for transformation
context.

The API may evolve a bit though, because I feel it's a bit hackish, as it is. The concept will stay the same, but we need
to find a better way to apply it.

To understand how it works today, look at https://github.com/python-bonobo/bonobo/blob/0.2/bonobo/io/csv.py#L63 and class hierarchy.

What is a plugin? Do I need to write one?
-----------------------------------------

Plugins are special classes added to an execution context, used to enhance or change the actual behavior of an execution
in a generic way. You don't need to write plugins to code transformation graphs.

Is there a difference between a transformation node and a regular python function or generator?
-----------------------------------------------------------------------------------------------

No.

Transformation callables are just regular callables, and there is nothing that differentiate it from regular python callables.
You can even use some callables both in an imperative programming context and in a transformation graph, no problem.


Why did you include the word «marketing» in a commit message? Why is there a marketing-automation tag on the project? Isn't marketing evil?
-------------------------------------------------------------------------------------------------------------------------------------------

I do use bonobo for marketing automation tasks. Also, half the job of coding something is explaining the world what
you're actually doing, how to get more informations, and how to use it and that's what I call "marketing" in some
commits. Even documentation is somehow marketing, because it allows a market of potential users to actually understand
your product. Whether the product is open-source, a box of chips or a complex commercial software does not change a
thing.

Marketing may be good or evil, and honestly, it's out of this project topic and I don't care. What I care about is that
there are marketing tasks to automate, and there are some of those cases I can solve with bonobo.


Why not use <some library> instead?
-----------------------------------

I did not find the tasks I had easy to do with the libraries I tried. That may or may not apply for your cases, and that
may or not include some lack of knowledge about some library from me. There is a plan to include comparisons with
major libraries in this documentation, and help from experts of other libraries (python or not) would be very welcome.

See https://github.com/python-bonobo/bonobo/issues/1

Bonobo is not a replacement for pandas, nor dask, nor luigi, nor airflow... It may be a replacement for Pentaho, Talend
or other data integration suites but targets people more comfortable with code as an interface.

All those references to monkeys hurt my head. Bonobos are not monkeys.
----------------------------------------------------------------------

Sorry, my bad. I'll work on this point in the near future, but as an apology, we only have one word that means both
«ape» and «monkey» in french, and I never realised that there was an actual difference. As one question out of two I
got about the project is somehow related to primates taxonomy, I'll make a special effort as soon as I can on this
topic.

Or maybe, I can use one of the comments as an answer: python not only has duck typing; it has the little known primate
typing feature.

Who is behind this?
-------------------

Me (as an individual), and a few great people that helped me along the way. Not commercially endorsed, or supported.

The code, documentation, and surrounding material is created using spare time.

Documentation seriously lacks X, there is a problem in Y...
-----------------------------------------------------------

Yes, and sorry about that. An amazing way to make it better would be to submit a pull request about it. You can read a
bit about how to contribute on page :doc:`contribute/index`.

