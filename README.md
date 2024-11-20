
Nagios/Icinga2 monitoring plugin for Open-E storage

Monitors the ZFS Pool state and dumps ARC and L2ARC stats
to Nagios/Icinga2 performance data

    ./check_opene_zfs -H 172.26.224.22 -C public 
    OPENE_ZFS OK - Data-1 online(1) | zfsARCSizeKB=25255100KB;; 
        zfsARCMetadataSizeKB=274545KB;; zfsARCDataSizeKB=24982592KB;; 
        zfsARCHits=5282784231c;; zfsARCMisses=165977682c;; 
        zfsL2ARCHits=97583282c;; zfsL2ARCMisses=68394340c;; 
        zfsL2ARCReads=48119966519c;; zfsL2ARCWrites=95131924067c;;

Versions
========

From version 30 on OpenE broke the SNMP Mibs by making non backward
compatible changes to the mib. The knowledge base article mentions
"rearranging SNMP oids" which one does not do under any circumstance.
Additonally there is no way to read out the version supported. So 
it involves some guessing by reading out values and detecting brokeness.

If you have no clue about SNMP, please do not write mibs, decide on OIDs
and renaming of stuff.

See:

https://kb.open-e.com/jdss-changes-for-zfs-parameters-in-nymnetworks-mib-after-updating-to-up30r2_3541.html

Dependencies
============

    apt-get install libgetopt-long-descriptive-perl libnet-snmp-perl libmonitoring-plugin-perl
