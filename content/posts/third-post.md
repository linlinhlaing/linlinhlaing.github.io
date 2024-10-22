---
title: "Immutable vs mutable object"
date: 2024-10-22T10:23:23-05:00

draft: false
tags: ["Python","Immutable","Mutable","Pass by value", "Pass by reference", "Learning notes"]
categories: ["Python"]
---
### Pass by Value
- The function receives a copy of the argument’s value.
- Modifications to the parameter inside the function do not affect the original argument.
### Pass by Reference
- The function receives a reference (or address) to the actual argument.
- Modifications to the parameter inside the function affect the original argument because both the argument and the parameter refer to the same memory location.
### Mutable Objects (like lists or dictionaries):
 The function can modify the object in place, and those changes will be reflected outside the function.

 {{< figure src="/images/third-post/1.png" alt="mutable object">}}
 **Explanation**:

- `my_list` is a list, which is mutable.
- When `my_list` is passed to `modify_list()`, the function receives a reference to the same list object.
- The `append` operation modifies the list object directly, so `my_list` reflects this change outside.

 {{< figure src="/images/third-post/3.png" alt="mutable object">}}

### Immutable Objects (like integers, strings, tuples):
 Since these objects cannot be modified, any operation that seems to change the object actually creates a new object. This makes it *appear* like "pass by value," but technically it's still passing a reference to the original object.

{{< figure src="/images/third-post/2.png" alt="Immutable object">}}
**Explanation**:

- `my_number` is an integer, which is immutable.
- When `my_number` is passed to `modify_integer()`, the function gets a reference to the integer object `10`.
- Inside the function, `n += 1` creates a new integer object `11` and assigns it to the local variable `n`, but this does not affect `my_number` outside the function.
 {{< figure src="/images/third-post/4.png" alt="Immutable object">}}

### Key Takeaways

- **Python is "pass by object reference"**: It passes references to objects, but the way these references behave depends on whether the object is mutable or immutable.
- **Mutable objects** (like lists and dictionaries) can be changed in place inside a function, and these changes will reflect outside the function.
- **Immutable objects** (like integers, strings, and tuples) cannot be altered in place; operations that seem to modify them actually create new objects.

**In Python, mutable objects are passed by reference (or more accurately, by object reference).**

### note
- Mutable ဆိုတာက object creation လုပ်ပီးပေမဲ့ change လို့ရတာ
- Pass by reference ကလဲ value passပေးလိုက်ပေမဲ့ object ရဲ့ memory location ပါpassပေးလိုက်တာ
- တခုခု modify လုပ်လိုက်တာနဲ့ Original argument ကိုaffectဖြစ်စေတယ်
အဲ့တော့ function အပြင်ရော အထဲမှာပါ valueရဲ့changesက affectဖြစ်သွားတယ်

- Immutable object ကpass by valueနဲ့သဘောတရားတူ