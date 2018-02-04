---
title: '&lt;specifiedPickupDirectory&gt; Element (Network Settings)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#specifiedPickupDirectory
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp/specifiedPickupDirectory
helpviewer_keywords:
- specifiedPickupDirectory element
- <specifiedPickupDirectory> element
ms.assetid: 0121f49d-bff2-4bc6-af06-f1628dcd61f1
caps.latest.revision: 
author: mcleblanc
ms.author: markl
manager: markl
ms.workload:
- dotnet
ms.openlocfilehash: e68ce8cac4048ee2df89d0241cc50242e20391a2
ms.sourcegitcommit: cf22b29db780e532e1090c6e755aa52d28273fa6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/01/2018
---
# <a name="ltspecifiedpickupdirectorygt-element-network-settings"></a>&lt;specifiedPickupDirectory&gt; Element (Network Settings)
Configura el directorio local de un servidor SMTP (Protocolo simple de transferencia de correo).  
  
 \<configuration>  
\<system.net>  
\<mailSettings >  
\<smtp>  
\<specifiedPickupDirectory>  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<specifiedPickupDirectory  
  pickupDirectoryLocation="directory"   
/>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`pickupDirectoryLocation`|El directorio donde las aplicaciones guardan correo electrónico para su posterior procesamiento por el servidor SMTP.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<SMTP > elemento (configuración de red)](../../../../../docs/framework/configure-apps/file-schema/network/smtp-element-network-settings.md)|Configura opciones de envío de correo de Protocolo Simple de transferencia de correo (SMTP).|  
  
## <a name="remarks"></a>Comentarios  
 El `specifiedPickupDirectory` atributo establece el directorio donde las aplicaciones guardan los mensajes de correo electrónico para ser procesados por el servidor SMTP.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se especifica c:\maildrop como el directorio de recogida de correo electrónico.  
  
```xml  
<configuration>  
  <system.net>  
    <mailSettings>  
      <smtp deliveryMethod="specifiedPickupDirectory">  
        <specifiedPickupDirectory  
          pickupDirectoryLocation="c:\maildrop"  
        />  
      </smtp>  
    </mailSettings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>  
 <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>  
 <xref:System.Net.Configuration.SmtpSpecifiedPickupDirectoryElement?displayProperty=nameWithType>  
 [Esquema de la configuración de red](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
