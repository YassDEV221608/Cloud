# Storage Infrastructure and Management Guide

## 1. Storage Types and Architectures

### Direct Attached Storage (DAS)
* Simple setup with direct connection to a compute system
* Limited scalability and resource sharing

### Storage Area Networks (SAN)
* Overcomes DAS limitations by centralizing management and sharing resources
* Supports replication and geographically dispersed backups
* Common SAN types:
  * Fibre Channel (FC): High-speed optical communication
  * IP SAN: Uses IP protocols (e.g., iSCSI, FCoE)

### Network Attached Storage (NAS)
* High-performance file sharing using IP networks
* Supports CIFS and NFS protocols for file-level data access
* Unified NAS combines both file-level and block-level access

## 2. Fibre Channel (FC) in SAN

### Key Components
* Network adapters, cables (copper/optical), switches, and storage systems
* Addressing using WWN (World Wide Names) and FCID for unique device identification

### Interconnecting Options
* Point-to-Point: Direct connections, limited scalability
* FC-AL (Arbitrated Loop): Shared loop, low performance due to contention
* FC-SW (Switched Fabric): High scalability using switches and inter-switch links (ISLs)

### Security Mechanisms
* Zoning: Logical isolation to control communication paths
* LUN Masking: Prevents unauthorized access to logical units

## 3. iSCSI and FCoE

### iSCSI
* Encapsulates SCSI commands over IP for cost-effective implementation
* Utilizes IQN (iSCSI Qualified Names) for unique identification
* Hardware and software initiators available for connection

### FCoE (Fibre Channel over Ethernet)
* Consolidates FC and Ethernet traffic
* Requires CNAs (Converged Network Adapters) and FCoE switches
* Reduces infrastructure complexity and cost

## 4. Data Deduplication

### Methods
* File-level: Detects duplicate files
* Subfile-level: Detects duplicate data within files (fixed or variable block sizes)

### Implementations
* Source-based: Deduplication at the host level, reducing network bandwidth
* Target-based: Deduplication at the storage level

## 5. Storage Infrastructure Management

### Key Activities
* Availability Management
  * Ensuring redundancy
  * Deploying RAID
  * Clustering
* Capacity Management
  * Storage provisioning
  * Data compression
  * Deduplication
* Performance Management
  * Fine-tuning
  * Path configurations
  * RAID optimization
* Security Management
  * Access control
  * Encryption
  * Event auditing

### Virtualized Environments
* Virtualization of storage (e.g., LUNs)
* Network virtualization (e.g., VLAN, VSAN)
* Compute virtualization (e.g., VMs)

## 6. Monitoring and Alerts

### Monitored Parameters
* Host:
  * CPU
  * Memory
  * File system usage
* Network:
  * Switches
  * Zones
  * Port utilization
* Storage:
  * Disk health
  * Replication processes
  * I/O response times

### Alert Categories
* Informational: No immediate action needed
* Warning: Requires attention
* Fatal: Immediate action necessary
