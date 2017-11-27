---
title: '&lt;performanceCounters&gt; elemento'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/performanceCounters
- http://schemas.microsoft.com/.NetConfiguration/v2.0#performanceCounters
helpviewer_keywords:
- performanceCounters element
- <perfomanceCounters> element
ms.assetid: a71f605b-c7d9-4501-a5c3-abcbb964a43f
caps.latest.revision: "10"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: f7fdbb244663e5114880437a5a508270c80a9c79
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ltperformancecountersgt-element"></a>&lt;performanceCounters&gt; elemento
Especifica el tamaño de la memoria global que comparten los contadores de rendimiento.  
  
 \<configuration>  
\<System.Diagnostics >  
\<performanceCounters >  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<performanceCounters filemappingsize="524288" />  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|FileMappingSize|Atributo necesario.<br /><br /> Especifica el tamaño, en bytes, de la memoria global compartida por los contadores de rendimiento. El valor predeterminado es 524288.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`Configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`system.diagnostics`|Especifica el elemento raíz de la sección de configuración de ASP.NET.|  
  
## <a name="remarks"></a>Comentarios  
 Contadores de rendimiento de usar un archivo asignado a memoria, o memoria compartida, para publicar los datos de rendimiento.  El tamaño de la memoria compartida determina cuántas instancias se pueden utilizar a la vez.  Hay dos tipos de memoria compartida: memoria compartida global y memoria compartida independiente.  La memoria compartida global se usa por todas las categorías de contador de rendimiento instaladas con las versiones de .NET Framework 1.0 o 1.1.  Las categorías de contador de rendimiento instaladas con la versión 2.0 de .NET Framework utilizan memoria compartida independiente, y cada categoría de contador de rendimiento tiene su propia memoria.  
  
 El tamaño de la memoria compartida global puede establecerse solo con un archivo de configuración.  El tamaño predeterminado es 524.288 bytes, el tamaño máximo es de 33.554.432 bytes y el tamaño mínimo es de 32.768 bytes.  Puesto que todos los procesos y categorías comparten la memoria compartida global, el primer creador especifica el tamaño.  Si el tamaño se define en el archivo de configuración de aplicación, ese tamaño sólo se utiliza si la aplicación es la primera aplicación que hace que los contadores de rendimiento ejecutar.  Por lo tanto, la ubicación correcta para especificar el `filemappingsize` valor es el archivo Machine.config.  No se puede liberar memoria en la memoria compartida global mediante contadores de rendimiento individuales, por lo que finalmente se agota la memoria compartida global si se crea una gran cantidad de instancias de contador de rendimiento con nombres diferentes.  
  
 El tamaño de memoria compartida independiente, el valor de DWORD FileMappingSize en el registro de clave HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\\*\<nombre de categoría >*\Performance se hace referencia en primer lugar, seguido por el valor especificado para la memoria compartida global en el archivo de configuración. Si el valor de FileMappingSize no existe, el tamaño de memoria compartida independiente se establece en una cuarta (1/4) la configuración global en el archivo de configuración.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Diagnostics.PerformanceCounter>  
 <xref:System.Diagnostics.PerformanceCounterCategory>  
 <xref:System.Diagnostics.PerformanceCounter.InstanceLifetime%2A>  
 <xref:System.Diagnostics.PerformanceCounterInstanceLifetime>
