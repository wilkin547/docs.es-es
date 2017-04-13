---
title: "&lt;specifiedPickupDirectory&gt; (Elemento, Configuraci&#243;n de red) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#specifiedPickupDirectory"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp/specifiedPickupDirectory"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<specifiedPickupDirectory> (elemento)"
  - "specifiedPickupDirectory (elemento)"
ms.assetid: 0121f49d-bff2-4bc6-af06-f1628dcd61f1
caps.latest.revision: 8
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 8
---
# &lt;specifiedPickupDirectory&gt; (Elemento, Configuraci&#243;n de red)
Configura el directorio local de un servidor SMTP \(Protocolo simple de transferencia de correo\).  
  
## Sintaxis  
  
```  
  
      <specifiedPickupDirectory  
  pickupDirectoryLocation="directory"   
/>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|`pickupDirectoryLocation`|Directorio en el que las aplicaciones guardan el correo electrónico para su posterior procesamiento por parte del servidor SMTP.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<smtp\> \(Elemento, Configuración de red\)](../../../../../docs/framework/configure-apps/file-schema/network/smtp-element-network-settings.md)|Configura opciones para el envío de correo del Protocolo simple de transferencia de correo \(SMTP\).|  
  
## Comentarios  
 El atributo de `specifiedPickupDirectory` establece el directorio donde las aplicaciones guardan los mensajes de correo que se procesen por el servidor SMTP.  
  
## Ejemplo  
 En el siguiente ejemplo de código se especifica c:\\maildrop como directorio de recogida de correo.  
  
```  
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
  
## Vea también  
 <xref:System.Net.Mail.SmtpClient?displayProperty=fullName>   
 <xref:System.Net.Configuration.SmtpSection?displayProperty=fullName>   
 <xref:System.Net.Configuration.SmtpSpecifiedPickupDirectoryElement?displayProperty=fullName>   
 [Esquema de la configuración de red](../../../../../docs/framework/configure-apps/file-schema/network/index.md)