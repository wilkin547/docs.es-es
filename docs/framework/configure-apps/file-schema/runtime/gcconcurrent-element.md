---
title: "Elemento &lt;gcConcurrent&gt; | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/gcConcurrent"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#gcConcurrent"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<gcConcurrent> (elemento)"
  - "etiquetas contenedoras, <gcConcurrent> (elemento)"
  - "gcConcurrent (elemento)"
ms.assetid: 503f55ba-26ed-45ac-a2ea-caf994da04cd
caps.latest.revision: 18
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 18
---
# Elemento &lt;gcConcurrent&gt;
Especifica si Common Language Runtime ejecuta la recolección de elementos no utilizados en un subproceso independiente.  
  
## Sintaxis  
  
```  
<gcConcurrent    
   enabled="true|false"/>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|`enabled`|Atributo necesario.<br /><br /> Especifica si CLR ejecuta la recolección de elementos no utilizados simultáneamente.|  
  
## Atributo enabled  
  
|Valor|Descripción|  
|-----------|-----------------|  
|`false`|No ejecuta la recolección de elementos no utilizados simultáneamente.|  
|`true`|Ejecuta la recolección de elementos no utilizados simultáneamente.  Este es el valor predeterminado.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.|  
  
## Comentarios  
 Antes de .NET Framework 4, la recolección de elementos no utilizados de estación de trabajo permitía la recolección de elementos no utilizados  simultánea, que se realizaba en segundo plano en un subproceso independiente.  En .NET Framework 4, la recolección de elementos no utilizados simultánea se reemplazó por GC, que también realiza la recolección de elementos no utilizados en segundo plano en un subproceso independiente.  A partir de .NET Framework 4.5, la recolección de elementos no utilizados de servidor se puede realizar en segundo plano.  El elemento `<gcConcurrent>` controla si CLR realiza la recolección de elementos no utilizados simultáneamente o en segundo plano, si está disponible o si realiza la recolección de elementos no utilizados en primer plano.  
  
> [!WARNING]
>  A partir de .NET Framework 4, la recolección de elementos no utilizados en segundo plano reemplaza a la recolección de elementos no utilizados simultánea.  Los términos *simultánea* y *en segundo plano* se usan indistintamente en la documentación de .NET Framework.  Para deshabilitar la recolección de elementos no utilizados en segundo plano, use el elemento `<gcConcurrent>` tal y como se describe en este artículo.  
  
 De forma predeterminada, CLR usa la recolección de elementos no utilizados simultánea, que está optimizada para la latencia.  Si la aplicación requiere mucha interacción por parte del usuario, deje habilitada la recolección de elementos no utilizados simultánea para minimizar el tiempo que la aplicación debe parar para realizar la recolección de elementos no utilizados.  Si establece el atributo `enabled` del elemento `<gcConcurrent>` en `false`, CLR usa la recolección de elementos no utilizados no simultánea, que está optimizada para el rendimiento.  El archivo de configuración siguiente deshabilita la recolección de elementos no utilizados en segundo plano.  
  
```xml  
  
<configuration>  
   <runtime>  
      <gcConcurrent enabled="false"/>  
   </runtime>  
</configuration>  
  
```  
  
 Si hay una opción de configuración `<gcConcurrentSetting>` en el archivo de configuración del equipo, define el valor predeterminado para todas las aplicaciones de .NET Framework.  El archivo de configuración del equipo reemplaza el archivo de configuración de la aplicación.  
  
 Para obtener más información sobre la recolección de elementos no utilizados simultánea y en segundo plano, consulte la sección "Recolección de elementos no utilizados simultánea" en el tema [Fundamentals of Garbage Collection](../../../../../docs/standard/garbage-collection/fundamentals.md).  
  
## Ejemplo  
 En el ejemplo siguiente se habilita la recolección de elementos no utilizados simultánea.  
  
```  
  
<configuration>  
   <runtime>  
      <gcConcurrent enabled="true"/>  
   </runtime>  
</configuration>  
  
```  
  
## Vea también  
 [Esquema de la configuración de Common Language Runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [Esquema de los archivos de configuración](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [Fundamentals of Garbage Collection](../../../../../docs/standard/garbage-collection/fundamentals.md)