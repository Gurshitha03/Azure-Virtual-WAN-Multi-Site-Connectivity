# Architecture

## Azure Virtual WAN Multi-Site Connectivity

The proposed architecture uses Azure Virtual WAN to provide centralized connectivity between three campuses and two Azure Virtual Networks (VNets).

The design provides a scalable networking model where multiple sites can connect through a centralized Virtual WAN hub instead of maintaining separate point-to-point connections.

### Proposed Architecture

The architecture consists of the following major components:

- Azure Virtual WAN
- Virtual WAN Hub
- Campus 1
- Campus 2
- Campus 3
- Azure VNet 1
- Azure VNet 2
- Routing and connectivity between sites

### Network Flow

The three campuses connect to the Azure Virtual WAN hub. The Virtual WAN hub provides centralized connectivity and routing between the connected sites and Azure VNets.

```text
                         Azure Virtual WAN
                                |
                        +-------+-------+
                        |               |
                  Virtual WAN Hub       |
                        |               |
             +----------+----------+----+----------+
             |          |          |               |
             |          |          |               |
         Campus 1   Campus 2   Campus 3         Azure
             |          |          |            VNets
             |          |          |           /     \
             |          |          |        VNet 1  VNet 2
             |          |          |
             +----------+----------+
                  Centralized
                  Connectivity
                  Multi-Site Connectivity
The project considers connectivity between three campuses and two Azure VNets.
The Virtual WAN architecture provides:
- Centralized network connectivity
- Simplified routing management
- Scalable site-to-site connectivity
- Connectivity between campuses and Azure resources
- Centralized control through the Virtual WAN hub
**Hub-and-Spoke Alternative**
A traditional hub-and-spoke architecture is also considered for comparison.
In the hub-and-spoke model, a central Azure hub VNet provides connectivity to multiple spoke VNets and connected sites.
                       Central Hub
                           |
             +-------------+-------------+
             |             |             |
           Spoke 1       Spoke 2       Spoke 3
             |             |             |
          Campus 1      Campus 2      Campus 3
                           |
                     Azure Resources
