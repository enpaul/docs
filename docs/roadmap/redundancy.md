# Redundancy Efforts

Currently the Homelab suffers from a critical lack of data redundancy. Fixing
this will require improvements both to the hardware and software layout of the
homelab.

## Goals

1. Improve data storage redundancy to mitigate loss-risk associated with
physical failures
2. Improve failover capacity, allowing for certain systems to be taken offline
in a controlled manner without losing services
3. Institute a backup creation and management system to reduce risk of
data corruption

## Storage Redundancy

### Current State

All primary data is stored on a single 8TB drive array in hardware RAID 5. The
array is comprised of four Western Digital Red NAS drives, each with a 3TB
capacity. The array is fault tolerant, but not redundant. Secondary data is
stored in one of three places: the primary array, a secondary drive array, or
the 256GB boot drive of a single server.

The secondary array is 470GB aggregate, comprised of four HST Travelstar 10K
SAS drives, also in hardware RAID 5. The boot drive of the server is a consumer
grade SSD. None of these systems are backed up or redundant.

Primary data includes personal data including books, projects, documents,
documentation, photos, etc. Secondary data is application configuration
information and deployed hosting systems.

In addition to the primary and secondary data, there is the tertiary data of
a media collection (movies, TV, etc). Tertiary data is stored on the primary
drive array, only because there is nowhere else with enough capacity to store
it.

### Desired State

Data should be more efficiently segregated by priority tier. The two drive
arrays should be split up into two arrays each: a pair of 3TB arrays using the
WD Red's and a pair of 146GB array's using the Travelstars. Each pair of arrays
should be installed into the two [Dell R410's](../hardware/poweredge-r410.md).
Secondary data exists on the 146GB arrays on each server and is routinely
backed up to the 3TB arrays on the same server.

Primary data should be cloned on both of the 3TB arrays. Primary data should
be backed up externally to a third server.
