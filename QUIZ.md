### How does the DevBoard handle received serial messages? How does this differ from the naïve approach?
A variable "Serial" is created in the App class and a another class cis created for the Serial Port. A menu is made to select the Serial port necessary because it is not limited to one specific port. We communicate back to the DevBoard by creating a write function that will handle error responses.
Our code is event driven by an interrupt and the computer receives each byte and determines if it is valid or invalid.

### What does `detached_callback` do? What would happen if it wasn't used?
It allows code to run concurrently so that multiple operations can occur at once. Python is single threaded and the UI will remain frozen until the serial code is done executing 
If it was not used, each line of code would run one by one and it would take more time to complete. It helpes to prevent the UI from becoming frozen if any of the serial code gets stuck/takes too long using a decorator.

### What does `LockedSerial` do? Why is it _necessary_?
Since  multiple threads can use the serial port at once, we wrap the serial in a lock, which locks an object until it is released.
It is necessary to allow the Serial function while also locking every cell.

