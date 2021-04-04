# General principles for reliable serverless systems

## If you didn't write it down, it didn't happen

Serverless systems should avoid any forms of ephemeral (in memory) state and any un-logged actions as it is impossible to determine what was going on should an execution fail and there be no evidence of what it was doing at the time.

## Communication should be asynchronous and queue based

To prevent single failures bringing down large parts of a serverless system the system should be designed with resiliency built in - specifically by designing for asynchronous communication and by having *in tray* work queues to hold the requests for each component.

## Do the very least you can do

In each serverless function the code should do the absolute minimum amount of work it can do, with additional functionality being added by composition and orchestration.  In addition whilst workflows may have multiple dependencies, individual serverless functions should not.

In summary the goal for a serverless function should be _Do one thing, do it well and leave it completely done or completely undone_
