---
title: "&lt;smtp&gt; (Elemento, Configuraci&#243;n de red) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#smtp"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<smtp> (elemento)"
  - "smtp (elemento)"
ms.assetid: 220b0329-e384-4e0c-86b4-0945ad17efd9
caps.latest.revision: 13
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 13
---
# &lt;smtp&gt; (Elemento, Configuraci&#243;n de red)
Configura el formato de entrega, el método de entrega y la dirección de remitente para el envío de correos electrónicos.  
  
## Sintaxis  
  
```  
  
      <smtp  
  deliveryFormat="format"   
  deliveryMethod="method"   
  from="from address"   
  <specifiedPickupDirectory> … </ specifiedPickupDirectory >  
  <network> … </network>  
/smtp>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|`deliveryFormat`|Especifica el formato de entrega para los mensajes de correo electrónico salientes.  Los valores aceptables son SevenBit e International.|  
|`deliveryMethod`|Especifica el método de entrega para los mensajes de correo electrónico.  Los valores aceptables son network, pickupDirectoryFromIis y specifiedPickupDirectory.|  
|`from`|Especifica la dirección de remitente para los mensajes de correo electrónico salientes.|  
  
### Elementos secundarios  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|`specifiedPickupDirectory`|Configura el directorio local de un servidor SMTP \(Protocolo simple de transferencia de correo\).|  
|`network`|Configura las opciones de red de un servidor SMTP externo.|  
  
### Elementos primarios  
  
|**Elemento**|**Descripción**|  
|------------------|---------------------|  
|[\<mailSettings\> \(Elemento, Configuración de red\)](../../../../../docs/framework/configure-apps/file-schema/network/mailsettings-element-network-settings.md)|Configura opciones de envío de correo.|  
  
## Ejemplo  
 En el ejemplo de código siguiente se especifican los parámetros SMTP adecuados para enviar correo electrónico mediante las credenciales de red predeterminadas.  
  
```  
<configuration>  
  <system.net>  
    <mailSettings>  
      <smtp deliveryMethod="network" deliveryFormat="SevenBit"  from="ben@contoso.com">  
        <network  
          host="localhost"  
          port="25"  
          defaultCredentials="true"  
        />  
      </smtp>  
    </mailSettings>  
  </system.net>  
</configuration>  
```  
  
## Vea también  
 <xref:System.Net.Configuration.SmtpSection?displayProperty=fullName>   
 <xref:System.Net.Mail.SmtpClient?displayProperty=fullName>   
 <xref:System.Net.Mail.SmtpDeliveryFormat>   
 <xref:System.Net.Mail.SmtpDeliveryMethod>   
 [Esquema de la configuración de red](../../../../../docs/framework/configure-apps/file-schema/network/index.md)