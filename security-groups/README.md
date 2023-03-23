# AWS Security Groups

## Security Groups

Statefull - If a request is accepted by security group then the response is automatically accepted by the security group even if exists some outbound rule blocking this port.

Inbound Accepted = Outbound Accepted

## Network Access Control List (NACL)

Stateless - If a request is accepted by inbound rules when the response to this request goes through the NACL the NACL will evaluate outbound rules, then if exists any rule where the port is blocked the request will be reject.

Inbound Accepted = Outbound Accepted if NACL explicit rule for this.