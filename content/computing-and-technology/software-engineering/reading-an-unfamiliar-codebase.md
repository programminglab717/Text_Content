# Reading an Unfamiliar Codebase

You clone the repository and run the tree command, and it prints four thousand files. There is a directory called core and another called common and a third called utils, and nothing in their names tells you which one holds the thing you were hired to change. The README's setup instructions fail at step two because they were written against a version of the database driver that no longer exists. Somebody has left a file named notes.txt at the root, last modified three years ago.

This is the normal condition of joining a project, and the skill it demands is a genuine one that almost nobody is taught. Programmers spend far more time reading code than writing it, and most of that reading is of code they did not write, in systems whose organizing ideas were never written down. The approaches that work are not about reading faster. They are about choosing what not to read, and about extracting structure from sources other than the source itself.

## Run It Before You Read It

The first productive hour is usually spent getting the thing to start on your machine, not reading any of it. A system you can execute answers questions in seconds that would take a day of static reading — what it prints on startup, which config it complains about, what port it binds, which external services it tries to reach and fails to find. The failures are informative in themselves. An error about a missing credential for a message queue tells you there is a message queue, which the directory listing did not.

Getting it running also forces you through the build system, and the build configuration is the most reliably honest document in any repository. Prose documentation drifts because nothing breaks when it is wrong. The build file cannot drift, because the build would stop working. It names every dependency, which tells you what family of software this is — an HTTP framework, an ORM, a particular test runner, a queue client. The continuous integration configuration is nearly as good: it lists exactly the commands the team considers authoritative, in order, including the lint rules and the test invocation and any setup step a human is expected to know about. When a README and a CI config disagree, believe the CI config.

## Find the Doors

Large systems have a small number of entry points, and everything else is reached from them. Finding those doors converts an unstructured pile into a graph with roots.

Where they live depends on the kind of program. A web service has a routing table, and that table is a table of contents for the entire application — every operation the system performs for the outside world, with a handler function attached. A command-line tool has an argument parser that enumerates its own capabilities. A batch system has a scheduler configuration or a list of job definitions. A library has a public interface that is usually far smaller than its internals. Whatever the shape, finding the place where control enters from outside gives you a handful of named starting points instead of four thousand files of equal apparent importance.

The inverse trick works too: look for the exits. Find where the system writes to the database, sends network requests, or emits events, and you have found the places where it actually affects the world. Code between the doors and the exits is where the logic lives. Code that touches neither is often infrastructure, or dead.

## Follow One Request All the Way Down

Breadth-first exploration of an unfamiliar system produces the illusion of understanding and very little of the real thing. You end up with a vocabulary of file names and no model of how anything happens. The alternative that consistently works is to take one concrete operation — the smallest real thing the system does for a user — and trace it from the entry point to the final side effect, refusing to wander.

Choose something narrow. Not "how does checkout work" but "what happens when someone changes their email address." Start at the route, step into the handler, follow it into the service layer, into whatever validates the input, into the persistence call, and out to whatever notification gets sent. Keep going through every layer even when the layer looks boring, because the boring layers are where a project's conventions live: how errors are represented, how transactions are opened, how authorization is checked, whether the code returns errors or throws them. Once you have seen those conventions on one path, you have seen them on all paths, because almost every codebase does this consistently even when it does everything else inconsistently.

A debugger accelerates this enormously and is underused for exploration rather than diagnosis. Set a breakpoint in the handler, trigger the operation, and step through. The call stack is a free, accurate, always-current map of how control arrives — better than any architecture diagram, because it cannot be out of date. Following code by eye through dynamic dispatch, dependency injection, or a framework's middleware chain is slow and error-prone; watching it happen is neither.

## Ask the History and the Tests

Two sources sitting inside the repository tell you things the code cannot, and both are routinely ignored by new arrivals.

The tests are executable documentation of intent. A unit test for a pricing function shows you what inputs the authors expected, what edge cases they thought were worth protecting, and what the output is supposed to look like — often more clearly than the function, which has been modified nine times since. Integration tests are better still for orientation, because they contain setup code that shows how the pieces are meant to be assembled: which objects depend on which, what a valid request body looks like, what state has to exist before the operation is legal. If you want to know how to construct a valid instance of the central domain object, the fastest answer is almost always to find a test that constructs one.

Version control answers the other question, which is why. A line of code with an odd conditional in it is opaque; the commit that introduced it usually has a message, and the message may reference a ticket, and the ticket may describe a customer incident from four years ago that the conditional exists to prevent. Annotating a file to see when each line was last changed also gives you a quick sense of temperature. A file whose lines all date from the initial commit is settled and probably safe to rely on. A file where half the lines changed in the last two months is where the project is currently living, and it is where your change will probably go.

Naming deserves deliberate attention while you do this. Every mature codebase has a domain vocabulary — words that mean something precise inside this system and nothing in particular outside it. Learning that an "assignment" here always means a teacher-created artifact and never a variable binding, or that "account" and "customer" are different tables with a specific relationship, does more for comprehension than reading another thousand lines. When two words seem to mean the same thing, either there is a distinction you have not learned yet or there was a rename that never finished, and both are worth knowing.

## Make a Small Change as a Probe

At some point reading has diminishing returns and the next real information comes from touching something. The cheapest probe is a change you are confident about: fix a typo in an error message, add a log line inside a function you believe is hot, change a default and see what test fails. You are not testing the change. You are testing your model of the system — whether the code you think runs actually runs, whether the test suite covers what you assumed, whether the file you edited is even in the deployed build.

Deliberately breaking something in a scratch branch is an underrated version of this. Comment out a call you believe is essential and run the tests. If nothing fails, you have learned something significant: either the code is dead, or the suite has a hole. Both are worth knowing before you make a change that depends on one of them.

Write down what you learn as you go, in whatever form you will actually reread. A list of the four entry points that matter, the names of the three modules everything passes through, the one diagram of how a request flows. Do it in the first two weeks, because the knowledge that is expensive to acquire becomes invisible within a month — once the system feels obvious you will no longer be able to remember which parts were confusing, which is also why the people best placed to write the missing orientation document are the ones who have just stopped needing it.

The endpoint is not comprehension of the whole system. Nobody on the team has that either, including the people who have been there for years; they have detailed knowledge of the parts they work in and a coarse map of everything else, and they navigate the rest by the same tracing and searching you are doing. What you are after is enough of a model to make a change safely, plus an accurate sense of where your model runs out.
