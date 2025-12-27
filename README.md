# therotical-day2
1. What are the primitive and non-primitive data types in JavaScript?

JavaScript has primitive types: string, number, boolean, null, undefined, symbol, and bigint.
Non-primitive (reference) types include object, array, and function.
Primitive types store actual values, while reference types store memory addresses.
Primitives are immutable; reference types are mutable.

Difference & Memory:
Primitives are stored in stack memory and copied by value.
Reference types are stored in heap memory and copied by reference.

2. Explain type coercion in JavaScript

Type coercion is JavaScript’s automatic or manual conversion of values from one data type to another.
Implicit coercion happens automatically (e.g., "5" + 2 → "52").
Explicit coercion is done using functions like Number(), String(), or Boolean().

== vs ===:
== compares values after coercion, while === compares both value and type without coercion.

3. What is NaN? How do you check if a value is NaN?

NaN stands for Not-a-Number, representing an invalid numeric result (e.g., 0 / 0).
NaN === NaN returns false because NaN is not equal to any value, including itself.
Use Number.isNaN(value) for accurate checking.

isNaN vs Number.isNaN:
isNaN() performs type coercion and may give incorrect results.
Number.isNaN() checks strictly and is the recommended approach.
