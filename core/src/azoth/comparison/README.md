# `azoth.comparison`

This namespace defines types and functions for comparing values for equality, equivalence or
ordering and operations based on those comparisons.

## Overview of Traits

Ordered <: Equatable
Strictly_Ordered <: Strictly_Equatable

Ordering[T] <: Weak_Ordering[T] <: Equivalence[T] <: Partial_Equivalence[T]

Subset_Ordering[T] <: Weak_Subset_Ordering[T] <: Partial_Equivalence[T]

## Equality and Strict Equality

**TODO:** Document:

* Most languages fail to define equality
* Languages that support partial equivalence return `false` for incomparable instead of `none`
* What abstract value equality is
* What strict equality is

## Intrinsic vs Extrinsic

## Definition of Ordering

In mathematical terms orderings are typically defined by either a precedes (`≺`), or a precedes or
equivalent to (`≾`) operation. In programming, all the various comparison operations (i.e. `≺`, `≾`,
`≻` and `≿`) are generally wanted together and need to be efficiently implemented. To support this,
we use an alternate but equivalent way of defining orderings in terms of comparison. Given `≺`, `≼`,
`≻` and `≿`, it can be observed that two values `x` and `y` may stand in any of four mutually
exclusive relationships to each other: either `x ≺ y`, or `x ≍ y` (i.e. equivalent), or `x ≻ y`, or
`x` and `y` are incomparable. This is implemented by a function `compare(...)` returning
`ordering` where the four cases are represented by `ordering.Precedes`, `ordering.Equivalent`,
`ordering.Succeeds`, and `none` (for incomparable).

This definition also sidesteps questions about the distinction between strict (i.e. `≺`) and
non-strict (i.e. `≾`) orderings since it defines both as part of one comparison.

## Confusion About Partial Orders

Some languages define a trait for a partial order (e.g. Rust `PartialOrd` and Haskell `PartialOrd`).
However, they then have IEEE floating point numbers implement this trait. IEEE floating point
comparisons are not a proper partial order because `NaN` is not equal to `NaN`, but a partial order
must be reflexive (i.e. `a ≼ a`). This leads to confusion and bugs since the operators `<`, `<=`,
`==`, `>`, `>=` do not follow the expected mathematical laws and relationship. For example, in Rust
`f64::NAN <= f64::NAN` is `false`. If it were `None`, the problem would at least be pointed out to a
developer writing the expression. As another example, in Rust `PartialOrd <: PartialEq` even though
a partial order *is not* a partial equivalence relation.

Another common mistake in programming texts is to talk about a partial order when what is really
needed is the stronger notion of a weak ordering. Thus a partial order gets conflated with both a
weak ordering and with a partial order over a subset of values.

Azoth consistently uses the following terms to avoid confusion:

| Term                             | Mathematical Meaning                    |
| -------------------------------- | --------------------------------------- |
| equivalence                      | equivalence relation                    |
| partial equivalence              | partial equivalence relation            |
| (unqualified) ordered / ordering | a total order                           |
| weak ordering                    | a weak order                            |
| subset (weak) ordering           | a (weak) ordering on a subset of values |

The distinction between a total order and a weak order is useful since it corresponds to whether a
stable or unstable sort is needed when sorting by that ordering.

Looking at all the commonly defined types in programming, it turns out that turn partial orders
aren't particularly useful in programming. Likewise the many other kinds of relations defined in the
order theory branch of math.
