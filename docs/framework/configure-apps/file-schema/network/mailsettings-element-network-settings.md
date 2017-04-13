---
title: "&lt;mailSettings&gt; (Elemento, Configuraci&#243;n de red) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#mailSettings"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<mailSettings> (elemento)"
  - "mailSettings (elemento)"
ms.assetid: 54f0f153-17e5-4f49-afdc-deadb940c9c1
caps.latest.revision: 20
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 20
---
# &lt;mailSettings&gt; (Elemento, Configuraci&#243;n de red)
Configura opciones de envío de correo.  
  
## Sintaxis  
  
```  
  
      <mailSettings  
  <smtp> … </smtp>  
/mailsettings>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
 Ninguno.  
  
### Elementos secundarios  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|[\<smtp\> \(Elemento, Configuración de red\)](../../../../../docs/framework/configure-apps/file-schema/network/smtp-element-network-settings.md)|Configura las opciones de protocolo simple de transferencia de correo.|  
  
### Elementos primarios  
  
|**Elemento**|**Descripción**|  
|------------------|---------------------|  
|[\<system.Net\> \(elemento\) \(configuración de red\)](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|Contiene los valores de configuración que especifican cómo se conecta a la red .NET Framework.|  
  
## Ejemplo  
 En el ejemplo de código siguiente se especifican los parámetros SMTP adecuados para enviar correo electrónico mediante las credenciales de red predeterminadas.  
  
```  
<configuration>  
  <system.net>  
    <mailSettings>  
      <smtp deliveryMethod="network">  
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
 <xref:System.Net.Mail.SmtpClient>   
 [Esquema de la configuración de red](../../../../../docs/framework/configure-apps/file-schema/network/index.md)