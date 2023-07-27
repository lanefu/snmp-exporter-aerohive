# snmp-exporter-aerohive
Build Prometheus Exporter with specific aerohive mibs

## purpose

a custom configuration of snmp-exporter allows more data.. in this case.. better monitoring for my aerohive APs.

## approach

goal is to build by sourcing upstream repo, add customizations, and then cross compile artifiacts.

we'll decouple the binary artifacts from containers to make builds efficient.

### sadly above doesn't make sense as it's just the snmp.yml that needs to be generated :P 

### mibs

going to use aerohive mibs from https://github.com/netdisco/netdisco-mibs.git since they have some corrections. Fixes probably not needed, but why not.

place mibs in mibs folder

#### generating snmp.yml

`MIBSDIR` variable imporant

```bash
cd generator
MIBSDIR=mibs make generate
```

### converting hexadecimal to string

most of the string values are returned as hex... we need ot convert them..

apparently overrides in generator.yml is the most friendly way

https://www.robustperception.io/numbers-from-displaystrings-with-the-snmp_exporter/

#### update

overrides in generator.yml didn't cover all teh touchpoints. i had to manualy change some types in snmp.yl from OctetString to DisplayStirng
