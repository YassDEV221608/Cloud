# Virtualization and Cloud Computing Guide

## 1. Virtualization

### Definition
Virtualization abstracts physical resources and presents them as logical resources. It can be applied to compute, storage, network, or applications.

### Types of Virtualization

#### Compute Virtualization
* Enables multiple operating systems to run on a single physical machine
* Uses hypervisors:
  * Type 1: Bare-metal
  * Type 2: Hosted
* Examples: VMware ESXi, Microsoft Hyper-V, Oracle VirtualBox
* Benefits:
  * Server consolidation
  * Isolation
  * Encapsulation
  * Hardware independence
  * Reduced cost
* Advanced features:
  * GPU virtualization for graphics-intensive applications
  * Oversubscription of resources (CPU, memory, storage)

#### Storage Virtualization
* Masks complexity and creates logical storage pools
* Benefits:
  * Non-disruptive data migration
  * Heterogeneous storage support
  * Improved utilization
* Techniques:
  * Block-level virtualization (SAN)
  * File-level virtualization (NAS)
  * Thin provisioning and storage tiering

#### Network Virtualization
* Groups physical networks into logical segments (e.g., VLAN, VSAN)
* Components:
  * Virtual switches
  * Virtual NICs
  * Virtual HBAs
* Enables load balancing, multipathing, and resource sharing

## 2. Cloud Computing

### Definition
A model for on-demand network access to shared computing resources, enabling rapid provisioning and minimal management effort.

### Essential Characteristics (NIST)
1. On-demand self-service: Provision resources automatically
2. Broad network access: Accessible from various devices
3. Resource pooling: Multitenancy model for dynamic allocation
4. Rapid elasticity: Scales resources based on demand
5. Measured service: Pay-as-you-go model based on usage

### Service Models
* SaaS (Software as a Service): Applications accessed via internet
* PaaS (Platform as a Service): Development platforms provided as service
* IaaS (Infrastructure as a Service): Virtualized infrastructure like VMs, storage

### Deployment Models
* Private Cloud: Dedicated to single organization
* Public Cloud: Open to multiple customers
* Hybrid Cloud: Combination of private and public
* Community Cloud: Shared by organizations with similar needs

## 3. Cloud Infrastructure

### Building Blocks
* Compute, storage, network, applications, DBMS
* Requires virtualization to enable pooling and elasticity

### Virtualized Data Centers (VDCs)
* Infrastructure is virtualized to support cloud services
* Includes virtual NICs, switches, and distributed virtual switches

### Virtualization Techniques
* Thin Provisioning: Allocates storage as needed
* Automated Storage Tiering: Moves data between storage tiers
* Datastores and VMFS: Native file systems for managing VM files

## 4. Resource Management
* Ensures efficient allocation and prevents resource monopolization
* Uses resource pools, limits, shares, and reservations
* Supports VM migration, failover, and load balancing

## 5. Networking in Virtualized Environments
* Virtual Switches: Provide OSI layer 2 functionality
* Distributed Switches: Manage networks across multiple hosts
* Multipathing: Ensures data transfer reliability
* VSAN and VLAN: Logical segmentation of traffic

## 6. P2V Conversion
* Converts physical machines into VMs
* Benefits:
  * Time-saving
  * Legacy system migration
  * Heterogeneous hardware support

## 7. Benefits of Virtualization
* Operational: Reduces downtime, simplifies management
* Cost Efficiency: Decreases hardware and operational costs
* Scalability: Rapidly adapts to changing workloads
