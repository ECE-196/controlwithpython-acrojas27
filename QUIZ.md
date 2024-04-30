### How does the DevBoard handle received serial messages? How does this differ from the naïve approach?

### What does `detached_callback` do? What would happen if it wasn't used?
It allows code to run concurrently so that multiple operations can occur at once.
If it was not used, each line of code would run one by one and it would take more time to complete

### What does `LockedSerial` do? Why is it _necessary_?
