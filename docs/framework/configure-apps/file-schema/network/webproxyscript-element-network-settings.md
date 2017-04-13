---
title: "Elemento &lt;webProxyScript&gt; (configuraci&#243;n de red) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#webProxyScript"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/webProxyScript"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<webProxyScript> (elemento)"
  - "webProxyScript (elemento)"
ms.assetid: a13c26db-6218-4af3-9696-38f24b23bfac
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# Elemento &lt;webProxyScript&gt; (configuraci&#243;n de red)
Configura las características del script que se utilizan para detectar los servidores proxy Web.  
  
## Sintaxis  
  
```  
  
      <webProxyScript  
  downloadTimeout="hh:mm:ss"  
/>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|`downloadTimeout`|Especifica la tiempo máximo para descargar el script en horas, minutos y segundos.  El valor predeterminado es un minuto.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[settings](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|Configura las opciones de red básicas para el espacio de nombres <xref:System.Net>.|  
  
## Comentarios  
  
## Archivos de configuración  
 Este elemento puede utilizarse en el archivo de configuración de la aplicación o en el archivo de configuración del equipo \(Machine.config\).  
  
## Vea también  
 [Esquema de la configuración de red](../../../../../docs/framework/configure-apps/file-schema/network/index.md)