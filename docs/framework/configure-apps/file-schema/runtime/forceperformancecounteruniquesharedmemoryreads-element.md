---
title: "&lt;forcePerformanceCounterUniqueSharedMemoryReads&gt; (Elemento) | Microsoft Docs"
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
  - "<forcePerformanceCounterUniqueSharedMemoryReads> (elemento)"
  - "forcePerformanceCounterUniqueSharedMemoryReads (elemento)"
ms.assetid: 91149858-4810-4f65-9b48-468488172c9b
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# &lt;forcePerformanceCounterUniqueSharedMemoryReads&gt; (Elemento)
Especifica si PerfCounter.dll usa el valor del Registro CategoryOptions en una aplicación de la versión 1.1 de .NET Framework para determinar si debe cargar los datos del contador de rendimiento de la memoria compartida específica de la categoría o de la memoria global.  
  
## Sintaxis  
  
```  
<forcePerformanceCounterUniqueSharedMemoryReads   
enabled="true|false"/>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|`enabled`|Atributo necesario.<br /><br /> Indica si PerfCounter.dll usa el valor del Registro CategoryOptions para determinar si debe cargar los datos del contador de rendimiento de la memoria compartida específica de la categoría o de la memoria global.|  
  
## Atributo enabled  
  
|Valor|Descripción|  
|-----------|-----------------|  
|`false`|PerfCounter.dll no utiliza el valor del Registro CategoryOptions, éste es el valor predeterminado.|  
|`true`|PerfCounter.dll utiliza el valor del Registro CategoryOptions.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.|  
  
## Comentarios  
 En las versiones de .NET Framework anteriores a [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], la versión de PerfCounter.dll cargada correspondía al runtime que se cargó en el proceso.  Si un equipo tiene .NET Framework versión 1.1. y [!INCLUDE[dnprdnlong](../../../../../includes/dnprdnlong-md.md)], una aplicación .NET Framework 1.1 cargaría la versión 1.1 de .NET Framework de PerfCounter.dll.  A partir de [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], se carga la última versión instalada de PerfCounter.dll.  Esto significa que una aplicación .NET Framework 1.1 cargará la versión [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] de PerfCounter.dll, si [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] está instalada en el equipo.  
  
 A partir de [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], cuando se utilizan contadores de rendimiento, PerfCounter.dll comprueba la entrada del Registro CategoryOptions de cada proveedor para determinar si debería leer de la memoria compartida específica de la categoría o la memoria compartida global.  PerfCounter.dll de .NET Framework 1.1 no lee esa entrada del Registro, debido a que no reconoce la memoria compartida específica de la categoría; siempre lee de la memoria compartida global.  
  
 Para la compatibilidad con versiones anteriores, [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] PerfCounter.dll no comprueba la entrada del Registro de CategoryOptions al ejecutarse en la aplicación .NET Framework 1.1.  Simplemente utiliza la memoria compartida global, solo como .NET Framework 1.1 PerfCounter.dll.  Sin embargo, puede indicarle a PerfCounter.dll [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] que compruebe el valor del Registro habilitando el elemento `<forcePerformanceCounterUniqueSharedMemoryReads>`.  
  
> [!NOTE]
>  Al habilitar el elemento `<forcePerformanceCounterUniqueSharedMemoryReads>` no se garantiza que se utilizará esa memoria compartida específica de la categoría.  El valor habilitado para `true` sólo provoca que PerfCounter.dll haga referencia al valor del Registro CategoryOptions.  La configuración predeterminada para CategoryOptions es el uso la memoria compartida específica de la categoría; sin embargo, puede cambiar CategoryOptions para indicar que se debería utilizar la memoria compartida global.  
  
 La clave del Registro que contiene el valor de CategoryOptions es categoryName\\Performance\<\>de HKEY\_LOCAL\_MACHINE\\System\\CurrentControlSet\\Services\\.  De manera predeterminada, CategoryOptions está establecido en 3, lo que indica a PerfCounter.dll que use la memoria compartida específica de la categoría.  Si CategoryOptions está establecido en 0, PerfCounter.dll utiliza la memoria compartida global.  Sólo se reutilizarán los datos de instancia si el nombre de la instancia que se está creando es idéntico a la instancia que se está reutilizando.  Todas las versiones serán capaces de escribir en la categoría.  Si CategoryOptions está establecido en 1, se utiliza la memoria compartida global, pero se pueden reutilizar los datos de instancia si el nombre de categoría tiene la misma longitud que la categoría que se reutiliza.  
  
 La configuración 0 y 1 puede llevar a pérdidas de memoria y el rellenado de la memoria del contador de rendimiento.  
  
## Ejemplo  
 En el ejemplo siguiente se muestra cómo especificar que PerfCounter.dll debería hacer referencia a la entrada del Registro CategoryOptions para determinar si debería utilizar la memoria compartida específica de la categoría.  
  
```  
<configuration>  
  <runtime>  
    <forcePerformanceCounterUniqueSharedMemoryReads enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## Vea también  
 [Esquema de la configuración de Common Language Runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [Esquema de los archivos de configuración](../../../../../docs/framework/configure-apps/file-schema/index.md)