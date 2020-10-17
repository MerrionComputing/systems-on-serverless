# General principles for reliable serverless systems

## If you didn't write it down, it didn't happen

Serverless systems should avoid any forms of ephemeral (in memory) state and any un-logged actions as it is impossible to determine what was going on should an execution fail and there be no evidence of what it was doing at the time.

## Communication should be asynchronous and queue based

To prevent single failures bringing down large parts of a serverless system the system should be designed with resiliency built in - specifically by designing for asynchronous communication and by having *in tray* work queues to hold the requests for each component.
