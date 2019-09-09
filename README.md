# docker-geofirewall

This is a tiny bash script setting up a firewall inside a docker container.

It is VERY stupid in nature and assumes a lot of things:
- The container's iptables tables/chains are empty and can be flushed
- We're sitting behind a filtering NAT/PAT forwarding only the allowed ports, otherwise we're on a LAN
- It assumes you have the xtables & geoip extensions installed in iptables

You mainly provide it
- a list of ports you want to allow
- a list of subnets you want to allow traffic through (the defined ports)
- a list of country-codes you want to allow traffic through (the defined ports)

All the rest gets dropped.

NOTE:
> The default is to allow all local networks\
> If you override the list of allowed networks,
> add any private networks you want to retain
