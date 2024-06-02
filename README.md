## Decommissioning of KEK's iRODS services for T2K and Hyper-Kamiokande <!-- omit in toc -->

[/issues](/issues)

[/-/issues](/-/issues)

[../issues](../issues)


[[_TOC_]]

[TOC]

I am writing to notify whom it may concern about decommissioning the following iRODS (*1) services hosted at KEK.

- gsr03.cc.kek.jp (Zone: KEK-T2K)
- gsr04.cc.kek.jp (Zone: KEK-HK)

Although this broadcasting tool is probably not the best channel for the purpose above, it seems no better place to reach out to potential stakeholders of stored data as widely as possible. I apologise in advance if you are not concerned about this matter.

KEK's iRODS service for T2K and HK experiments will be decommissioned by the end of August 2024 after decades of operation for SRB, followed by iRODS. We securely preserve the existing stored data and offer the data access in alternative ways such as SRM and HTTPS through VOMS authentication. See below for more details about accessing iRODS data in SRM and HTTPS protocols through VOMS authentication (*2).

The following timeline will be applied for the decommissioning steps:

Mon, Jun 3rd 2024
- Announcement: Creating a GitLab repository (*2) and EGI Broadcast (*3).
- The services will be provided in a read-only mode until the end of the day of services. Please remember that storing any new data or creating an account on or after this date is no longer possible.
- From this date, accessing data stored in iRODS HTTPS

Fri, August 30th
Service will be decommissioned. The database backup and logs on the services must be secured and preserved at least 90 days from this date.

Issue:
Create an issue if you need assistance.



https://t2k-webdav.cc.kek.jp/irods/t2k.org/
https://t2k-webdav.cc.kek.jp/irods/disk/t2k.org/
https://t2k-webdav.cc.kek.jp/irods/hyperk.org/

https://operations-portal.egi.eu/vo/view/voname/t2k.org
https://voms.gridpp.ac.uk:8443/voms/t2k.org/register/start.action

VO Id Card
https://operations-portal.egi.eu/vo/view/voname/hyperk.org
Enrollment Url
https://voms.gridpp.ac.uk:8443/voms/hyperk.org/register/start.action


consult@kek.jp に質問するよう
GGUS ticket は作らなくとも良いか egi broadcast だけで良い

Sincerely yours,
Go Iwai -- Computing Research Centre, KEK

[1] https://ggus.eu/index.php?mode=ticket_info&ticket_id=154776
[2] https://goc.egi.eu/portal/index.php?Page_Type=Downtime&id=31357

