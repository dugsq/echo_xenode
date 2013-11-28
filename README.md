Echo-Xenode
===========

**Echo Xenode** does what the name suggests: it echoes messages. This Xenode writes any and all of the messages it receives to all of its downstream children. It is perfect as a aggregator of messages coming from a large number of parent Xenodes that need to be distributed to a large number of children Xenodes. For example, if you have 10 parent Xenodes passing data to 10 children Xenodes, instead of setting up each parent to have 10 children with a total of 100 connections within the Xenoflow, put an Echo Xenode in the middle and now you only need to set up 1 children Xenode (the Echo Xenode) for each parent Xenode and 10 children Xenode for the Echo Xenode, and you accomplish the same task with only 20 connections, a design that is 5x more efficient.

###Configuration File Options:###
* loop_delay: defines number of seconds the Xenode waits before running the Xenode process. Expects a float. 
* enabled: determines if this Xenode process is allowed to run. Expects true/false.
* debug: enables extra debug messages in the log file. Expects true/false.

###Example Configuration File:###
* enabled: true
* loop_delay: 10
* debug: false

###Example Input:###
* msg.data: "String contains the data from one of the parent Xenodes."

###Example Output:###
* msg.data: "String contains the data from one of the parent Xenodes"
