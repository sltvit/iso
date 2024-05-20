#### Network Restrictions
Competition PCs are to have no internet access aside from what is minimally required to log in to Steam and CS and run the game.

- Block access to everything and allow only UDP traffic to AS32590 blocks (http://bgp.he.net/AS32590#_prefixes) to avoid any content hosted on 3rd party sites from getting onto the tournament machines. Blocking all non-UDP traffic, primarily TCP access, even to our AS32590 blocks is also required, because our IP ranges still deliver game content, and malicious participants can have game content masquerading as different appid on Steam Greenlight, Early Access, or the Workshop.

- Have the tournament LAN ports 27015-27050 open for TCP and UDP to Valve network AS. This will just allow WebSocket connections to be used for logon traffic.

- Ideal implementation will be proactively dropping non-UDP connections with TCP resets or similar low-level packets sent to initiating clients, which should hopefully help the client timeouts to be reasonable (as opposed to blackholing outgoing traffic and forcing the client to be stuck waiting for prolonged periods of time).

- Set the player machines to use local host (127.0.0.1) for DNS, otherwise players will experience stalls while trying to reach an external DNS due to the network restrictions.
