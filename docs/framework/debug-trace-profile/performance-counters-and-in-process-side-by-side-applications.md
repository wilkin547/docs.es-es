---
title: "Performance Counters and In-Process Side-By-Side Applications | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
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
  - "performance counters"
  - "performance counters,and in-process side-by-side applications"
  - "performance,.NET Framework applications"
  - "performance monitoring,counters"
ms.assetid: 6888f9be-c65b-4b03-a07b-df7ebdee2436
caps.latest.revision: 26
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 26
---
# Performance Counters and In-Process Side-By-Side Applications
Con Monitor de rendimiento \(Perfmon.exe\), es posible diferenciar los contadores de rendimiento según el runtime.  En este tema se describe el cambio que hay que realizar en el Registro para habilitar esta funcionalidad.  
  
## El comportamiento predeterminado  
 De forma predeterminada, Monitor de rendimiento muestra los contadores de rendimiento según la aplicación.  Sin embargo, hay dos escenarios en los que esto es problemático:  
  
-   Cuando supervisa dos aplicaciones que tienen el mismo nombre.  Por ejemplo, si ambas aplicaciones se llaman miapl.exe, una se mostrará como **miapl** y la otra como **miapl\#1** en la columna **Instancia**.  En este caso, es difícil hacer coincidir un contador de rendimiento con una aplicación determinada.  No está claro si los datos recopilados para **miapl\#1** hace referencia a la primera miapl.exe o a la segunda miapl.exe.  
  
-   Cuando una aplicación usa varias instancias de Common Language Runtime.  [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] admite escenarios de hospedaje en paralelo en el mismo proceso; es decir, un único proceso o aplicación puede cargar varias instancias de Common Language Runtime.  Si una única aplicación llamada miapl.exe carga dos instancias en tiempo de ejecución, de forma predeterminada, se designarán en la columna **Instancia** como **miapl** y **miapl\#1**.  En este caso, no está claro si **miapl** y **miapl\#1** se refieren a dos aplicaciones que tienen el mismo nombre o a la misma aplicación con dos runtime.  Si varias aplicaciones que tienen el mismo nombre cargan varios runtime, la ambigüedad es aún mayor.  
  
 Puede establecer una clave del Registro para eliminar esta ambigüedad.  Para las aplicaciones desarrolladas con [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], este cambio del Registro agrega un identificador de proceso seguido de un identificador de instancia en tiempo de ejecución al nombre de la aplicación en la columna **Instancia**.  En lugar de *application* o de *application*\#1, la aplicación se identifica ahora como \_`r`*runtimeID* de`p`*processID*de \_de *application*en la columna de **Instancia** .  Si una aplicación se desarrolló usando una versión anterior de Common Language Runtime, esa instancia se representa como *application\_*`p`*processID* siempre que [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] está instalado.  
  
## Contadores de rendimiento para aplicaciones en paralelo en proceso  
 Para administrar los contadores de rendimiento para varias versiones de Common Language Runtime hospedadas en una única aplicación, debe cambiar un único valor de clave del Registro, como se muestra en la tabla siguiente.  
  
|||  
|-|-|  
|Nombre de clave|HKEY\_LOCAL\_MACHINE\\System\\CurrentControlSet\\Services\\.NETFramework\\Performance|  
|Nombre del valor|ProcessNameFormat|  
|Tipo de valor|REG\_DWORD|  
|Valor|1 \(0x00000001\)|  
  
 El valor 0 para `ProcessNameFormat` indica que está habilitado el comportamiento predeterminado; es decir, Perfmon.exe muestra los contadores de rendimiento por aplicación.  Cuando se establece este valor en 1, Perfmon.exe elimina la ambigüedad entre varias versiones de una aplicación y proporciona contadores de rendimiento por runtime.  De momento, no se admite ningún otro valor para la clave del Registro `ProcessNameFormat`.  
  
 Después de actualizar el valor de la clave del Registro `ProcessNameFormat`, es preciso reiniciar Perfmon.exe o cualquier otro consumidor de los contadores de rendimiento para que la nueva característica de nomenclatura de instancias funcione correctamente.  
  
 En el ejemplo siguiente, se muestra cómo cambiar el valor de `ProcessNameFormat` mediante programación.  
  
 [!code-csharp[Conceptual.PerfCounters.InProSxS#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.perfcounters.inprosxs/cs/regsetting1.cs#1)]
 [!code-vb[Conceptual.PerfCounters.InProSxS#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.perfcounters.inprosxs/vb/regsetting1.vb#1)]  
  
 Cuando realiza este cambio del registro, Perfmon.exe muestra los nombres de las aplicaciones destinadas [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] como \_`r`*runtimeID*de`p`*processID*de \_de*application*, donde es el nombre *application* de la aplicación, *processID* es el identificador de proceso de la aplicación, y *runtimeID* es un identificador de Common Language Runtime.  Por ejemplo, si una aplicación denominada miapl.exe carga dos instancias de Common Language Runtime, Perfmon.exe puede identificar una instancia como miapl\_p1416\_r10 y la otra como miapl\_p3160\_r10.  El identificador en tiempo de ejecución solo elimina la ambigüedad de los runtime dentro de un proceso; no proporciona ninguna otra información sobre el runtime. \(Por ejemplo, el Id. de tiempo de ejecución no tiene ninguna relación con la versión o la SKU del runtime.\)  
  
 Si [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] está instalado, el cambio del Registro también afecta a las aplicaciones desarrolladas con versiones anteriores de .NET Framework.  Aparecen en Perfmon.exe como *application\_*`p`*processID*, donde es el nombre de aplicación *application* y *processID* es el identificador de proceso.  Por ejemplo, si se supervisan los contadores de rendimiento de dos aplicaciones llamadas miapl.exe, una podría aparecer como miapl\_p23900 y la otra como miapl\_p24908.  
  
> [!NOTE]
>  El identificador de proceso elimina la ambigüedad de resolver dos aplicaciones con el mismo nombre que usan versiones anteriores del runtime.  No es necesario un identificador del tiempo de ejecución para las versiones anteriores, ya que las versiones anteriores de Common Language Runtime no admiten escenarios en paralelo.  
  
 Si [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] no está presente o se ha desinstalado, establecer la clave del Registro no produce ningún efecto.  Esto significa que dos aplicaciones con el mismo nombre seguirán apareciendo en Perfmon.exe como *application* y *application\#1* \(por ejemplo, como **myapp** y **myapp\#1**\).