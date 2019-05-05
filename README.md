# A web app for marking student work

web-remarks is intended as a platform for providing substantiating
evidence for quantitative evaluations of student work (e.g., grades).
The platform is designed to be web-based, offline-capable, and
mobile-friendly.

## Quantitative vs. Qualitative Evaluation

A quantitative evaluation of student performance (e.g., a grade) is
shallow without substantiating evidence. Such "evidence" can be
_recursively_ provided by:

1. quantitative sub-evaluations (e.g., points given per
part/exercise), and a formal strategy as to how these are combined
into an overall evaluation (e.g., sum of given points); or

2. qualitative _remarks_, which to a domain expert would justify the
quantitative evaluation.

For example, consider a student beign asked to "Write a Hello, World
program in C", and submitting a program that does so, except that it
does not write a terminating line-break.

A quantitative evaluation, with a single qualitative remark may read
as follows:

```
# Write a Hello, World Program in C: 80/100
  * Wrote a working program, but forgot to add a line break
```

Here, the student gets 80 points out of 100, and it is left for the
domain expert to judge whether forgetting a line break in your,
presumably first, program in C constitutes 1/5th of the job.

As another example, the quantitative evaluation may be more explicitly
segregated into some domain-specific parts:

```
# Write a Hello, World Program in C: 80/100
## The code submitted compiles and runs: 50/50
## Writes Hello, World: 30/30
## Writes a line break at the end: 0/20
```

## Common Framework

A quantitative evaluation is not fair, unless there is a common set of
criteria according to which the work of each student is critiqued.

## Extensible Format

It should be possible to both praise and condemn, beyond the scope of
this baseline framework: It is hard to foresee student creativity and
understanding. Elements of student work may both far exceed, and fall
far below our expectations.

## Background

web-remarks is intended as a web-based interface for
[remarks](https://github.com/DIKU-EDU/remarks), a domain-specific
language for marking student work.
