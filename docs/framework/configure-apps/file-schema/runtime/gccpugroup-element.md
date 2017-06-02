---
title: "Elemento &lt;GCCpuGroup&gt; | Microsoft Docs"
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
  - "<GCCpuGroup> (elemento)"
  - "GCCpuGroup (elemento)"
ms.assetid: c1fc7d6c-7220-475c-a312-5b8b201f66e0
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# Elemento &lt;GCCpuGroup&gt;
Especifica si la recolección de elementos no utilizados admite varios grupos de CPU.  
  
## Sintaxis  
  
```  
<GCCpuGroup    
   enabled="true|false"/>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|`enabled`|Atributo necesario.<br /><br /> Especifica si la recolección de elementos no utilizados admite varios grupos de CPU.|  
  
## Atributo enabled  
  
|Valor|Descripción|  
|-----------|-----------------|  
|`false`|La recolección de elementos no utilizados no admite varios grupos de CPU.  Éste es el valor predeterminado.|  
|`true`|La recolección de elementos no utilizados admite varios grupos de CPU, si está habilitada la recolección de elementos no utilizados de servidor.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.|  
  
## Comentarios  
 Cuando un equipo tiene varios grupos de CPU y la recolección de elementos no utilizados está habilitada \(vea el elemento [\<gcServer\>](../../../../../docs/framework/configure-apps/file-schema/runtime/gcserver-element.md)\), habilitar este elemento extiende la recolección de elementos no utilizados por todos los grupos de CPU y tiene en cuenta todos los núcleos al crear y equilibra montones.  
  
> [!NOTE]
>  Este elemento solo se aplica a los subprocesos de recolección de elementos no utilizados.  Para que el runtime pueda distribuir subprocesos de usuario en todos los grupos de CPU, también se debe habilitar el elemento [\<Thread\_UseAllCpuGroups\>](../../../../../docs/framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md).  
  
## Ejemplo  
 En el ejemplo siguiente se muestra cómo habilitar la recolección de elementos no utilizados para varios grupos de CPU.  
  
```  
<configuration>  
   <runtime>  
      <GCCpuGroup enabled="true"/>  
      <gcServer enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## Vea también  
 [Esquema de la configuración de Common Language Runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [Esquema de los archivos de configuración](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [How to: Disable Concurrent Garbage Collection](http://msdn.microsoft.com/es-es/ba2c6c67-5778-497c-9fac-5f793b5500c7)   
 [Recolección de elementos no utilizados de estación de trabajo y de servidor](../../../../../docs/standard/garbage-collection/fundamentals.md#workstation_and_server_garbage_collection)