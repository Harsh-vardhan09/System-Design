**Client can request to the server and it returns a response that the request has been added to the list.**

A List maintains the order and can be added to the queue.

![[Pasted image 20261005200611.png]]

*Once done it is removed from the queue. This whole process is asynchronous.*

*Orders can be put according to priority.*

## when there are multiple services

- if a service goes down we can send the request to other services
- To do this we need Database to persist the data.

## how to re-route the requests

- we use a type of notifier and checks if the server is alive
- if Server is dead and picks the order not done and distribute them
- To fix the problem for duplicate we use `LOAD BALANCING`

![[Pasted image 20261005201324.png]]

