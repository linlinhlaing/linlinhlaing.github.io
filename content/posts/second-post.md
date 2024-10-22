---
title: "while loop vs do-while loop"
date: 2024-10-22T09:23:03-05:00
draft: false
tags: ["Python","Basic","while loop","do-while loop", "Learning notes"]
categories: ["Python"]
---
### while loop vs do-while loop
{{< figure src="/images/second-post/1.png" alt="structure" >}}

{{< figure src="/images/second-post/2.png" alt="structure" >}}

This is a standard `while` loop because:

- The condition `i < 5` is checked before each iteration.
- If `i` were greater than or equal to 5 from the start, the loop would not execute even once.

### Structure in python
{{< figure src="/images/second-post/3.png" alt="structure" >}}
{{< figure src="/images/second-post/4.png" alt="structure" >}}

This behaves like a `do-while` loop because:

- The loop starts with `while True:`, which guarantees that the loop body will execute at least once.
- Inside the loop, the condition `(i < 5)` is checked after the loop body has been executed.
- The `break` statement is used to exit the loop if the condition is not met, mimicking the post-condition check of a `do-while` loop.

### Can You Assume `while True:` is a `do-while` Loop?

You **can** assume that `while True:` **may** simulate a `do-while` loop **if** there is a condition inside the loop that determines whether the loop should continue or exit (using a `break` statement). However, not all `while True:` loops are `do-while` loops. The significant feature that makes a `while True:` loop similar to a `do-while` loop is **checking the exit condition inside the loop body after at least one execution**.

### Significant Features of Each

- **`while` Loop**:
    - Condition is evaluated before the loop body executes.
    - May not execute the loop body at all if the condition is initially `False`.
- **`do-while` Loop** (simulated with `while True:` in Python):
    - Loop body is guaranteed to execute at least once.
    - Exit condition is checked after the loop body has been executed.