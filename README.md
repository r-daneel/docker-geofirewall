# docker-geofirewall

This is a tiny bash script setting up a firewall inside a docker container.

It is VERY stupid in nature and assumes a couple of things:
- The container's iptables tables/chains are empty and can be flushed
- It assumes you have the xtables geoip extension installed in iptables on your docker host

You mainly provide it
- a list of ports you want to allow
- a list of subnets you want to allow traffic through (the defined ports)
- a list of country-codes you want to allow traffic through (the defined ports)

All the rest gets dropped.

NOTE:
> The default is to allow all local networks\
> If you override the list of allowed networks,
> add any private networks you want to retain
