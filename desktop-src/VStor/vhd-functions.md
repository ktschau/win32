---
MS-HAID: vhd.vhd\_functions
MSHAttr:
- PreferredSiteName:MSDN
- PreferredLib:/library/windows/desktop
title: Virtual Disk Functions
ms.technology: desktop
ms.prod: windows
ms.author: windowssdkdev
ms.topic: article
ms.date: 05/31/2018
---

# <span id="vhd.vhd_functions"></span>Virtual Disk Functions

The following functions are used in Virtual Disks:

## <span id="in_this_section"></span>In this section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Topic</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>[<strong>ApplySnapshotVhdSet</strong>](https://msdn.microsoft.com/library/Mt638034(v=VS.85).aspx)</p></td>
<td><p>Applies a snapshot of the current virtual disk for VHD Set files.</p></td>
</tr>
<tr class="even">
<td><p>[<strong>AddVirtualDiskParent</strong>](https://msdn.microsoft.com/en-us/library/Hh832154(v=VS.85).aspx)</p></td>
<td><p>Attaches a parent to a virtual disk opened with the <strong>OPEN_VIRTUAL_DISK_FLAG_CUSTOM_DIFF_CHAIN</strong> flag.</p></td>
</tr>
<tr class="odd">
<td><p>[<strong>AttachVirtualDisk</strong>](https://msdn.microsoft.com/library/Dd323692(v=VS.85).aspx)</p></td>
<td><p>Attaches a virtual hard disk (VHD) or CD or DVD image file (ISO) by locating an appropriate VHD provider to accomplish the attachment.</p></td>
</tr>
<tr class="even">
<td><p>[<strong>BreakMirrorVirtualDisk</strong>](https://msdn.microsoft.com/library/Hh448676(v=VS.85).aspx)</p></td>
<td><p>Breaks a previously initiated mirror operation and sets the mirror to be the active virtual disk.</p></td>
</tr>
<tr class="odd">
<td><p>[<strong>CompactVirtualDisk</strong>](https://msdn.microsoft.com/library/Dd323655(v=VS.85).aspx)</p></td>
<td><p>Reduces the size of a virtual hard disk (VHD) backing store file.</p></td>
</tr>
<tr class="even">
<td><p>[<strong>CreateVirtualDisk</strong>](https://msdn.microsoft.com/library/Dd323659(v=VS.85).aspx)</p></td>
<td><p>Creates a virtual hard disk (VHD) image file, either using default parameters or using an existing virtual disk or physical disk.</p></td>
</tr>
<tr class="odd">
<td><p>[<strong>DeleteSnapshotVhdSet</strong>](https://msdn.microsoft.com/library/Mt414212(v=VS.85).aspx)</p></td>
<td><p>Deletes a snapshot from a VHD Set file.</p></td>
</tr>
<tr class="even">
<td><p>[<strong>DeleteVirtualDiskMetadata</strong>](https://msdn.microsoft.com/en-us/library/Hh832155(v=VS.85).aspx)</p></td>
<td><p>Deletes metadata from a virtual disk.</p></td>
</tr>
<tr class="odd">
<td><p>[<strong>DetachVirtualDisk</strong>](https://msdn.microsoft.com/library/Dd323696(v=VS.85).aspx)</p></td>
<td><p>Detaches a virtual hard disk (VHD) or CD or DVD image file (ISO) by locating an appropriate virtual disk provider to accomplish the operation.</p></td>
</tr>
<tr class="even">
<td><p>[<strong>EnumerateVirtualDiskMetadata</strong>](https://msdn.microsoft.com/en-us/library/Hh832156(v=VS.85).aspx)</p></td>
<td><p>Enumerates the metadata associated with a virtual disk.</p></td>
</tr>
<tr class="odd">
<td><p>[<strong>ExpandVirtualDisk</strong>](https://msdn.microsoft.com/library/Dd323664(v=VS.85).aspx)</p></td>
<td><p>Increases the size of a fixed or dynamically expandable virtual hard disk (VHD).</p></td>
</tr>
<tr class="even">
<td><p>[<strong>GetStorageDependencyInformation</strong>](https://msdn.microsoft.com/library/Dd323669(v=VS.85).aspx)</p></td>
<td><p>Returns the relationships between virtual hard disks (VHDs) or CD or DVD image file (ISO) or the volumes contained within those disks and their parent disk or volume.</p></td>
</tr>
<tr class="odd">
<td><p>[<strong>GetVirtualDiskInformation</strong>](https://msdn.microsoft.com/library/Dd323670(v=VS.85).aspx)</p></td>
<td><p>Retrieves information about a VHD.</p></td>
</tr>
<tr class="even">
<td><p>[<strong>GetVirtualDiskMetadata</strong>](https://msdn.microsoft.com/en-us/library/Hh832157(v=VS.85).aspx)</p></td>
<td><p>Retrieves the specified metadata from the virtual disk.</p></td>
</tr>
<tr class="odd">
<td><p>[<strong>GetVirtualDiskOperationProgress</strong>](https://msdn.microsoft.com/library/Dd323671(v=VS.85).aspx)</p></td>
<td><p>Checks the progress of an asynchronous virtual hard disk (VHD) operation.</p></td>
</tr>
<tr class="even">
<td><p>[<strong>GetVirtualDiskPhysicalPath</strong>](https://msdn.microsoft.com/library/Dd323672(v=VS.85).aspx)</p></td>
<td><p>Retrieves the path to the physical device object that contains a virtual hard disk (VHD) or CD or DVD image file (ISO).</p></td>
</tr>
<tr class="odd">
<td><p>[<strong>MergeVirtualDisk</strong>](https://msdn.microsoft.com/library/Dd323676(v=VS.85).aspx)</p></td>
<td><p>Merges a child virtual hard disk (VHD) in a differencing chain with one or more parent virtual disks in the chain.</p></td>
</tr>
<tr class="even">
<td><p>[<strong>MirrorVirtualDisk</strong>](https://msdn.microsoft.com/library/Hh448678(v=VS.85).aspx)</p></td>
<td><p>Initiates a mirror operation for a virtual disk.</p></td>
</tr>
<tr class="odd">
<td><p>[<strong>ModifyVhdSet</strong>](https://msdn.microsoft.com/library/Mt414216(v=VS.85).aspx)</p></td>
<td><p>Modifies the internal contents of a virtual disk file. Can be used to set the active leaf, or to fix up snapshot entries.</p></td>
</tr>
<tr class="even">
<td><p>[<strong>OpenVirtualDisk</strong>](https://msdn.microsoft.com/library/Dd323680(v=VS.85).aspx)</p></td>
<td><p>Opens a virtual hard disk (VHD) or CD or DVD image file (ISO) for use.</p></td>
</tr>
<tr class="odd">
<td><p>[<strong>QueryChangesVirtualDisk</strong>](https://msdn.microsoft.com/library/Mt162230(v=VS.85).aspx)</p></td>
<td><p>Retrieves information about changes to the specified areas of a virtual hard disk (VHD) that are tracked by resilient change tracking (RCT).</p></td>
</tr>
<tr class="even">
<td><p>[<strong>RawSCSIVirtualDisk</strong>](https://msdn.microsoft.com/library/Mt764771(v=VS.85).aspx)</p></td>
<td><p>Issues an embedded SCSI request directly to a virtual hard disk.</p></td>
</tr>
<tr class="odd">
<td><p>[<strong>ResizeVirtualDisk</strong>](https://msdn.microsoft.com/en-us/library/Hh832158(v=VS.85).aspx)</p></td>
<td><p>Resizes a virtual disk.</p></td>
</tr>
<tr class="even">
<td><p>[<strong>SetVirtualDiskInformation</strong>](https://msdn.microsoft.com/library/Dd323685(v=VS.85).aspx)</p></td>
<td><p>Sets information about a virtual hard disk (VHD).</p></td>
</tr>
<tr class="odd">
<td><p>[<strong>SetVirtualDiskMetadata</strong>](https://msdn.microsoft.com/en-us/library/Hh832162(v=VS.85).aspx)</p></td>
<td><p>Sets a metadata item for a virtual disk.</p></td>
</tr>
<tr class="even">
<td><p>[<strong>TakeSnapshotVhdSet</strong>](https://msdn.microsoft.com/library/Mt414220(v=VS.85).aspx)</p></td>
<td><p>Creates a snapshot of the current virtual disk for VHD Set files.</p></td>
</tr>
</tbody>
</table>

 

 

 


