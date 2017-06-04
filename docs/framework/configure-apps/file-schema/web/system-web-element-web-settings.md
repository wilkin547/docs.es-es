---
title: "&lt;system.web&gt; (Elemento) (Configuraci&#243;n web) | Microsoft Docs"
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
  - "<system.Web> (elemento)"
  - "sistema de configuración de ASP.NET"
  - "archivos de configuración [ASP.NET]"
  - "system.Web (elemento)"
  - "Web.config (archivo de configuración) [ASP.NET]"
ms.assetid: 24c4cf4f-ad32-42b2-b040-8e4549e2855e
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# &lt;system.web&gt; (Elemento) (Configuraci&#243;n web)
Contiene información sobre cómo el nivel de hospedaje de ASP.NET administra el comportamiento de todo el proceso.  
  
## Sintaxis  
  
```  
<system.web>  
</system.web>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
 Ninguno.  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<applicationPool\>](../../../../../docs/framework/configure-apps/file-schema/web/applicationpool-element-web-settings.md)|Especifica la configuración para los grupos de aplicaciones de IIS en un archivo aspnet.config.|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<configuration\>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|Especifica el elemento raíz de cada archivo de configuración usado por Common Language Runtime y las aplicaciones de [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)].|  
  
## Comentarios  
 El elemento `system.web` y su elemento secundario `applicationPool` se agregaron a [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] a partir de [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)].  Cuando ejecuta [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] o versiones posteriores en modo integrado, esta combinación de elementos permite configurar cómo administra ASP.NET los subprocesos y cómo pone en cola las solicitudes cuando ASP.NET está hospedado en un grupo de aplicaciones de IIS.  Si ejecuta [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] o versiones posteriores en modo ISAPI o Clásico, se pasa por alto esta configuración.  
  
## Ejemplo  
 En el ejemplo siguiente se muestra cómo configurar el comportamiento de todo el proceso de ASP.NET en el archivo aspnet.config cuando ASP.NET está hospedado en un grupo de aplicaciones de IIS.  En el ejemplo se supone que IIS se está ejecutando en modo integrado y que la aplicación está usando [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)] o una versión posterior.  Este comportamiento no se produce en versiones de [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] anteriores a [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)].  Los valores de este ejemplo son los valores predeterminados.  
  
```  
<configuration>  
  <system.web>  
    <applicationPool   
        maxConcurrentRequestsPerCPU="5000"   
        maxConcurrentThreadsPerCPU="0"   
        requestQueueLimit="5000" />  
  </system.web>  
</configuration>  
```  
  
## Información de elemento  
  
|||  
|-|-|  
|Espacio de nombres||  
|Nombre de esquema||  
|Archivo de validación||  
|Puede estar vacío||  
  
## Vea también  
 [\<applicationPool\> \(Elemento\) \(Configuración web\)](../../../../../docs/framework/configure-apps/file-schema/web/applicationpool-element-web-settings.md)