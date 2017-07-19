---
title: "&lt;Thread_UseAllCpuGroups&gt; (Elemento) | Microsoft Docs"
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
ms.assetid: d30fe7c5-8469-46e2-b804-e3eec7b24256
caps.latest.revision: 6
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 6
---
# &lt;Thread_UseAllCpuGroups&gt; (Elemento)
Especifica si el runtime distribuye los subprocesos administrados en todos los grupos de CPU.  
  
## Sintaxis  
  
```vb  
<Thread_UseAllCpuGroups    
   enabled="true|false"/>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|`enabled`|Atributo necesario.<br /><br /> Especifica si el runtime distribuye los subprocesos administrados en todos los grupos de CPU.|  
  
## Atributo enabled  
  
|Valor|Descripción|  
|-----------|-----------------|  
|`false`|El runtime no distribuye los subprocesos administrados a través de varios grupos de CPU.  Éste es el valor predeterminado.|  
|`true`|El runtime distribuye los subprocesos administrados a través de varios grupos de CPU, si el equipo tiene varios grupos de CPU y se habilita el elemento de [\<GCCpuGroup\>](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md).|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.|  
  
## Comentarios  
 Cuando un equipo tiene varios grupos de CPU, habilitar este elemento provoca el runtime para distribuir los subprocesos administrados en todos los grupos de CPU.  Para usar esta característica, debe habilitar también el elemento [\<GCCpuGroup\>](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md) , que extiende la recolección de elementos no utilizados todos los grupos de CPU y tiene en cuenta todos los núcleos al crear y equilibrar montones.  Habilitar el elemento de [\<GCCpuGroup\>](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md) requiere habilitar el elemento de [\<gcServer\>](../../../../../docs/framework/configure-apps/file-schema/runtime/gcserver-element.md).  Si estos elementos no están habilitados, habilitar el elemento de `<Thread_UseAllCpuGroups>` no tiene ningún efecto.  
  
## Ejemplo  
 En el ejemplo siguiente se muestra cómo habilitar la compatibilidad con varios grupos de CPU.  
  
```  
<configuration>  
   <runtime>  
      <Thread_UseAllCpuGroups enabled="true"/>  
      <GCCpuGroup enabled="true"/>  
      <gcServer enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## Vea también  
 [Esquema de la configuración de Common Language Runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [Esquema de los archivos de configuración](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [Elemento \<GCCpuGroup\>](../../../../../docs/framework/configure-apps/file-schema/runtime/gccpugroup-element.md)