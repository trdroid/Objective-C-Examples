# Grand Central Dispatch (GCD)

GCD is a thread pool managed by the OS which is designed to make concurrency easy to program and efficient to execute. It decides the number of threads to use and when they should be scheduled for execution. 

GCD provides a C interface for submitting blocks. Cocoa provides a higher-level API to GCD by providing classes like
* NSOperationQueue
* NSInvocationOperation
* NSBlockOperation

