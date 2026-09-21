Checks to see if there are no vtables. Only data is copied 

Hidden pointer (vptr) for every instance of the class. Points to ROM. 

When vptr is copied over, the pointer is now pointing to garbage values. This is cbecause in previous case, it pointed to sender specific value.

Not good for things like memcpy