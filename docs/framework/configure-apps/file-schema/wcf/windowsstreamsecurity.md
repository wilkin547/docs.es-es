---
title: "&lt;windowsStreamSecurity&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 926bea29-90c7-4a26-9cf0-fb4aa44f6f70
caps.latest.revision: 10
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 10
---
# &lt;windowsStreamSecurity&gt;
Especifique configuración de seguridad de secuencia de Windows del enlace personalizado.  
  
## Sintaxis  
  
```  
  
<windowsStreamSecurity protectionLevel="None/Sign/EncryptAndSign"/>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|protectionLevel|Define la seguridad del nivel de mensaje.  Al firmar los mensajes se reduce el riesgo de que un tercero manipule el mensaje mientras se transfiere.  El cifrado proporciona privacidad de nivel de datos durante el transporte.  Los valores válidos son los siguientes:<br /><br /> -   None: sin protección.<br />-   Sign: se firman los mensajes.<br />-   EncryptAndSign: los mensajes se firman y cifran.<br /><br /> El valor predeterminado es EncryptAndSign.<br /><br /> Este atributo es del tipo <xref:System.Net.Security.ProtectionLevel>.|  
  
### Elementos secundarios  
 Ninguna  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<enlace\>](../../../../../docs/framework/misc/binding.md)|Define todas las funcionalidades de enlace del enlace personalizado.|  
  
## Comentarios  
 Transportes que utilizan un protocolo orientado a secuencias como TCP y canalizaciones con nombre que admiten las actualizaciones de transporte basadas en secuencias.  Concretamente, WCF proporciona actualizaciones de seguridad.  La configuración de esta seguridad de transporte es encapsulada por este elemento de configuración así como por [\<sslStreamSecurity\>](../../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md), que se puede configurar y se puede agregar a un enlace personalizado.  
  
## Vea también  
 <xref:System.ServiceModel.Channels.CustomBinding>   
 <xref:System.ServiceModel.Configuration.WindowsStreamSecurityElement>   
 <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>   
 [Enlaces](../../../../../docs/framework/wcf/bindings.md)   
 [Extensión de enlaces](../../../../../docs/framework/wcf/extending/extending-bindings.md)   
 [Enlaces personalizados](../../../../../docs/framework/wcf/extending/custom-bindings.md)   
 [\<customBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)