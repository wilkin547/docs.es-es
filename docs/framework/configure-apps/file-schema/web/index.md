---
title: "Esquema de configuraci&#243;n web | Microsoft Docs"
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
  - "sistema de configuración de ASP.NET, configuración web (esquema)"
  - "archivos de configuración [ASP.NET]"
  - "esquema de configuración [.NET Framework], configuración web"
  - "esquema de configuración web"
  - "configuración web, esquema [ASP.NET]"
  - "Web.config (archivo de configuración) [ASP.NET]"
ms.assetid: ae1ac356-267d-4753-8d7a-7a04eb45a9be
caps.latest.revision: 6
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 6
---
# Esquema de configuraci&#243;n web
La configuración web especifica las opciones de CPU y de ASP.NET de nivel de ejecución que se aplican al comportamiento de todo el proceso administrado por el nivel de hospedaje de ASP.NET.  Esta configuración difiere de la configuración del tipo de dominio de aplicación que se especifica en el archivo Web.config de una aplicación ASP.NET.  
  
 La configuración web está contenida en archivos Aspnet.config, que se encuentran en las carpetas de instalación para las versiones de .NET Framework.  Por ejemplo, el archivo Aspnet.config para [!INCLUDE[dnprdnext](../../../../../includes/dnprdnext-md.md)] está en la carpeta siguiente:  
  
 `C:\Windows\Microsoft.NET\Framework\v2.0.50727\`  
  
 La configuración web no se usa en ningún otro archivo de configuración como machine.config, el archivo Web.config raíz o archivos Web.config de nivel de aplicación.  
  
 [Elemento \<configuration\>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [\<system.web\> \(Elemento\) \(Configuración web\)](../../../../../docs/framework/configure-apps/file-schema/web/system-web-element-web-settings.md)  
  
 [\<applicationPool\> \(Elemento\) \(Configuración web\)](../../../../../docs/framework/configure-apps/file-schema/web/applicationpool-element-web-settings.md)  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<system.web\>](../../../../../docs/framework/configure-apps/file-schema/web/system-web-element-web-settings.md)|Contiene información usada por el nivel de hospedaje de ASP.NET.|  
|[\<applicationPool\>](../../../../../docs/framework/configure-apps/file-schema/web/applicationpool-element-web-settings.md)|Especifica la configuración de CPU y de ASP.NET de nivel de ejecución que se aplica al comportamiento de todo el proceso administrado por el nivel de hospedaje de ASP.NET.|  
  
## Vea también  
 [Esquema de los archivos de configuración](../../../../../docs/framework/configure-apps/file-schema/index.md)