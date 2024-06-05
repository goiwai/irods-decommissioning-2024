# Decommissioning of KEK's iRODS service for T2K and Hyper-Kamiokande <!-- omit in toc -->

- [Decommissioning timeline](#decommissioning-timeline)
  - [Monday, June 10th, 2024](#monday-june-10th-2024)
  - [Friday, August 30th, 2024](#friday-august-30th-2024)
- [Accessing iRODS data with SRM and WebDAV protocols through VOMS authentication](#accessing-irods-data-with-srm-and-webdav-protocols-through-voms-authentication)
  - [Alternative access points for the zone: KEK-T2K](#alternative-access-points-for-the-zone-kek-t2k)
  - [Alternative access points for the zone: KEK-HK](#alternative-access-points-for-the-zone-kek-hk)
  - [VO enrollment](#vo-enrollment)

Following *Storage Resources*[^resc] in [iRODS](https://irods.org/) *Zones*[^zone] for T2K and Hyper-Kamiokande experiments hosted at KEK will be decommissioned by the end of August 2024 after decades of operation for SRB, followed by iRODS. We preserve the existing data and offer data access in alternative ways, such as SRM and HTTPS, through VOMS authentication. See below for more details about [accessing iRODS data with SRM and WebDAV protocols through VOMS authentication](#accessing-irods-data-with-srm-and-webdav-protocols-through-voms-authentication).

|　Zone　  | Storage Resource | Hostname        |
| ------- | ---------------- | --------------- |
| KEK-T2K | hpssResc         | gsr03.cc.kek.jp |
| KEK-T2K | backupResc       | gsr03.cc.kek.jp |
| KEK-HK  | hpssResc         | gsr04.cc.kek.jp |

[^resc]: *Storage Resource* is a term in iRODS that refers to a critical concept of data virtualisation. iRODS enables multiple physical *Storage Resources* within a single logical storage, i.e. *Zone*.

[^zone]: *Zone* is another term in iRODS, which means a minimum unit to manage *Storage Resources*.

## Decommissioning timeline

The following timeline will be applied for the decommissioning steps:

### Monday, June 10th, 2024

- Announcement: Creating a [repository](https://gitlab.cern.ch/giwai/irods-decommissioning-2024) at gitlab.cern.ch and [EGI Broadcast](https://operations-portal.egi.eu/broadcast/archive/todo-fix-here).
- The iRODS services will be provided in a read-only mode until the end of the day of services. Please remember that storing new data or creating a new account on or after this date is no longer possible.
- From this date, alternative access protocols such as SRM and WebDAV are available through VOMS authentication for data access stored in iRODS on a read-only basis.

### Friday, August 30th, 2024

Service is going to be decommissioned. The database backup and logs on the services must be secured and preserved at least 90 days from this date.

## Accessing iRODS data with SRM and WebDAV protocols through VOMS authentication

### Alternative access points for the zone: KEK-T2K

iRODS for T2K has a zone KEK-T2K, which consists of two Storage Resources: hpssResc and backupResc. Stored data in these Storage Resources can be accessed with the following SURLs[^surl] and transfer URLs on a read-only basis:

|　Zone　  | Storage Resource | SURL        | WebDAV transfer URL |
| ------- | ---------------- | --------------- |-------------- |
| KEK-T2K | hpssResc         | srm://kek2-se01.cc.kek.jp:8444/srm/managerv2?SFN=/irods/t2k.org | <https://t2k-webdav.cc.kek.jp/irods/t2k.org/> |
| | | | <davs://t2k-webdav.cc.kek.jp/irods/t2k.org/> |
|  | backupResc       | srm://kek2-se01.cc.kek.jp:8444/srm/managerv2?SFN=/irods/disk/t2k.org | <https://t2k-webdav.cc.kek.jp/irods/disk/t2k.org/> |
| | | | <davs://t2k-webdav.cc.kek.jp/irods/disk/t2k.org/> |

[^surl]: Site URL

### Alternative access points for the zone: KEK-HK

For the zone KEK-HK, authenticated users are allowed read-only access to the existing data with SURL and transfer URL below:

|　Zone　  | Storage Resource | SURL        | WebDAV transfer URL |
| ------- | ---------------- | --------------- |-------------- |
| KEK-HK  | hpssResc         | srm://kek2-se01.cc.kek.jp:8444/srm/managerv2?SFN=/irods/hyperk.org | <https://hyperk-webdav.cc.kek.jp/irods/hyperk.org/> |
| | | | <davs://hyperk-webdav.cc.kek.jp/irods/hyperk.org/>　|

### VO enrollment

Since WLCG Storage Elements have different AuthNZ mechanisms from iRODS, the VO enrollment must be the first thing to do than anything. If you are eligible to be a VO member, take the following links for t2k.org and hyperk.org with an X.509 certificate imported web browser. Once accredited as a member of the VO, you can access the alternative access points shown in the tables above (for [KEK-T2K](#alternative-access-points-for-the-zone-kek-t2k) and [KEK-HK](#alternative-access-points-for-the-zone-kek-hk)).

- t2k.org: <https://voms.gridpp.ac.uk:8443/voms/t2k.org/register/start.action>
- hyperk.org: <https://voms.gridpp.ac.uk:8443/voms/hyperk.org/register/start.action>

It should also be noted that the time is now in the transition phase X.509 certificate-based authentication to token-based authentication as of Spring 2024. You may check the latest information about each VO enrollment at:

- <https://operations-portal.egi.eu/vo/view/voname/t2k.org>
- <https://operations-portal.egi.eu/vo/view/voname/hyperk.org>

Lastly, [please create the issue and let us know](https://gitlab.cern.ch/giwai/irods-decommissioning-2024/-/issues) if you have any questions or comments.

Sincerely yours,
Go Iwai -- Computing Research Centre, KEK

----
