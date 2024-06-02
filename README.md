# Decommissioning of KEK's iRODS services for T2K and Hyper-Kamiokande <!-- omit in toc -->

- [Decommissioning timeline](#decommissioning-timeline)
  - [Monday, June 3rd 2024](#monday-june-3rd-2024)
  - [Friday, August 30th, 2024](#friday-august-30th-2024)
- [Accessing iRODS data with SRM and WebDAV protocols through VOMS authentication](#accessing-irods-data-with-srm-and-webdav-protocols-through-voms-authentication)

Following [iRODS](https://irods.org/) services for T2K and HK experiments hosted at KEK will be decommissioned by the end of August 2024 after decades of operation for SRB, followed by iRODS. We preserve the existing data and offer data access in alternative ways, such as SRM and HTTPS, through VOMS authentication. See below for more details about [accessing iRODS data with SRM and WebDAV protocols through VOMS authentication](#accessing-irods-data-with-srm-and-webdav-protocols-through-voms-authentication).

- gsr03.cc.kek.jp (Zone: KEK-T2K)
- gsr04.cc.kek.jp (Zone: KEK-HK)

## Decommissioning timeline

The following timeline will be applied for the decommissioning steps:

### Monday, June 3rd 2024

- Announcement: Creating a [repository](https://gitlab.cern.ch/giwai/irods-decommissioning-2024) at gitlab.cern.ch and [EGI Broadcast](https://operations-portal.egi.eu/broadcast/archive/9999).
- The iRODS services will be provided in a read-only mode until the end of the day of services. Please remember that storing new data or creating a new account on or after this date is no longer possible.
- From this date, alternative access protocols such as SRM and WebDAV are available through VOMS authentication for data access stored in iRODS on a read-only basis.

### Friday, August 30th, 2024

Service is going to be decommissioned. The database backup and logs on the services must be secured and preserved at least 90 days from this date.

## Accessing iRODS data with SRM and WebDAV protocols through VOMS authentication

iRODS for T2K has two zones, KEK-T2K and KEK-XXX as well. Stored data in these zones can be accessed with the following SURLs and TURLs on a read-only basis:

|Zone|SURL|TURL|
| ---- | ---- | ---- |
|KEK-T2K| srm://kek2-se01.cc.kek.jp:8444/srm/managerv2?SFN=/irods/t2k.org | <https://t2k-webdav.cc.kek.jp/irods/t2k.org/>|
|KEK-XXX|srm://kek2-se01.cc.kek.jp:8444/srm/managerv2?SFN=/irods/disk/t2k.org|<https://t2k-webdav.cc.kek.jp/irods/disk/t2k.org/>|

For the zone KEK-HK, authenticated users can access existing data with the following SURL and TURL on a read-only basis.

|Zone|SURL|TURL|
| ---- | ---- | ---- |
|KEK-HK|srm://kek2-se01.cc.kek.jp:8444/srm/managerv2?SFN=/irods/hyperk.org|<https://hyperk-webdav.cc.kek.jp/irods/hyperk.org/>|

Since WLCG Storage Elements have different AuthNZ mechanisms from iRODS, the user-registration process for the VOs must be the first thing to do than anything.

- t2k.org: <https://voms.gridpp.ac.uk:8443/voms/t2k.org/register/start.action>
- hyperk.org: <https://voms.gridpp.ac.uk:8443/voms/hyperk.org/register/start.action>

Also, it should be noted that the time is now in the transition phase X.509 certificate authentication to token-based authentication as of Spring 2024. You may check the latest information about each VO enrollment at:

- <https://operations-portal.egi.eu/vo/view/voname/t2k.org>
- <https://operations-portal.egi.eu/vo/view/voname/hyperk.org>

Lastly, if you have any questions or comments, [please feel free to create the issue and let us know](/-/issues).
