---
title: "Esquema de la configuraci&#243;n de red | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "valores de configuración [.NET Framework], redes"
  - "conexiones [.NET Framework], elementos de la configuración de red"
  - "elementos [.NET Framework], elementos de la configuración de red"
  - "Internet, elementos de la configuración de red"
  - "elementos de la configuración de red"
  - "recursos de red, elementos de la configuración de red"
  - "configuración de red"
  - "recibir datos, elementos de la configuración de red"
  - "enviar datos, elementos de la configuración de red"
ms.assetid: f1de5a0f-76c5-4833-819f-5222b8146340
caps.latest.revision: 14
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 14
---
# Esquema de la configuraci&#243;n de red
La configuración de red especifican cómo se conecta .NET Framework internet.  La tabla siguiente describe la función de cada elemento de configuración secundario bajo [\<system.Net\> \(elemento\) \(configuración de red\)](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md).  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<authenticationModules\> \(Elemento, Configuración de red\)](../../../../../docs/framework/configure-apps/file-schema/network/authenticationmodules-element-network-settings.md)|Especifica los módulos utilizados para autenticar las solicitudes de Internet.|  
|[\<connectionManagement\> \(Elemento, Configuración de red\)](../../../../../docs/framework/configure-apps/file-schema/network/connectionmanagement-element-network-settings.md)|Especifica el número máximo de conexiones a hosts de Internet.|  
|[\<defaultProxy\> \(Elemento, Configuración de red\)](../../../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md)|Especifica el servidor proxy utilizado para las solicitudes HTTP a Internet.|  
|[\<mailSettings\> \(Elemento, Configuración de red\)](../../../../../docs/framework/configure-apps/file-schema/network/mailsettings-element-network-settings.md)|Contiene los valores de configuración para las opciones de envío de correo.|  
|[\<requestCaching\> \(Elemento, Configuración de red\)](../../../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)|Especifica los módulos utilizados para solicitar información a hosts de Internet.|  
|[\<requestCaching\> \(Elemento, Configuración de red\)](../../../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)|Configura las opciones de red básicas para el espacio de nombres <xref:System.Net?displayProperty=fullName>.|  
|[\<webRequestModules\> \(Elemento, Configuración de red\)](../../../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md)|Especifica los módulos utilizados para solicitar información a hosts de Internet.|  
  
 Los valores de URI especifican cómo .NET Framework administra las direcciones web expresadas mediante identificadores uniformes de recursos \(URIs\).  La tabla siguiente describe la función de cada elemento de configuración secundario bajo [\<Uri\> \(Elemento, configuración de Uri\)](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md).  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<idn\> \(Elemento, Configuración de Uri\)](../../../../../docs/framework/configure-apps/file-schema/network/idn-element-uri-settings.md)|Especifica si el análisis de nombres de dominio internacionalizados \(IDN\) se aplica a los nombres de dominio.|  
|[\<iriParsing\> \(Elemento, Configuración de Uri\)](../../../../../docs/framework/configure-apps/file-schema/network/iriparsing-element-uri-settings.md)|Especifica si el análisis de identificadores de recursos internacionales \(IRI\) se aplica a <xref:System.Uri> y si deben aplicarse las reglas de análisis IRI.|  
|[\<schemeSettings\> \(Elemento, Configuración de URI\)](../../../../../docs/framework/configure-apps/file-schema/network/schemesettings-element-uri-settings.md)|Especifica cómo se analizará <xref:System.Uri> para esquemas concretos.|  
  
## Vea también  
 [Configuración de aplicaciones de Internet](../../../../../docs/framework/network-programming/configuring-internet-applications.md)   
 [Esquema de los archivos de configuración](../../../../../docs/framework/configure-apps/file-schema/index.md)