## Section 8

Topics: ARIES

Recovery is probably the most complicated topic we will be covering
in CS 186. Even the original pioneers in the field had trouble with
recovery. System R in the 1970s developed many of the ideas that we
covered so far in this class, such as query optimization and
concurrency control, but its developers did not see an efficient way
to guarantee recovery with a NO FORCE/STEAL buffer management policy.
ARIES was developed in 1992, and it took advantage of many clever
ideas and observations to create an efficient recovery algorithm that
also guaranteed a NO FORCE/STEAL policy.

The best way to understand the algorithm is to do lots of practice
problems - in this discussion, from previous midterms, etc. The way I
learned ARIES was by teaching section in Spring 2015 and writing
problems for vitamins, review sessions, and the final.

This is well beyond the scope of this class, but if you ever want to
see all the details of the algorithm (or if you ever take CS 262A),
the original paper is available at:
http://www.eecs.berkeley.edu/~kubitron/courses/cs262a-S16/handouts/papers/Aries.pdf.

