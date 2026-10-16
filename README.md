# Awesome-Cloud-Native-Networking-EBPF

## Top Cloud-Native Networking & eBPF Ecosystem



**Curated List of SaaS Products & Open-Source GitHub Projects**  

*Focused on eBPF Dataplanes, Network Policy & Kubernetes-Native Observability*  

**Last updated: October 2026**



This repository tracks notable **SaaS platforms** and **open-source projects** for **Cloud-Native Networking & eBPF**. These tools enable organizations to provide pod connectivity, enforce network policies, and gain deep observability into cluster traffic—from traditional iptables-based CNIs to eBPF-powered dataplanes that bypass kube-proxy entirely.



**Examples** include Calico Enterprise, Tigera Cloud, Isovalent Enterprise Cilium, VMware NSX, AWS VPC CNI, Azure CNI, Weave Net, Flannel, OVN-Kubernetes, and Cilium (the category leaders).



**Open-source emphasis**: This section is heavily expanded with every major active project for self-hosting, eBPF-based networking, and open observability—ideal for platform engineers, SREs, and organizations seeking transparent, vendor-independent cloud-native networking.



Contributions welcome! Open a PR to add/update entries. Keep descriptions factual and link to official sites.



## Table of Contents

- [Sector Overview & Market Dynamics](#sector-overview--market-dynamics)
- [SaaS/Hosted Platforms](#saas-hosted-platforms)
- [Open-Source GitHub Projects](#open-source-github-projects)
- [How to Contribute](#how-to-contribute)
- [Disclaimer](#disclaimer)

## Sector Overview & Market Dynamics

The global cloud-native networking and container networking market is estimated at approximately **$3.5B to $7B** (with the broader Cloud-Native Network Functions market exceeding $25B and projected to surpass $70B by the 2030s at a ~20% CAGR), while specialized kernel-level eBPF networking and security constitutes an emerging sub-segment expanding towards $5B+. The sector is **moderately fragmented and dual-structured**: public cloud hyperscalers dominate the commoditized native VPC overlay tier, while high-performance eBPF dataplanes, advanced network policy enforcement, and observability represent an open-source-anchored battleground led by Cilium and Calico enterprise ecosystems alongside consolidating enterprise networking giants (Cisco, Broadcom).

## SaaS/Hosted Platforms

| Product | Company | Valuation / Revenue | Starting Pricing | Free Tier / Trial Limits | Description |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **[Azure CNI](https://azure.microsoft.com/)** | Microsoft | ~$3.1T Market Cap / ~$245B Annual Revenue | $0.00 (Included with AKS; AKS Standard tier starts at $0.10/cluster/hour, ~$73/month) | **Free tier available**: AKS Free control plane tier covers up to 1,000 nodes at $0/month (standard Azure compute/VNet egress resource usage charged separately). | **Native Azure CNI** with VNet integration. Azure CNI Overlay provides overlay networking without consuming VNet IP space. Default for AKS. |
| **[AWS VPC CNI](https://aws.amazon.com/)** | Amazon (AWS) | ~$1.9T Market Cap / ~$105B+ AWS Annual Revenue Run Rate | $0.00 (Software is free; EKS managed control plane starts at $0.10/cluster/hour, ~$72/month) | **Trial/Credit tier**: No permanent free control plane tier; eligible for AWS Free Tier $100–$200 promotional credits (expires in 6 months; standard EC2/VPC infrastructure billable). | **Native AWS CNI** assigning VPC IP addresses directly to pods. Default for EKS—pods are first-class VPC citizens with native AWS networking integration. |
| **[VMware NSX](https://www.vmware.com/)** | Broadcom | ~$800B Market Cap / ~$50B+ Annual Revenue | Subscriptions start per-core via VMware Cloud Foundation (VCF) / vDefend bundles (~16-core minimum per CPU socket) | **60-day free trial**: Full evaluation mode for 60 days across NSX Manager and container plugins; reverts to read-only/restricted mode upon expiration. | **Enterprise network virtualization and security platform** with container networking via NSX Container Plugin (NCP). Deep integration with vSphere and Tanzu. |
| **[Isovalent Enterprise Cilium](https://pages.solo.io/rs/132-VJP-402/images/Service_mesh_buyers_guide.pdf?version=0#7#3)** | Cisco (Isovalent) | ~$230B Market Cap / ~$54B Annual Revenue (Isovalent acquired for ~$650M) | Starting tier estimated at ~$1,000/node/year (unit-based licensing via Cisco / Cloud Marketplaces) | **Interactive labs / Custom trial**: Free hands-on access via Isovalent Interactive Labs (unlimited, no expiration for learning); custom enterprise evaluation licenses available upon request. | **Enterprise version of Cilium** with troubleshooting, operational support, and multi-cluster capabilities. Cluster Mesh enables cross-cluster failover and multicloud connectivity. |
| **[Calico Cloud](https://docs.tigera.io/calico/latest/about/product-comparison)** | Tigera | ~$100M–$150M Valuation (~$25M+ ARR) | Pay-as-you-go starting at $0.025/vCPU-hour (~$0.05–$0.08/node-hour or ~$350/node/year) | **Free tier available**: Permanent Free Tier covers 1 Kubernetes cluster (requires Calico Open Source 3.30+, includes Dynamic Service Graph and view-only policy board); also offers a 14-day full-feature trial (no credit card required). | **Fully managed SaaS platform for Kubernetes networking and security**. Provides policy management, runtime observability, and service graphs without managing infrastructure. |
| **[Calico Enterprise](https://docs.tigera.io/calico/latest/about/calico-product-editions)** | Tigera | ~$100M–$150M Valuation (~$25M+ ARR) | Annual subscriptions based on node/vCPU count via private marketplace offers | **Custom evaluation trial**: Multi-week trial license provided on request via Tigera technical sales; alternative hands-on trial available via Calico Cloud 14-day trial. | **Self-managed enterprise platform** extending Calico Open Source with hierarchical tiered network policy, DNS/FQDN policy, policy recommendations, SIEM integrations, workload WAF, and compliance reporting. |
## Open-Source GitHub Projects



- **[Cilium](https://github.com/cilium/cilium)**  

  **eBPF-based Networking, Security, and Observability** (Apache-2.0) . **The de facto standard for cloud-native networking**—**over 60% of CNI deployments** according to the State of Kubernetes Networking report, **more than double the next alternative** . **24,000+ GitHub stars** and **1,010+ developers** . **Core capabilities**: **CNI plugin** for pod connectivity, **identity-based NetworkPolicy** enforcement at L3/L4, **L7 policy** for HTTP/gRPC/Kafka, **ClusterIP load-balancing via eBPF** (bypassing kube-proxy), **Multi-Pool IPAM**, **ztunnel mTLS integration**, and **IPv6-first support** . **Hubble** provides **fully distributed networking and security observability**—answering "which services experienced DNS resolution problems?", "what is the 99th percentile latency?", and "which connections were blocked by policy?" . **Adopted by all major cloud providers** including GKE Dataplane V2, Azure Kubernetes Service, and OVHcloud's Managed Kubernetes Service . **The reference implementation for eBPF-based Kubernetes networking** .



- **[Calico Open Source](https://github.com/projectcalico/calico)**  

  **Open-source networking and security for containers, virtual machines, and native host-based workloads** (Apache-2.0) . **The most widely used container networking solution**—supports **Kubernetes, OpenShift, OpenStack, and bare metal** . **Core capabilities**: **high-performance pod networking**, **advanced IP address management**, **seamless Kubernetes NetworkPolicy support**, **global default deny policy**, **DNS/FQDN-based policy**, **data-in-transit encryption via WireGuard**, and **multiple dataplane options** (eBPF, iptables, nftables, Windows HNS, VPP) . **Calico's encryption performance is notable**: benchmark testing shows **Calico TCP bandwidth at 9,786 Mbit/s under encryption versus Cilium's 1,386 Mbit/s**—approximately **7x higher throughput** . **The enterprise-grade choice** for organizations requiring BGP peering with physical networks and strict policy enforcement .



- **[Flannel](https://github.com/flannel-io/flannel)**  

  **Simple, lightweight container network fabric** (Apache-2.0). **The easiest CNI for Kubernetes beginners**—**VXLAN or host-gw backends** with minimal configuration . **Does not support NetworkPolicy**—must be paired with Calico or similar for policy enforcement . **Best for**: learning, testing, small clusters, and environments without network policy requirements .



- **[Weave Net](https://github.com/weaveworks/weave)**  

  **Mesh overlay network with encryption and multicast support** (Apache-2.0). **Historically popular** but **community activity has declined significantly**—**not recommended for new projects** . **Performance under policy enforcement degrades severely**: benchmark testing shows **latency increasing from 7ms intra-node to 350ms under policy enforcement**—a **97% performance drop** . **Best for**: legacy deployments only.



- **[OVN-Kubernetes](https://github.com/ovn-org/ovn-kubernetes)**  

  **Open Virtual Network (OVN) based Kubernetes networking** (Apache-2.0). **The default CNI for OpenShift** and **Red Hat ecosystem** . **Uses OVS/OVN for logical networking** with **distributed ACLs applied via Kubernetes policies**, **IPAM support**, **load-balancing without kube-proxy**, and **NAT without iptables/netsh** . **Best for**: OpenShift, Red Hat, and environments requiring OVN integration.



- **[Antrea](https://github.com/antrea-io/antrea)**  

  **Kubernetes networking and security based on Open vSwitch** (Apache-2.0). **The VMware-backed alternative** to Cilium and Calico. **Features**: **NetworkPolicy enforcement**, **eBPF datapath** (Antrea-native), **Windows support**, **cluster networking**, and **observability**. **Best for**: VMware Tanzu and organizations preferring OVS-based networking.



### Additional Strong Open-Source Options



- **[Tetragon](https://github.com/cilium/tetragon)** — eBPF-based security observability and runtime enforcement from the Cilium project . **The emerging standard for runtime security**—detects process execution, network activity, and file access with eBPF.

- **[Hubble](https://github.com/cilium/hubble)** — Fully distributed networking and security observability platform built on Cilium and eBPF . **The standard for CNI-level observability**—answers DNS, latency, and policy-blocked connection queries.

- **[Kube-Router](https://github.com/cloudnativelabs/kube-router)** — Kubernetes network provider with IPVS-based service proxy and BGP-based routing (Apache-2.0). **Best for**: bare-metal BGP peering .

- **[Multus CNI](https://github.com/k8snetworkplumbingwg/multus-cni)** — Meta-plugin for attaching multiple network interfaces to pods (Apache-2.0). **The standard for multi-homed pods** .

- **[SR-IOV CNI](https://github.com/k8snetworkplumbingwg/sriov-cni)** — SR-IOV network device plugin for high-performance networking (Apache-2.0) .

- Community **n8n** workflows for network policy alerting and cluster event routing.



**Frameworks for building custom systems**: Combine **Cilium** for eBPF-native networking and observability with **Tetragon** for runtime security, **Hubble** for flow visibility, and **Calico Open Source** for BGP-based bare-metal deployments—creating a fully self-hosted, enterprise-grade cloud-native networking stack.



## How to Contribute



1. Fork the repo.

2. Add/edit entries in `README.md` (follow existing format).

3. Include: name, link, 1–2 sentence description, and whether it's SaaS or open-source.

4. Submit PR with a short explanation.



Star the repo if you find it useful!



## Disclaimer



- This is a **community-curated** list — not exhaustive and not an endorsement.

- Cloud-native networking tools handling cluster traffic must follow security best practices and implement appropriate network policies.

- **Open-source CNI is mature and production-ready.** Cilium represents **over 60% of CNI deployments** and is the dataplane for GKE, AKS, and major cloud providers . Calico is the most widely used container networking solution . **These are genuine alternatives to commercial platforms.**

- **Cilium vs Calico: the choice depends on your priorities.** Cilium offers **eBPF-native performance**, **L7 policy**, and **Hubble observability**—ideal for cloud-native, microservices-heavy environments . Calico offers **mature BGP peering**, **broader dataplane options**, and **significantly better encryption throughput** (9,786 vs 1,386 Mbit/s in benchmark testing) . **Cilium for observability and L7 policy; Calico for bare-metal BGP and encryption-heavy workloads** .

- **Weave Net should not be used for new projects.** Community activity has declined significantly , and benchmark testing shows **97% performance degradation under policy enforcement** . **Migrate to Cilium or Calico.**

- **Flannel is for learning, not production.** It provides simple VXLAN networking but **no NetworkPolicy support**—pair with Calico or Cilium for production .

- **eBPF is the future of cloud-native networking.** Cilium's eBPF dataplane **bypasses iptables entirely** for service routing, eliminating the scalability bottlenecks that plague traditional CNIs . **GKE Dataplane V2, Azure Kubernetes Service, and OVHcloud all run Cilium under the hood** .

- Self-hosted open-source solutions require proper kernel compatibility (eBPF requires Linux 5.4+, recommended 5.10+), CNI configuration, and ongoing maintenance . **Network policies are your primary security boundary**—default-deny is the recommended starting posture.



---



**Made for platform engineers, SREs, and organizations building transparent cloud-native networking solutions.**  

Let's make Cloud-Native Networking & eBPF more open, data-driven, and observable.
