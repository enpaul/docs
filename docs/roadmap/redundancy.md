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

All primary data is stored
