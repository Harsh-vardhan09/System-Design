# Monolith vs Microservices

![[Pasted image 20261005235730.png]]

|Feature|Monolith|Microservices|
|---|---|---|
|**Architecture**|Single application|Multiple independent services|
|**Deployment**|Entire application deployed together|Each service can be deployed independently|
|**Codebase**|Usually one codebase|Usually separate service boundaries|
|**Database**|Common/shared database is common|Often each service owns its database|
|**Communication**|Function/method calls within app|HTTP/gRPC/message queues/events|
|**Scaling**|Scale the entire application|Scale individual services|
|**Development**|Simpler|More complex|
|**Testing**|Relatively easier|More difficult due to distributed system|
|**Deployment**|Simple|More infrastructure required|
|**Failure**|One failure can affect whole app|Failure can potentially be isolated to one service|
|**Technology**|Usually one primary tech stack|Different services can use different technologies|
|**Team Structure**|Suitable for small teams|Useful for larger teams|
|**Infrastructure**|Low complexity|Higher complexity|
|**Best for**|Small/medium apps, MVPs|Large/complex applications|
|**Example**|One Node.js backend containing auth, users, orders|Auth service + User service + Order service|
# Monolith

It's primarily that the application is **one deployable/runtime unit**.

- Under load this scales out into multiple server
- Good for small team 
- Lesser moving parts in this architecture
- Less duplication
- This is faster There is not Remote procedure call

> [!tip] Problem
> if there is fall of one service all services break
> There is no decoupling

![[Pasted image 20261006001619.png]]
# Microservice

With microservices, you split the application into **independently running/deployable services**, usually around business capabilities.

- Easy to scale 
- need to understand the context of single service
- Parallel developing is possible
- Easy to deploy and scale for a single service
![[Pasted image 20261006002346.png]]