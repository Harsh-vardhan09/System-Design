**Server serves response with more users we need more server to process the LOAD**
## Hashing

- When a request comes there will be request id from 0 to m-1.
- we can hash the ID and use 
  `h(r1)=m1%n` so the remainder decides the Server where it goes.
  
> [!tip] Problem
> - when we add the new server we need to add new number in the formula.
>  - since we are being sent to same server for same value hash we should be able to cache it but
>  - Due to change in modulo the server changed so then we are sent to different server 
>  - This takes the advantage


![[Pasted image 20261005181538.png]]
  
# Consistent Hashing

![[Pasted image 20261005182832.png]]

- Consider a Ring of hash instead of array
- so based on this each server is also given a value and hashed and given a position in the ring
- so each of the request is served by closest sever in clockwise
![[Pasted image 20261005183854.png]]

> [!tip] the problem
>  theoretically the load should be `1/n` but the load can be skewed distributed

# To fix the problem

- we can use multiple hash function 
- we can have `k hash function` we can have a server hashed to multiple points.
- This allows the load to be skewed very low

 