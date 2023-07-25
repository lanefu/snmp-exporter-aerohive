# snmp-exporter-aerohive
Build Prometheus Explorer with specific aerohive mibs

## purpose

a custom configuration of snmp-exporter allows more data.. in this case.. better monitoring for my aerohive APs.

## approach

goal is to build by sourcing upstream repo, add customizations, and then cross compile artifiacts.

we'll decouple the binary artifacts from containers to make builds efficient.

### sadly above doesn't make sense as it's just the snmp.yml that needs to be generated :P 

### mibs

going to use aerohive mibs from https://github.com/netdisco/netdisco-mibs.git since they have some corrections. Fixes probably not needed, but why not.

all MIBS in folder aerohive
script
```bash
