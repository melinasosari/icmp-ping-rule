# Windows Firewall Rule - Allow Ping from One windows only
This project sets up a custom rule in windows firewall that only alows *one windows machine**(e.g. Server or client) to ping *another windows machine*. All other systems are blocked from sending ICMP(Ping) requests.

Steps to create this rule:
1) Open Firewall Settings: open the *run menu* and type *wf.msc*
2) Create a  New Inbound Rule:
   1) select *inbound rule* click *new rule*
   2) Choose *custom* then click next
   3) Choose *All Programs* then click next
   4) for *Protocol Type* choose *Icmpv4* then select *customize* 
   5) select *Specific ICMP types* then choose *Echo request*
   6) under *remote ip address* select *these ip addresses*:
      -add the IP address of the allowed computer(e.g. DC) 
   7)Choose the firewall profiles(public or private or domain) depending on your network
   9) Choose *Allow the connection*
   10) type a name for example *Allow Ping from DC*
   11) Finish the rule

Result: now, only the specified machine (e.g. DC) will be able to ping this computer. other systems will be blocked by the firewall.
