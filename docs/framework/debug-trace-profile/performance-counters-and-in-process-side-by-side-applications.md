---
title: Contadores de rendimiento y aplicaciones en paralelo en proceso
description: Revise los contadores de rendimiento y las aplicaciones en paralelo en proceso en .NET. Utilice Perfmon.exe para diferenciar los contadores de rendimiento por tiempo de ejecución.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- performance counters
- performance counters,and in-process side-by-side applications
- performance,.NET Framework applications
- performance monitoring,counters
ms.assetid: 6888f9be-c65b-4b03-a07b-df7ebdee2436
ms.openlocfilehash: eb05d9f5f930420827c6b3d94ea0ed34f64464fd
ms.sourcegitcommit: c23d9666ec75b91741da43ee3d91c317d68c7327
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85803864"
---
# <a name="performance-counters-and-in-process-side-by-side-applications"></a>Contadores de rendimiento y aplicaciones en paralelo en proceso
Con el Monitor de rendimiento (Perfmon.exe), es posible diferenciar los contadores de rendimiento por tiempo de ejecución. En este tema se describe el cambio del Registro necesario para habilitar esta funcionalidad.  
  
## <a name="the-default-behavior"></a>El comportamiento predeterminado  
 De forma predeterminada, el Monitor de rendimiento muestra los contadores de rendimiento según cada aplicación. Pero hay dos escenarios en los que esto es problemático:  
  
- Al supervisar dos aplicaciones que tienen el mismo nombre. Por ejemplo, si ambas aplicaciones se denominan myapp.exe, una se mostrará como **myapp** y la otra como **myapp#1** en la columna **Instance**. En este caso, es difícil que un contador de rendimiento coincida con una aplicación determinada. No está claro si los datos recopilados para **myapp#1** hacen referencia a la primera myapp.exe o a la segunda.  
  
- Cuando una aplicación usa varias instancias de Common Language Runtime. El .NET Framework 4 admite escenarios de hospedaje en paralelo en el proceso; es decir, un único proceso o aplicación puede cargar varias instancias del Common Language Runtime. Si una aplicación denominada myapp.exe carga dos instancias de tiempo de ejecución, se designarán en la columna **Instance** como **myapp** y **myapp#1** de forma predeterminada. En este caso, no está claro si **myapp** y **myapp#1** hacen referencia a dos aplicaciones con el mismo nombre, o a la misma aplicación con dos tiempos de ejecución. Si varias aplicaciones con el mismo nombre cargan varios tiempos de ejecución, la ambigüedad es incluso mayor.  
  
 Puede establecer una clave del Registro para eliminar esta ambigüedad. En el caso de las aplicaciones desarrolladas con el .NET Framework 4, este cambio del registro agrega un identificador de proceso seguido de un identificador de instancia en tiempo de ejecución al nombre de la aplicación en la columna **instancia** . En *lugar de la aplicación o* *la #1 de aplicación,* la aplicación se identifica ahora como *Application*_ `p` *processID* \_ `r` *runtimeID* en la columna **Instance** . Si una aplicación se desarrolló con una versión anterior del Common Language Runtime, esa instancia se representa como processID *de \_ aplicación*, `p` *processID* siempre que esté instalado el .NET Framework 4.  
  
## <a name="performance-counters-for-in-process-side-by-side-applications"></a>Contadores de rendimiento para aplicaciones en paralelo en proceso  
 Para administrar los contadores de rendimiento para varias versiones de Common Language Runtime que se hospedan en una sola aplicación, debe cambiar una única clave del Registro, como se muestra en la tabla siguiente.  
  
|||  
|-|-|  
|Nombre de clave|HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\\.NETFramework\Performance|  
|Nombre del valor|ProcessNameFormat|  
|Tipo de valor|REG_DWORD|  
|Valor|1 (0x00000001)|  
  
 Un valor de 0 para `ProcessNameFormat` indica que el comportamiento predeterminado está habilitado; es decir, Perfmon.exe muestra los contadores de rendimiento según cada aplicación. Cuando este valor se establece en 1, Perfmon.exe elimina la ambigüedad de varias versiones de una aplicación y proporciona contadores de rendimiento según cada tiempo de ejecución. Cualquier otro valor para la clave del Registro `ProcessNameFormat` no es compatible y se reserva para uso en el futuro.  
  
 Después de actualizar el valor de la clave del Registro `ProcessNameFormat`, debe reiniciar Perfmon.exe o cualquier otro consumidor de los contadores de rendimiento para que la nueva característica de asignación de nombres de instancia funcione correctamente.  
  
 En el siguiente ejemplo se muestra cómo cambiar el valor `ProcessNameFormat` mediante programación.  
  
 [!code-csharp[Conceptual.PerfCounters.InProSxS#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.perfcounters.inprosxs/cs/regsetting1.cs#1)]
 [!code-vb[Conceptual.PerfCounters.InProSxS#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.perfcounters.inprosxs/vb/regsetting1.vb#1)]  
  
 Cuando realice este cambio en el registro, Perfmon.exe mostrará los nombres de las aplicaciones que tienen como destino el .NET Framework 4 como *Application*_ `p` *processID* \_ `r` *runtimeID*, donde *Application* es el nombre de la aplicación, *processID* es el identificador de proceso de la aplicación y *runtimeID* es un identificador de Common Language Runtime. Por ejemplo, si una aplicación denominada myapp.exe carga dos instancias de Common Language Runtime, Perfmon.exe puede identificar una instancia como myapp_p1416_r10 y la segunda como myapp_p3160_r10. El identificador de tiempo de ejecución solo elimina la ambigüedad de los tiempos de ejecución dentro de un proceso; no proporciona ninguna otra información sobre el tiempo de ejecución. (Por ejemplo, el identificador de tiempo de ejecución no tiene ninguna relación con la versión o la SKU del tiempo de ejecución).  
  
 Si el .NET Framework 4 está instalado, el cambio en el registro también afecta a las aplicaciones desarrolladas con versiones anteriores de la .NET Framework. Aparecen en Perfmon.exe como *application_* `p` *processID*, donde *aplicación* es el nombre de la aplicación y *processID* es el identificador del proceso. Por ejemplo, si se supervisan los contadores de rendimiento de dos aplicaciones denominadas myapp.exe, es posible que una aparezca como myapp_p23900 y la otra como myapp_p24908.  
  
> [!NOTE]
> El identificador de proceso elimina la ambigüedad de resolver dos aplicaciones con el mismo nombre que usan versiones anteriores del tiempo de ejecución. No se necesita un identificador de tiempo de ejecución para las versiones anteriores, dado que las versiones anteriores de Common Language Runtime no admiten escenarios en paralelo.  
  
 Si el .NET Framework 4 no está presente o se desinstaló, el establecimiento de la clave del registro no tiene ningún efecto. Esto significa que dos aplicaciones con el mismo nombre seguirán apareciendo en Perfmon.exe como *aplicación* y *application#1* (por ejemplo, como **myapp** y **myapp#1**).
