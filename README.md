# Accidental Immutability through Accessor Methods in Ruby

This example demonstrates a subtle bug in Ruby where an accessor method (getter) can unintentionally prevent modification of an instance variable if a corresponding setter method is absent.  This can lead to unexpected behavior and difficult-to-debug issues.

**The Bug:**
The `MyClass` class has a getter method for `@value`, but lacks a setter. While the getter works to retrieve the value, any attempt to assign a new value using `my_object.value = 20` will fail to update the internal `@value`. This isn't a syntax error; the assignment is simply ignored, making the instance variable effectively immutable despite appearances.

**The Solution:**
To correct this, add an explicit `value=` setter method to allow modification of the instance variable.
