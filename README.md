# Code-Quality-and-Software-Agility
Code Quality and Software Agility is an invaluable resource for understanding the software quality trade-offs at both the code and organizational levels. It covers testing and monitoring strategies, requirements management, team agility, and decision making.

![capture](https://cloud.githubusercontent.com/assets/23619819/24940296/3d38b8fa-1f10-11e7-9ae3-49b0751b390c.PNG)
### Your Code Is Like A Crime Scene:
Find Problem Spots With
Forensic Methods
by Adam Tornhill
qu ick view
01
The same principles behind geographical
offender profiling, a technique used by
forensic psychologists, can also be applied
to a codebase.
02
Your version control system contains
much of the data you need to identify
where to focus your code quality
improvement efforts.
03
Sometimes, only a small percentage
of the codebase is responsible for the
majority of historic defects. By narrowing
down their efforts, developers can often
solve a large number of defects by
working on a very small section of code.
We’ll never be able to understand large-scale
systems from a single snapshot of the code. Instead,
we need to understand how the code evolves and
how the people who work on it are organized. That
is, we have to unlock the history of our system
to predict its future. Follow along and see how
your version control data can provide just the
information you need to prioritize and improve the
parts of your codebase that matter the most.
The Challenge of Legacy Code
If you’ve spent some years in the software industry, you’ve probably
encountered your fair share of legacy code. The real problem
with legacy code isn’t necessarily the lack of comprehensive unit
tests or even excess complexity. The problem is that no one truly
understands why the code looks as it does.
Legacy code is full of mysteries. For example, that strange ifstatement
that seems to do nothing was once introduced as a
workaround for a nasty compiler bug that has now been fixed. The
re-use of the ‘userId’ parameter to represent a time stamp was a
quick and dirty fix that saved a deadline.
All these things are part of a system’s story; a history that’s often
lost with the passage of time. What you’re left with is a mess, and
now you need to maintain it, add new features, and improve the
existing code. Where do you start?
Move Beyond Code
Now, let’s pretend for a moment that you are handed a complete
map of the system. You immediately notice that it isn’t your typical
software diagram of boxes and cylinders. Instead, this map looks
more topographical. It shows the distribution of complexity in your
codebase along with information on the relative importance of
each part. You’re told that the map is generated based on how the
team interacted with the codebase, so you know it’s closer to reality
than most of the documentation. This is good news! Now you know
which components you need to grasp first and you know where the
most difficult spots are located. All of this drives your learning.
Wouldn’t it be great to have access to that information on your own
projects organized so you can concentrate on the parts that require
the most attention?. The good news is that you already have the
data you need—just not presented in the manner you need. We’ll
uncover this information by taking inspiration from an unexpected
field: forensic psychology.
Learn from Forensic Psychology
Time and money are always important in commercial software
projects, so you need to find a way to gradually improve the
code while you maintain it. You also need to ensure that the
improvements you choose to make do the most good. Even if some
modules suffer from excess complexity, that doesn’t mean you
should focus on them. If the team hasn’t worked on a particular
module for a long time, there are probably other modules with
more urgent matters where your efforts will have a greater effect
on overall quality (that’s why complexity metrics alone won’t do
the trick). To identify the most problematic modules, you need to
prioritize all the design issues and technical debt you have in the
codebase, hardly an easy task
Interestingly enough, crime investigators face similarly openended,
large-scale problems. Modern forensic psychologists attack
these problems with methods such as geographical offender
profiling. Believe it or not, this method works for software
developers too.
dzone’s 2015 guide to code quality and software agility 2 1
dzone.com/guides dzone’s 2015 guide to code quality and software agility
A geographical offender profile uses the spatial movement of
criminals to calculate a probability surface for the location of the
criminal’s home base. This probability surface is projected onto a
real-world map and the high probability areas are called hotspots.
Crime investigators use these probability distributions to focus their
investigations. Instead of searching and supervising a vast area, law
enforcement can now focus their efforts where they are most likely
to apprehend their targets.
Hotspots are Based on Spatial Patterns
Geographical offender profiling works because crimes, at least their
geographic locations, are never random; the distribution of crimes
follows a set of known principles. For a forensic psychologist, once
they have a series of recorded crimes, they can detect patterns in the
spatial behavior of the offender. They then use that information to
predict where the criminal is located.
Software development is similar because code modifications aren’t
random either. Code changes for a reason: users want new features,
bugs appear and are fixed, and code improves as we learn new ways
to simplify it.
If you look into the evolution of a large system, you’ll see that
these modifications follow an uneven distribution. Some modules
stabilize early during development while others remain in a state
of flux. The latter is likely to be a problem; code that changes often
does so either because the problem domain is poorly understood, or
because the code suffers from quality problems.
The geographical profiling technique provides an attractive solution
to the legacy code puzzle. Every time we make a change to our code
we give away a piece of information. A code change is like a vote for
the importance of a module. What we need to do is to aggregate all
those votes cast by the programmers who work on the system. Code
changes are our equivalent to spatial movement—and all of those
changes are recorded by our version control systems.
Analyze Hotspots in Code
Version control systems are a gold mine, full of valuable
information on change patterns in legacy code. To identify hotspots,
we just need to traverse the source code repository and calculate the
change frequency of each module. That gives us a prioritized picture
of the most frequently modified code.
But there’s more to a hotspot than pure change frequencies. To
qualify as a hotspot, the code area also has to have a high likelihood
of overall quality problems. We don’t have a good metric for that
within software. What we do have is a decent approximation based
on complexity metrics from the source code. Everything from
simple heuristics, like lines of code, to more elaborate metrics, like
cyclomatic complexity, can potentially serve this purpose since the
differences in predictive value are usually small enough to ignore.
If we combine change frequency with code complexity, we get
an operational definition for hotspots. A hotspot is complicated
code that programmers also have to work with often. Such code
is often a maintenance nightmare. There’s empirical research to
support this claim: change frequency is one of the best predictors
of software defects [1].
I’ve listed some key tools and resources for finding and visualizing
hotspots in your own code.
Code Maat: A command line tool to mine and analyze data
from version control systems.
Code Maat Gallery: A gallery of the best examples from
various version control data visualizations.
Your Code as a Crime Scene: My book on forensic techniques
in code quality management.
Now that we know how hotspots are found, here are some tips on
how to best use that information.
Use Hotspots in Practice
Hotspots in code, like their counterparts in crime investigations,
aren’t precise. Instead they suggest a probability of where most of
the problems are located. A hotspot analysis can guide your team
to the most beneficial areas to focus on for codebase improvement.
Some obvious uses of hotspots are to identify code that’s expensive
to maintain, and to prioritize which sections of code need to be
reviewed. You can also use hotspots to communicate with testers,
who use the information to focus their testing around hotspot-dense
feature areas.
Hotspots are a simple metric. That simplicity is a strength that
translates to practice surprisingly well. In a recent analysis of one
project I worked on, I found that system’s hotspots made up just 4%
of the code—but were responsible for 72% of all historic defects! In
other words, if our team were to improve just 4% of that codebase,
we would get rid of the majority of all defects. Similar situations
have been found in empirical research on software defects [2].
Just a Beginning
In this article we learned about hotspots as a way to direct our
software quality improvement efforts. Hotspots let you narrow down
a large system to specific, critical areas that need your attention.
Hotspot analysis is a powerful technique, but there’s so much more
we can do once we learn to analyze how our code evolves. Over
the past years I’ve used version-control data to predict bugs, detect
architectural decay, find organizational problems that show up in
the code, evaluate Conway’s Law, and more. Visit the links in the
Analyze Hotspots in Code section of this article to download the tool
that I use for finding hotspots and see examples of how it’s done and
how they’re visualized.
