# Nagios-monitoring and checks for ceph nodes for COI (Cisco Openstack Installer)

## Implementation Details.

**Blueprint URL** :[ https://blueprints.launchpad.net/openstack-cisco/+spec/nagios-check-for-ceph ] ( https://blueprints.launchpad.net/openstack-cisco/+spec/nagios-check-for-ceph )

**People working** :
* [Rahul Krishna Upadhyaya] (mailto:rahuupad@cisco.com) 
* [Satya Sanjibani Routray] (mailto:satroutr@cisco.com)

**Target Timeline** : h1 release of Cisco Openstack.

## Goal

Nagios for Ceph would allow the user/admin to view the health of ceph using a single _alert-viewing interface_ where he is already monitoring other system and openstack services/parameters. Goal of this feature addition would be to identify the health status of ceph on all the nodes it is present and report it accordingly to the Ceph dashboard.

## About Components

### Nagios 

*Nagios* is an open source computer system monitoring, network monitoring and infrastructure monitoring software application. Nagios offers monitoring and alerting services for servers, switches, applications, and services. It alerts the users when things go wrong and alerts them a second time when the problem has been resolved.

*NRPE* :Nagios Remote Plugin Executor (NRPE) is a Nagios agent that allows remote system monitoring using scripts that are hosted on the remote systems. It allows for monitoring of resources such as disk usage, system load or the number of users currently logged in. Nagios periodically polls the agent on remote system using the check_nrpe plugin.


* More about Nagios : [Nagios Documentation] (http://nagios.sourceforge.net/docs/nagioscore/3/en/toc.html)
* NRPE :  [Documentation on NRPE] (http://nagios.sourceforge.net/docs/nrpe/NRPE.pdf)

### Ceph

Ceph is a free software storage platform designed to present object, block, and file storage from a single distributed computer cluster. Cephs main goals are to be completely distributed without a single point of failure, scalable to the exabyte level, and freely-available. The data is replicated, making it fault tolerant. Ceph software runs on commodity hardware. The system is designed to be both self-healing and self-managing and strives to reduce both administrator and budget overhead.

* [Ceph Documentation] (http://ceph.com/docs/master/) 
* [Ceph Architecture] (http://ceph.com/docs/master/architecture/)
* [Ceph and Openstack] (https://wiki.debian.org/OpenStackCephHowto)

Source of Script being Used : [Source] ( https://github.com/valerytschopp/ceph-nagios-plugins )

## Interaction Diagram  

## Monitoring Steps
The Nagios scripts check the following things and report the health of ceph.

* Checks ceph executable is present
* Check ceph.conf file is present
* Check keyring file is present
* Check using ceph health command to check status.        
