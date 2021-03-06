﻿---
title: Remove-CsClsSecurityGroup
TOCTitle: Remove-CsClsSecurityGroup
ms:assetid: 67778239-9338-4717-abeb-8b87e8cb7a9a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204958(v=OCS.15)
ms:contentKeyID: 48184352
ms.date: 07/23/2014
mtps_version: v=OCS.15
---

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# Remove-CsClsSecurityGroup

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Topic Last Modified:** 2013-03-06_

Removes a centralized logging configuration security group. Centralized logging provides a way for administrators to simultaneously enable or disable event tracing on multiple computers. This cmdlet was introduced in Lync Server 2013.

<div>

## Syntax

    Remove-CsClsSecurityGroup -Identity <XdsIdentity> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]

</div>

<span id="Examples"></span>

<div>

## Examples

<div>

## Example 1

The command shown in Example 1 deletes the centralized logging security group with the Identity Global/HelpDesk.

    Remove-CsClsSecurityGroup -Identity "global/HelpDesk"

</div>

<div>

## Example 2

In Example 2, all the centralized logging security groups currently in use in the organization are deleted. To do this, the command first calls the **Get-CsClsSecurityGroup** cmdlet without any parameters; this returns a collection of all the centralized logging security groups. That collection is then piped to the **Remove-CsClsSecurityGroup** cmdlet, which deletes each group in the collection.

    Get-CsClsSecurityGroup | Remove-CsClsSecurityGroup

</div>

<div>

## Example 3

Example 3 shows how you can delete all the centralized logging security groups that have the access level RedmondSupport. To carry out this task, the command first uses the **Get-CsClsSecurityGroup** cmdlet to return a collection of all the available centralized logging security groups. That collection is then piped to the **Where-Object** cmdlet, which selects only those groups where the AccessLevel property is set to Tier3. In turn, those groups are piped to, and removed by, the **Remove-CsClsSecurityGroup** cmdlet.

    Get-CsClsSecurityGroup | Where-Object {$_.AccessLevel -eq "Tier3"} | Remove-CsClsSecurityGroup

</div>

</div>

<span id="DetailedDescription"></span>

<div>

## Detailed Description

The centralized logging service (which replaces the OCSLogger and OCSTracer tools used in Microsoft Lync Server 2010) provides a way for administrators to manage logging and tracing for all computers and pools running Microsoft Lync Server 2013. Centralized logging enables administrators to stop, start, and configure logging for one or more pools and computers by using a single command; for example, you can use one command to enable Address Book service logging on all your Address Book servers. This differs from the OCSLogger and OCSTracer tools, which had to be individually managed (including individually stopped and started) on each server. In addition, the centralized logging service also provides a way for administrators to search trace logs from the command, using the Windows PowerShell command-line interface and the [Search-CsClsLogging](search-csclslogging.md) cmdlet.

With Lync Online, security groups are used to determine which users have access to the personally-identifiable information that is written to the log files. Security groups are created by using the [New-CsClsSecurityGroup](new-csclssecuritygroup.md) cmdlet and then are added to a collection of centralized logging configuration settings. These groups can later be removed by using the **Remove-CsClsSecurityGroup** cmdlet.

To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "Remove-CsClsSecurityGroup"}

**Lync Server Control Panel:** The functions carried out by the **Remove-CsClsSecurityGroup** cmdlet are not available in the Lync Server Control Panel.

</div>

<div>

## Parameters


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Parameter</th>
<th>Required</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><em>Identity</em></p></td>
<td><p>Required</p></td>
<td><p>Microsoft.Rtc.Management.Xds.XdsIdentity</p></td>
<td><p>Unique identifier for the centralized logging security group to be removed. A security group identity consists of the scope where the group was created followed by the group name. For example, to remove a group named HelpDesk created at the global scope, use the following syntax:</p>
<p>-Identity &quot;global/HelpDesk&quot;</p></td>
</tr>
<tr class="even">
<td><p><em>Confirm</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Prompts you for confirmation before executing the command.</p></td>
</tr>
<tr class="odd">
<td><p><em>Force</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Suppresses the display of any non-fatal error message that might occur when running the command.</p></td>
</tr>
<tr class="even">
<td><p><em>WhatIf</em></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Describes what would happen if you executed the command without actually executing the command.</p></td>
</tr>
</tbody>
</table>


</div>

<span id="InputTypes"></span>

<div>

## Input Types

The **Remove-CsClsSecurityGroup** cmdlet accepts pipelined instances of the Microsoft.Rtc.Management.WritableConfig.Settings.CentralizedLogging.SecurityGroup\#Decorated object.

</div>

<span id="ReturnTypes"></span>

<div>

## Return Types

None. Instead, the **Remove-CsClsSecurityGroup** cmdlet deletes existing instances of the Microsoft.Rtc.Management.WritableConfig.Settings.CentralizedLogging.SecurityGroup\#Decorated object.

</div>

<div>

## See Also


[Get-CsClsSecurityGroup](get-csclssecuritygroup.md)  
[New-CsClsSecurityGroup](new-csclssecuritygroup.md)  
[Set-CsClsSecurityGroup](set-csclssecuritygroup.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

