﻿---
title: New-CsSipProxyUseDefault
TOCTitle: New-CsSipProxyUseDefault
ms:assetid: 1e8bedca-8bd5-4559-b530-0f18ae23d6d3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398274(v=OCS.15)
ms:contentKeyID: 48183588
ms.date: 07/23/2014
mtps_version: v=OCS.15
---

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# New-CsSipProxyUseDefault

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Topic Last Modified:** 2013-02-21_

Used to assign the default realm (SIP Communications Service) to a collection of proxy configuration settings. Realms (also known as protection domains) are used to authenticate user credentials during logon. This cmdlet was introduced in Lync Server 2010.

<div>

## Syntax

    New-CsSipProxyUseDefault

</div>

<div>

## Examples

<div>

## EXAMPLE 1

The command shown in Example 1 assigns the default realm (SIP Communications Service) to a variable named $x.

    $x = New-CsSipProxyUseDefault

</div>

</div>

<div>

## Detailed Description

Proxy servers provide a way for users outside your internal network to access resources on your internal network. Each proxy server must be associated with a realm; realms (also known as protection domains) indicate where a user’s logon credentials should be processed. By default, Lync Server uses SIP Communications Service as its default realm; however, it is possible to change the realm employed by a proxy server. If you change the realm and then want to revert back to using the default realm, you can do so by creating a SipProxy.UseDefault object, and then assigning that object to the Realm property of the appropriate proxy server (or servers).

Who can run this cmdlet: By default, members of the following groups are authorized to run the **New-CsSipProxyUseDefault** cmdlet locally: RTCUniversalServerAdmins. To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$\_.Cmdlets –match "New-CsSipProxyUseDefault"}

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
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p>This cmdlet provides only common Windows PowerShell parameters.</p></td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


</div>

<div>

## Input Types

None. The **New-CsSipProxyUseDefault** cmdlet does not accept pipelined input.

</div>

<div>

## Return Types

The **New-CsSipProxyUseDefault** cmdlet creates new instances of the Microsoft.Rtc.Management.WritableConfig.Settings.SipProxy.UseDefault object.

</div>

<div>

## See Also


[New-CsSipProxyCustom](new-cssipproxycustom.md)  
[New-CsSipProxyRealm](new-cssipproxyrealm.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>
