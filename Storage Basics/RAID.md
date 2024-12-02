# RAID Systems Documentation

## 1. Core Concepts

### RAID Controller Types
* Hardware controllers
  * Dedicated hardware
  * Better performance
  * Offloads processing from system
* Software controllers
  * Uses system CPU
  * Lower performance
  * More cost-effective
* Provides abstraction between OS and physical disks

## 2. RAID Levels

### RAID 0 (Striping)
* Data striped across multiple disks
* No redundancy/fault tolerance
* 100% capacity utilization
* Write penalty: 1 (best performance)
* Ideal for: Temporary data, performance-critical applications
* Risk: Complete data loss if any drive fails

### RAID 1 (Mirroring)
* Exact copy (mirror) of data on second drive
* 50% capacity utilization
* Survives single drive failure
* Write penalty: 2 (writes to both drives)
* Ideal for: OS drives, critical data
* High read performance (can read from either drive)

### RAID 10 (1+0, Stripe of Mirrors)
* Combines RAID 1 and RAID 0
* 50% capacity utilization
* Survives multiple drive failures (one per mirror)
* Write penalty: 2
* Better fault tolerance than RAID 01
* Ideal for: Database servers, email servers
* Recovery is faster than RAID 5/6

### RAID 01 (0+1, Mirror of Stripes)
* Less common than RAID 10
* 50% capacity utilization
* Lower fault tolerance than RAID 10
* One drive failure affects entire stripe set
* Not recommended for critical systems

### RAID 5 (Striping with Parity)
* Distributed parity across all drives
* Capacity: ((n-1)/n) × 100%
* Survives one drive failure
* Write penalty: 4 (read-modify-write cycle)
* Minimum 3 drives required
* Rebuild process impacts performance
* Risk: Vulnerable during rebuild

### RAID 6 (Striping with Dual Parity)
* Two parity blocks per stripe
* Capacity: ((n-2)/n) × 100%
* Survives two simultaneous drive failures
* Write penalty: 6 (highest)
* Minimum 4 drives required
* Ideal for: Large capacity storage arrays
* Better protection during rebuilds than RAID 5

## 3. Performance Calculations

### Disk Load Formula
```
Disk Load = (Read IOPS × Read%) + (Write IOPS × Write% × Write Penalty)
```

### IOPS Calculations
```
Raw IOPS = Disk IOPS × Number of Disks
Functional IOPS = (Raw IOPS/RAID Penalty × Write%) + (Raw IOPS × Read%)
```

## 4. Advanced Features

### Hot Spare
* Standby drive for automatic replacement
* Immediate RAID rebuild when failure occurs
* Can be dedicated to specific array or global
* Reduces system vulnerability period

### Cache Operations

#### Read Cache
* Read Hit: Data found in cache (fast)
* Read Miss: Data must be read from disk (slow)
* Prefetch algorithms for optimization

#### Write Cache
* Write-Through: Writes to cache and disk simultaneously
* Write-Back: Writes to cache first, then disk (faster but riskier)

### Recovery Procedures
* Automatic rebuild with hot spare
* Manual rebuild with replacement drive
* Rebuild priority can be adjusted
* Performance impact during rebuild:
  * RAID 5: 20-30% degradation
  * RAID 6: 25-35% degradation
  * RAID 10: Minimal impact

## 5. Best Practices

1. Never mix drives of different:
   * Capacities
   * Speeds
   * Technologies
2. Consider rebuild time when choosing array size
3. Use hot spares for critical systems
4. Monitor array health regularly
5. Implement regular backup strategy regardless of RAID level
