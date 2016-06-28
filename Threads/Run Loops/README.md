# Run Loops

A Run Loop is an event processing loop associated with every thread.

Each thread has an associated run loop object provided by Cocoa and Core Foundation. The run loop associated with the Application's Main Thread is setup and run by the Framework as part of the application startup process, however the one associated with any secondary thread has to be run explicitly. 

The code in a run loop is implemented by using any looping control statement like for or while. 
A thread enters its run loop on receiving incoming events. 
The code within the run loop uses a run loop object to process the events by calling the installed handlers.

The incoming events are from event sources.

Event sources could be:
* Input sources 
> Input sources deliver asynchronous events which get handled by the corresponding event handlers and cause the run loop to exit.

* Timer sources 
> Timer sources deliver synchronous events which get handled by the corresponding event handlers but do not terminate the run loop.

* Run Loop itself
> a run-loop generates notifications about its behavior which are handled by registered observers which can be installed using Core Foundation

### Run Loop Mode

A run loop mode constitutes of the event sources (input sources and timer sources) and a collection of 
run loop observers.

A mode can be specified with each iteration of a run loop. The default mode is "default", KSDefaultRunLoopMode for Cocoa and KCFRunLoopDefaultMode for Core Foundation. 

On each iteration, ONLY the sources associated with the "current" mode CAN deliver their events. The sources
that belong to other modes hold on to their events until the next iteration of the run loop with the appropriate mode is run.

Cocoa and Core Foundation defines several modes. 
* Default
* Connection 
* Modal
* Event Tracking
* Common Modes


Custom modes can also be defined, which could include one or more input sources, timer sources, or run loop observers.
