
**socketLB**
The socket-level loadbalancer acts transparent to Cilium's lower layer
datapath in that upon `connect`, `sendmsg`, or `recvmsg` system calls,
the destination IP is checked for an existing service IP and one of
the service backends is selected as a target.

This means that although the application assumes it is connected to
the service address, the corresponding kernel socket is actually
connected to the backend address and therefore no addiitional lower
layer NAT is required.


**socketLB bypass**
Cilium has built-in support for bypassing the socket-level
loadbalancer and falling back to the tc loadbalancer at the veth
interface when a custom redirectionoperation relies on the original
ClusterIP within pod namespace or due to the Pod's nature the
socket-level loadbalancer is ineffective.

Setting `socketLB.hostNamespaceOnly=true` enables this bypassing mode.


