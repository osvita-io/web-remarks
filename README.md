# A web app for marking student work

web-remarks is intended as a web-based, offline-capable, and
mobile-friendly platform for providing substantiating evidence for
quantitative evaluations of student work (e.g., grades).

web-remarks is heavily inspired by, and is intended as a web-based
front-end for [remarks](https://github.com/DIKU-EDU/remarks), a
domain-specific language for marking student work, designed at the
[Department of Computer Science at the University of Copenhagen
(DIKU)](https://di.ku.dk/).

## Quantitative vs. Qualitative Evaluation

A quantitative evaluation of student performance (e.g., a grade) is
shallow without substantiating evidence.

Such "evidence" can be _recursively_ provided by:

1. quantitative sub-evaluations (e.g., points given per
part/exercise), and a formal strategy as to how these are combined
into an overall evaluation (e.g., sum of given points); or

2. qualitative _remarks_, which to a domain expert would justify the
quantitative evaluation.

For example, consider a student being asked to "Write a Hello, World
program in C". Let the student submit a program that does so, except
that it does not write a terminating line-break.

A quantitative evaluation, with a single qualitative remark may read
as follows:

```
# Write a Hello, World Program in C: 80/100
  * The code submitted compiles and runs, but forgot a terminating line-break
```

Here, a top-level quantitative evaluation gives the student 80 points
out of a possible 100. This is justified in the qualitative remark
below it. The domain expert can now ponder over whether this
quantification is fair.

The qualitative remark given here is rather instance-specific. Given
points (80) disregarded, this is not a great template to follow when
judging others students: although it is important to check for a
terminating line-break, the remark is not phrased as a Yes/No
question.

One option is to enrich the qualitative remarks with mood marks:

```
# Write a Hello, World Program in C: 80/100
  + The code submitted compiles and runs
  - Remembered a terminating line-break
```

Here, the remarks with a (+) are positive, while those with a (-) are
negative. This could be turned into a template as follows:

```
# Write a Hello, World Program in C: 0/100
  * The code submitted compiles and runs
  * Remembered a terminating line-break
```

Another, perhaps more clear, way to fill out this template might be:

```
# Write a Hello, World Program in C: 80/100
  * The code submitted compiles and runs
    + Yes!
  * Remembered a terminating line-break
    - No :-(
```

Finally, the quantitative evaluation may be better off, if more
explicitly segregated into some domain-specific parts:

```
# Write a Hello, World Program in C: 80/100
## The code submitted compiles and runs: 50/50
  + Yes!
## The program actually writes Hello, World: 30/30
  + Yes!
## Remembered a terminating line-break: 0/20
  - No :-(
```

The template here would then look as follows:

```
# Write a Hello, World Program in C: 0/100
## The code submitted compiles and runs: 0/50
## The program actually writes Hello, World: 0/30
## Remembered a terminating line-break: 0/20
```

## Common Framework

A quantitative evaluation is not fair, unless there is a common set of
criteria according to which the work of each student is critiqued.

## Extensible Format

It should be possible to both praise and condemn, beyond the scope of
this baseline framework: It is hard to foresee student creativity and
understanding. Elements of student work may both far exceed, and fall
far below our expectations.
