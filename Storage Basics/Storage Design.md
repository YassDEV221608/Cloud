# Storage Systems Technical Documentation

## 1. Addressing Methods

### CHS (Cylinder, Head, Sector)
* Traditional method used in HDDs
* References data by physical location on disk  
* Uses cylinder (concentric tracks), head (read/write head), and sector coordinates

### LBA (Logical Block Addressing)
* Modern method that simplifies addressing
* Assigns sequential numbers to blocks
* More efficient than CHS

## 2. Performance Factors (Disk Service Time)

### Seek Time
* Time taken for the read/write head to move to the correct track
* Full stroke: Time to move head across entire disk
* Track-to-track: Time to move between adjacent tracks 
* Average seek time: Typically between full stroke and track-to-track

### Rotational Latency
* Time for platter to rotate to correct position
* Formula: Average rotational latency = 1/2(RPM/60)
* Example: For 7200 RPM drive, latency = 1/2(7200/60) = 4.17ms

### Data Transfer Rates
* Internal: Speed from platter to buffer
* External: Speed from disk interface to Host Bus Adapter (HBA)

## 3. Storage Design Calculations

### IOPS Overview
IOPS (Input/Output Operations Per Second) is a common unit of measurement in computing. It is used in performance testing of storage media such as hard disk drives (HDD), solid-state drives (SSD), and SAN storage networks.

### Capacity Planning
* Calculate total storage needs with redundancy:
  * Current data volume
  * Growth projections
  * Backup requirements 
  * System overhead
  * RAID level overhead
  * Hot spares
  * Snapshot space

### Performance Planning
```
Disks for Performance (DP) = Application IOPS / Single Disk IOPS
```

### Disk Service Time Calculation
```
TS = Seek Time + 0.5(Disk RPM/60) + (Data Block Size / Data Transfer Rate)
```

### IOPS Calculation
```
IOPS per disk = 1/TS
Total Disks Required = max(DC, DP)
```

> **Note**: The final number of disks needed is determined by whichever requirement is larger - capacity or performance. This ensures both requirements are met while being resource-efficient.
