---
title: "&lt;performanceCounters&gt; (Elemento) | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/performanceCounters"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#performanceCounters"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<perfomanceCounters> (elemento)"
  - "performanceCounters (elemento)"
ms.assetid: a71f605b-c7d9-4501-a5c3-abcbb964a43f
caps.latest.revision: 10
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 10
---
# &lt;performanceCounters&gt; (Elemento)
Especifica el tamaño de la memoria global compartida por los contadores de rendimiento.  
  
## Sintaxis  
  
```  
<performanceCounters filemappingsize="524288" />  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|filemappingsize|Atributo necesario.<br /><br /> Especifica el tamaño \(en bytes\) de la memoria global compartida por los contadores de rendimiento.  El valor predeterminado es 524288.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|`Configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`system.diagnostics`|Especifica el elemento raíz de la sección de configuración de ASP.NET.|  
  
## Comentarios  
 Los contadores de rendimiento utilizan un archivo de asignación de memoria, o memoria compartida, para publicar los datos de rendimiento.  El tamaño de la memoria compartida determina cuántas instancias se pueden utilizar al mismo tiempo.  Hay dos tipos de memoria compartida: memoria compartida global y memoria compartida independiente.  Todas las categorías de contador de rendimiento instaladas con las versiones 1.0 o 1.1 de .NET Framework utilizan la memoria compartida global.  Las categorías de contador de rendimiento instaladas con la versión 2.0 de .NET Framework usan la memoria compartida independiente, de manera que cada categoría de contador de rendimiento tiene su propia memoria.  
  
 El tamaño de memoria compartida global sólo se puede establecer con un archivo de configuración.  El tamaño predeterminado es 524.288 bytes, el tamaño máximo es de 33.554.432 bytes y el mínimo de 32.768 bytes.  Puesto que todos los procesos y categorías comparten la memoria compartida global, el primer creador especifica el tamaño.  Si define el tamaño en su archivo de configuración de aplicación, ese tamaño sólo se utiliza si su aplicación es la primera que provoca la ejecución de contadores de rendimiento.  Por consiguiente la ubicación correcta para especificar el valor de `filemappingsize` es el archivo Machine.config.  La memoria de la memoria compartida global no se puede liberar mediante contadores de rendimiento individuales, por lo que la memoria compartida global se acabará agotando si se crea un gran número de instancias de contadores de rendimiento con distintos nombres.  
  
 Para el tamaño de la memoria compartida independiente, el valor de DWORD FileMappingSize en el HKEY\_LOCAL\_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\*\<category name\>*\\Performance de la clave del Registro hace referencia primero, seguido del valor especificado para la memoria compartida global en el archivo de configuración.  Si el valor FileMappingSize no existe, el tamaño de la memoria compartida independiente se establece en una cuarta parte \(1\/4\) de la configuración global especificada en el archivo de configuración.  
  
## Vea también  
 <xref:System.Diagnostics.PerformanceCounter>   
 <xref:System.Diagnostics.PerformanceCounterCategory>   
 <xref:System.Diagnostics.PerformanceCounter.InstanceLifetime%2A>   
 <xref:System.Diagnostics.PerformanceCounterInstanceLifetime>