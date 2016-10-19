---
title: Deploying the Host Guardian Service for guarded hosts and shielded VMs
ms.custom: na
ms.prod: windows-server-threshold
ms.topic: article
ms.assetid: 310b63d9-5ac7-4961-98ef-103af45d706a
manager: dongill
author: rpsqrd
ms.technology: security-guarded-fabric
--

# Deploying the Host Guardian Service for guarded hosts and shielded VMs

>Applies To: Windows Server 2016

One of the most important goals of providing a hosted environment is to guarantee the security of the virtual machines running in the environment.  As a cloud service provider or enterprise private cloud administrator, you can use a guarded fabric to provide a more secure environment for VMs. A guarded fabric consists of one Host Guardian Service (HGS)???typically, a cluster of three nodes???plus one or more guarded hosts, and a set of shielded virtual machines (VMs).

The following topics tell how to set up a guarded fabric.

- [Prerequisites for deploying Host Guardian Service and guarded hosts](guarded-fabric-deployment-prerequisites.md)
- [Setting up the Host Guardian Service - HGS](guarded-fabric-setting-up-the-host-guardian-service-hgs.md)
- [Appendix A - Configure Nano server as TPM attested guarded host](guarded-fabric-configure-nano-server-as-tpm-guarded-host.md)

## Deployment tasks for guarded fabrics and shielded VMs

The following table breaks down the tasks to deploy a guarded fabric and create shielded VMs according to different administrator roles. Note that when the HGS admin configures HGS with authorized Hyper-V hosts, a fabric admin will collect and provide identifying information about the hosts at the same time.    

<table>
<colgroup>
<col width="38%" />
<col width="38%" />
<col width="26%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">![Host Guardian Service administrator tasks](../media/Guarded-Fabric-Shielded-VM/guarded-host-hgs-administrator-tasks.png)</th>
<th align="left">![Fabric administrator tasks](../media/Guarded-Fabric-Shielded-VM/guarded-host-fabric-administrator-tasks.png)</th>
<th align="left">![Tenant administrator tasks](../media/Guarded-Fabric-Shielded-VM/guarded-host-tenant-administrator-tasks.png)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><img src="../media/Guarded-Fabric-Shielded-VM/1111.png" alt="Step 1" hspace="8" align="left" /> [Verify HGS prerequisites](guarded-fabric-deployment-prerequisites.md#prerequisites-for-the-host-guardian-service) <img src="../media/Guarded-Fabric-Shielded-VM/guarded-host-verify.png" alt="Step 1" hspace="8" align="right" /></p></td>
<td align="left"><p><img src="../media/Guarded-Fabric-Shielded-VM/2222.png" alt="Step 2" hspace="8" align="left" /> [Verify host&nbsp;prerequisites](guarded-fabric-deployment-prerequisites.md#prerequisites-for-hyper-v-hosts-that-will-become-guarded-hosts)&nbsp;<img src="../media/Guarded-Fabric-Shielded-VM/guarded-host-verify.png" alt="Step 2" hspace="8" align="right" /></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><img src="../media/Guarded-Fabric-Shielded-VM/3333.png" alt="Step 3" hspace="8" align="left" /> [Configure first HGS&nbsp;node](guarded-fabric-setting-up-the-host-guardian-service-hgs.md#configure-the-first-hgs-node)&nbsp;<img src="../media/Guarded-Fabric-Shielded-VM/guarded-host-configure-first-hgs-node.png" alt="Step 3" hspace="8" align="right" /> </p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p><img src="../media/Guarded-Fabric-Shielded-VM/4444.png" alt="Step 4" hspace="8" align="left" /> [Configure fabric DNS](guarded-fabric-setting-up-the-host-guardian-service-hgs.md#configure-the-fabric-dns) <img src="../media/Guarded-Fabric-Shielded-VM/guarded-host-configure-fabric-dns.png" alt="Step 4" hspace="8" align="right" /></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><img src="../media/Guarded-Fabric-Shielded-VM/5555.png" alt="Step 5" hspace="8" align="left" /> [Configure secondary HGS&nbsp;nodes](guarded-fabric-setting-up-the-host-guardian-service-hgs.md#configure-secondary-hgs-nodes) <img src="../media/Guarded-Fabric-Shielded-VM/guarded-host-configure-secondary-hgs-nodes.png" alt="Step 5" hspace="8" align="right" /></p></td>
<td align="left"><p>![Arrow](../media/Guarded-Fabric-Shielded-VM/guarded-host-bent-arrow-01.png)</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><img src="../media/Guarded-Fabric-Shielded-VM/7777.png" alt="Step 7" hspace="8" align="left" /> [Configure HGS with host information](guarded-fabric-setting-up-the-host-guardian-service-hgs.md#configure-hgs-with-authorized-hyper-v-hosts) <img src="../media/Guarded-Fabric-Shielded-VM/guarded-host-configure-hgs-with-host-info.png" alt="Step 7" hspace="8" align="right" /> </p></td>
<td align="left"><p><img src="../media/Guarded-Fabric-Shielded-VM/6666.png" alt="Step 6" hspace="8" align="left" /> [Collect information from hosts (TPM)](guarded-fabric-setting-up-the-host-guardian-service-hgs.md#tpm-trusted-attestation-capturing-hardware-and-software-information-that-hgs-uses-in-attestation) <img src="../media/Guarded-Fabric-Shielded-VM/guarded-host-collect-info-from-hosts.png" alt="Step 6" hspace="8" align="right" /></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><img src="../media/Guarded-Fabric-Shielded-VM/8888.png" alt="Step 8" hspace="8" align="left" /> [Verify HGS configuration](guarded-fabric-setting-up-the-host-guardian-service-hgs.md#verify-hgs-is-configured-properly) <img src="../media/Guarded-Fabric-Shielded-VM/guarded-host-verify-hgs-configuration.png" alt="Step 8" hspace="8" align="right" /></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p><img src="../media/Guarded-Fabric-Shielded-VM/9999.png" alt="Step 9" hspace="8" align="left" /> [Confirm hosts can attest](guarded-fabric-setting-up-the-host-guardian-service-hgs.md#confirm-hosts-can-attest-successfully) <img src="../media/Guarded-Fabric-Shielded-VM/guarded-host-confirm-hosts-attest.png" alt="Step 9" hspace="8" align="right" /></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p><img src="../media/Guarded-Fabric-Shielded-VM/101010.png" alt="Step 10" hspace="8" align="left" /> [Configure VMM (optional)](https://technet.microsoft.com/system-center-docs/vmm/scenario/guarded-overview) <img src="../media/Guarded-Fabric-Shielded-VM/guarded-host-configure-vmm.png" alt="Step 10" hspace="8" align="right" /></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p><img src="../media/Guarded-Fabric-Shielded-VM/11eleven.png" alt="Step 11" hspace="8" align="left" /> [Create template disks](guarded-fabric-create-a-shielded-vm-template.md) <img src="../media/Guarded-Fabric-Shielded-VM/guarded-host-create-template-disk.png" alt="Step 11" hspace="8" align="right" /></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p><img src="../media/Guarded-Fabric-Shielded-VM/121212.png" alt="Step 12" hspace="8" align="left" /> [Create a VM shielding helper disk for VMM (optional)](guarded-fabric-vm-shielding-helper-vhd.md) <img src="../media/Guarded-Fabric-Shielded-VM/guarded-host-create-helper-disk.png" alt="Step 12" hspace="8" align="right" /></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p><img src="../media/Guarded-Fabric-Shielded-VM/131313.png" alt="Step 13" hspace="8" align="left" /> [Set up Windows Azure Pack (optional)](guarded-fabric-shielded-vm-windows-azure-pack.md) <img src="../media/Guarded-Fabric-Shielded-VM/guarded-host-windows-azure-pack.png" alt="Step 13" hspace="8" align="right" /></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><img src="../media/Guarded-Fabric-Shielded-VM/141414.png" alt="Step 14" hspace="8" align="left" /> [Create shielding data file](guarded-fabric-tenant-creates-shielding-data.md) <img src="../media/Guarded-Fabric-Shielded-VM/guarded-host-shielding-data-file.png" alt="Step 14" hspace="8" align="right" /></p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><img src="../media/Guarded-Fabric-Shielded-VM/151515.png" alt="Step 15" hspace="8" align="left" /> [Create shielded VMs using Windows Azure Pack](guarded-fabric-shielded-vm-windows-azure-pack.md#steps-tenants-take-to-create-shielded-vms-with-windows-azure-pack) <img src="../media/Guarded-Fabric-Shielded-VM/guarded-host-shielded-vms.png" alt="Step 15" hspace="8" align="right" /></p>
<p><img src="../media/Guarded-Fabric-Shielded-VM/guarded-host-plain-spacer-15.png" alt="Step 15" hspace="8" align="left" /> [Create shielded VMs using VMM](https://technet.microsoft.com/system-center-docs/vmm/scenario/guarded-vms) <img src="../media/Guarded-Fabric-Shielded-VM/guarded-host-shielded-vms.png" alt="Step 15" hspace="8" align="right" /></p></td>
</tr></tbody>
</table>

## See also

- [Guarded fabric and shielded VMs](guarded-fabric-and-shielded-vms-top-node.md)