---
title: "&lt;appDomainResourceMonitoring&gt; (Elemento) | Microsoft Docs"
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
  - "<appDomainResourceMonitoring> (elemento)"
  - "appDomainResourceMonitoring (elemento)"
ms.assetid: 02119ab6-1e91-448e-97ad-e7b2e5c4bbbd
caps.latest.revision: 14
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 14
---
# &lt;appDomainResourceMonitoring&gt; (Elemento)
Indica al runtime que recopile estadísticas de todos los dominios de aplicación del proceso mientras dure el proceso.  
  
## Sintaxis  
  
```  
<appDomainResourceMonitoring    
   enabled="true|false"/>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|`enabled`|Atributo necesario.<br /><br /> Especifica si el runtime recopila estadísticas para la supervisión de recursos del dominio de aplicación.|  
  
## Atributo enabled  
  
|Valor|Descripción|  
|-----------|-----------------|  
|`true`|Se recopilan estadísticas para la supervisión de recursos del dominio de aplicación.|  
|`false`|No se recopilan estadísticas para la supervisión de recursos del dominio de aplicación.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.|  
  
## Comentarios  
 La supervisión de recursos del dominio de aplicación está disponible a través de la clase de dominio de aplicación administrada, la interfaz [ICLRAppDomainResourceMonitor](../../../../../ocs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md) de hospedaje y Seguimiento de eventos para Windows \(ETW\).  Cuando la supervisión está habilitada, se recopilan estadísticas para todos los dominios de aplicación mientras dure el proceso.  
  
 Para habilitar la supervisión desde código administrado, use la propiedad <xref:System.AppDomain.MonitoringIsEnabled%2A>.  
  
 Este elemento de configuración solo está disponible en [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] y en versiones posteriores.  
  
## Ejemplo  
 En el ejemplo siguiente se muestra cómo habilitar la supervisión de recursos de dominio de aplicación.  
  
```  
<configuration>  
   <runtime>  
      <appDomainResourceMonitoring enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## Vea también  
 <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=fullName>   
 [Esquema de la configuración de Common Language Runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [Esquema de los archivos de configuración](../../../../../docs/framework/configure-apps/file-schema/index.md)