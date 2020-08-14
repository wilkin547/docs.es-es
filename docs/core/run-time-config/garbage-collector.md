---
title: Valores de configuración del recolector de elementos no utilizados
description: Obtenga información sobre los valores del entorno de ejecución para configurar el modo en el que el recolector de elementos no utilizados administra la memoria de las aplicaciones de .NET Core.
ms.date: 07/10/2020
ms.topic: reference
ms.openlocfilehash: 91d155b638c7e69b3d2c0216266a7c0c0410db4c
ms.sourcegitcommit: ef50c99928183a0bba75e07b9f22895cd4c480f8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2020
ms.locfileid: "87915997"
---
# <a name="run-time-configuration-options-for-garbage-collection"></a>Opciones de configuración del entorno de ejecución para la recolección de elementos no utilizados

Esta página contiene información sobre la configuración del recolector de elementos no utilizados (GC) que se puede cambiar en el entorno de ejecución. Si intenta lograr el máximo rendimiento de una aplicación en ejecución, valore la posibilidad de usar esta configuración. Sin embargo, los valores predeterminados proporcionan un rendimiento óptimo para la mayoría de aplicaciones en situaciones habituales.

En esta página, la configuración se organiza en grupos. La configuración de cada grupo se usa normalmente junto con las otras para lograr un resultado concreto.

> [!NOTE]
>
> - La aplicación también puede cambiar dinámicamente esta configuración mientras se ejecuta, por lo que se puede invalidar cualquier valor del entorno de ejecución que haya establecido.
> - Por lo general, algunos valores de configuración, como el [nivel de latencia](../../standard/garbage-collection/latency.md), se establecen únicamente a través de la API en tiempo de diseño. Estos valores se omiten en esta página.
> - En el caso de los valores numéricos, use la notación decimal para la configuración del archivo *runtimeconfig.json* y la notación hexadecimal para la configuración de las variables de entorno. Para los valores hexadecimales, puede especificarlos con o sin el prefijo "0x".

## <a name="flavors-of-garbage-collection"></a>Tipos de recolección de elementos no utilizados

Los dos tipos principales de recolección de elementos no utilizados son la GC de estación de trabajo y la de servidor. Para más información sobre la diferencia entre estos dos tipos, consulte [Recolección de elementos no utilizados de estación de trabajo y de servidor](../../standard/garbage-collection/workstation-server-gc.md).

Los subtipos de la recolección de elementos no utilizados son en segundo plano y no simultáneos.

Use la configuración siguiente para seleccionar los tipos de la recolección de elementos no utilizados:

- [Recolección de elementos no utilizados de estación de trabajo y de servidor](#workstation-vs-server)
- [GC en segundo plano](#background-gc)

### <a name="workstation-vs-server"></a>Estación de trabajo frente a servidor

- Configura si la aplicación usa la recolección de elementos no utilizados de estación de trabajo o la de servidor.
- Predeterminado: recolección de elementos no utilizados de estación de trabajo. Esto es equivalente a establecer el valor en `false`.

| | Nombre de valor | Valores | Versión introducida |
| - | - | - | - |
| **runtimeconfig.json** | `System.GC.Server` | `false`: estación de trabajo.<br/>`true`: servidor. | .NET Core 1.0 |
| **Propiedad de MSBuild** | `ServerGarbageCollection` | `false`: estación de trabajo.<br/>`true`: servidor. | .NET Core 1.0 |
| **Variable del entorno** | `COMPlus_gcServer` | `0`: estación de trabajo.<br/>`1`: servidor. | .NET Core 1.0 |
| **app.config para .NET Framework** | [GCServer](../../framework/configure-apps/file-schema/runtime/gcserver-element.md) | `false`: estación de trabajo.<br/>`true`: servidor. |  |

#### <a name="examples"></a>Ejemplos

Archivo *runtimeconfig.json*:

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.Server": true
      }
   }
}
```

Archivo del proyecto:

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ServerGarbageCollection>true</ServerGarbageCollection>
  </PropertyGroup>

</Project>
```

### <a name="background-gc"></a>GC en segundo plano

- Configura si está habilitada la recolección de elementos no utilizados en segundo plano (simultánea).
- Predeterminado: uso de GC en segundo plano. Esto es equivalente a establecer el valor en `true`.
- Para más información, consulte [Recolección de elementos no utilizados en segundo plano](../../standard/garbage-collection/background-gc.md).

| | Nombre de valor | Valores | Versión introducida |
| - | - | - | - |
| **runtimeconfig.json** | `System.GC.Concurrent` | `true`: GC en segundo plano.<br/>`false`: GC no simultáneo. | .NET Core 1.0 |
| **Propiedad de MSBuild** | `ConcurrentGarbageCollection` | `true`: GC en segundo plano.<br/>`false`: GC no simultáneo. | .NET Core 1.0 |
| **Variable del entorno** | `COMPlus_gcConcurrent` | `1`: GC en segundo plano.<br/>`0`: GC no simultáneo. | .NET Core 1.0 |
| **app.config para .NET Framework** | [gcConcurrent](../../framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) | `true`: GC en segundo plano.<br/>`false`: GC no simultáneo. |  |

#### <a name="examples"></a>Ejemplos

Archivo *runtimeconfig.json*:

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.Concurrent": false
      }
   }
}
```

Archivo del proyecto:

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ConcurrentGarbageCollection>false</ConcurrentGarbageCollection>
  </PropertyGroup>

</Project>
```

## <a name="manage-resource-usage"></a>Administración del uso de recursos

Use la siguiente configuración para administrar el uso del procesador y la memoria del recolector de elementos no utilizados:

- [Affinitize](#affinitize) (Afinidad)
- [Affinitize mask](#affinitize-mask) (Máscara de afinidad)
- [Affinitize ranges](#affinitize-ranges) (Intervalos de afinidad)
- [Grupos de CPU](#cpu-groups)
- [Heap count](#heap-count) (Recuento de montones)
- [Heap limit](#heap-limit) (Límite del montón)
- [Heap limit percent](#heap-limit-percent) (Límite del montón (porcentaje))
- [High memory percent](#high-memory-percent) (Uso de memoria alto (porcentaje))
- [Límites por cada montón de objetos](#per-object-heap-limits)
- [Per-object-heap limit percents](#per-object-heap-limit-percents) (Límite por montón de objetos (porcentaje))
- [Retain VM](#retain-vm) (Conservar VM)

Para obtener más información sobre algunos de estos valores, vea la entrada de blog en la que se detalla el [término medio entre la GC de la estación de trabajo y del servidor](https://devblogs.microsoft.com/dotnet/middle-ground-between-server-and-workstation-gc/).

### <a name="heap-count"></a>Heap count (Recuento de montones)

- Limita el número de montones creados por el recolector de elementos no utilizados.
- Solo se aplica a la recolección de elementos no utilizados del servidor.
- Si la [afinidad del procesador de GC](#affinitize) está habilitada (el valor predeterminado) el valor del recuento de montones establece afinidad entre `n` montones o subprocesos de GC en los primeros `n` procesadores. (Use los valores [affinitize mask](#affinitize-mask) o [affinitize ranges](#affinitize-ranges) para especificar exactamente los procesadores entre los que se va a establecer afinidad).
- Si la [afinidad del procesador de GC](#affinitize) está deshabilitada, esta configuración limita el número de montones de GC.
- Para obtener más información, vea la sección [Comentarios de GCHeapCount](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md#remarks).

| | Nombre de valor | Valores | Versión introducida |
| - | - | - | - |
| **runtimeconfig.json** | `System.GC.HeapCount` | *valor decimal* | .NET Core 3.0 |
| **Variable del entorno** | `COMPlus_GCHeapCount` | *valor hexadecimal* | .NET Core 3.0 |
| **app.config para .NET Framework** | [GCHeapCount](../../framework/configure-apps/file-schema/runtime/gcheapcount-element.md) | *valor decimal* | .NET Framework 4.6.2 |

Ejemplo:

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.HeapCount": 16
      }
   }
}
```

> [!TIP]
> Si configura la opción en *runtimeconfig.json*, especifique un valor decimal. Si configura la opción como una variable de entorno, especifique un valor hexadecimal. Por ejemplo, para limitar el número de montones a 16, los valores serían 16 para el archivo JSON y 0x10 o 10 para la variable de entorno.

### <a name="affinitize-mask"></a>Affinitize mask (Máscara de afinidad)

- Especifica los procesadores exactos que deben usar los subprocesos del recolector de elementos no utilizados.
- Si la [afinidad del procesador de GC](#affinitize) está deshabilitada, esta configuración se ignora.
- Solo se aplica a la recolección de elementos no utilizados del servidor.
- El valor es una máscara de bits que define los procesadores que están disponibles para el proceso. Por ejemplo, un valor decimal de 1023 (o un valor hexadecimal de 0x3FF o 3FF si utiliza la variable de entorno) es 0011 1111 1111 en notación binaria. Esto especifica que se usarán los 10 primeros procesadores. Para especificar los 10 procesadores siguientes, es decir, los procesadores 10-19, especifique un valor decimal de 1047552 (o un valor hexadecimal de 0xFFC00 o FFC00), que es equivalente a un valor binario de 1111 1111 1100 0000 0000.

| | Nombre de valor | Valores | Versión introducida |
| - | - | - | - |
| **runtimeconfig.json** | `System.GC.HeapAffinitizeMask` | *valor decimal* | .NET Core 3.0 |
| **Variable del entorno** | `COMPlus_GCHeapAffinitizeMask` | *valor hexadecimal* | .NET Core 3.0 |
| **app.config para .NET Framework** | [GCHeapAffinitizeMask](../../framework/configure-apps/file-schema/runtime/gcheapaffinitizemask-element.md) | *valor decimal* | .NET Framework 4.6.2 |

Ejemplo:

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.HeapAffinitizeMask": 1023
      }
   }
}
```

### <a name="affinitize-ranges"></a>Affinitize ranges (Intervalos de afinidad)

- Especifica la lista de procesadores que se van a usar para los subprocesos del recolector de elementos no utilizados.
- Este valor es similar a [System.GC.HeapAffinitizeMask](#affinitize-mask), salvo que permite especificar más de 64 procesadores.
- En el caso de los sistemas operativos Windows, agregue el prefijo con el [grupo de CPU](/windows/win32/procthread/processor-groups) correspondiente al número o el rango del procesador, por ejemplo, "0:1-10,0:12,1:50-52,1:70".
- Si la [afinidad del procesador de GC](#affinitize) está deshabilitada, esta configuración se ignora.
- Solo se aplica a la recolección de elementos no utilizados del servidor.
- Para obtener más información, vea el artículo del blog de Maoni Stephens sobre la [mejora de la configuración de la CPU para la GC en máquinas con > 64 CPU](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/).

| | Nombre de valor | Valores | Versión introducida |
| - | - | - | - |
| **runtimeconfig.json** | `System.GC.GCHeapAffinitizeRanges` | Lista separada por comas de números de procesador o rangos de números de procesador.<br/>Ejemplo de Unix: "1-10,12,50-52,70"<br/>Ejemplo de Windows: "0:1-10,0:12,1:50-52,1:70" | .NET Core 3.0 |
| **Variable del entorno** | `COMPlus_GCHeapAffinitizeRanges` | Lista separada por comas de números de procesador o rangos de números de procesador.<br/>Ejemplo de Unix: "1-10,12,50-52,70"<br/>Ejemplo de Windows: "0:1-10,0:12,1:50-52,1:70" | .NET Core 3.0 |

Ejemplo:

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.GCHeapAffinitizeRanges": "0:1-10,0:12,1:50-52,1:70"
      }
   }
}
```

### <a name="cpu-groups"></a>Grupos de CPU

- Configura si el recolector de elementos no utilizados usa [grupos de CPU](/windows/win32/procthread/processor-groups) o no.

  Cuando un equipo Windows de 64 bits tiene varios grupos de CPU, es decir, hay más de 64 procesadores, la habilitación de este elemento amplía la recolección de elementos no utilizados en todos los grupos de CPU. El recolector de elementos no utilizados usa todos los núcleos para crear y equilibrar montones.

- Solo se aplica a la recolección de elementos no utilizados del servidor en sistemas operativos Windows de 64 bits.
- Predeterminado: GC no se extiende por los grupos de CPU. Esto es equivalente a establecer el valor en `0`.
- Para obtener más información, vea el artículo del blog de Maoni Stephens sobre la [mejora de la configuración de la CPU para la GC en máquinas con > 64 CPU](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/).

| | Nombre de valor | Valores | Versión introducida |
| - | - | - | - |
| **runtimeconfig.json** | `System.GC.CpuGroup` | `0`: deshabilitado.<br/>`1`: habilitado. | .NET 5.0 |
| **Variable del entorno** | `COMPlus_GCCpuGroup` | `0`: deshabilitado.<br/>`1`: habilitado. | .NET Core 1.0 |
| **app.config para .NET Framework** | [GCCpuGroup](../../framework/configure-apps/file-schema/runtime/gccpugroup-element.md) | `false`: deshabilitado.<br/>`true`: habilitado. |  |

> [!NOTE]
> Para configurar Common Language Runtime (CLR) con el fin de distribuir también los subprocesos del grupo de subprocesos entre todos los grupos de CPU, habilite la opción [Elemento Thread_UseAllCpuGroups](../../framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md). En el caso de las aplicaciones de .NET Core, se puede habilitar esta opción estableciendo el valor de la variable de entorno `COMPlus_Thread_UseAllCpuGroups` en `1`.

### <a name="affinitize"></a>Affinitize (Afinidad)

- Especifica si *establecer afinidad* entre subprocesos de recolección de elementos no utilizados con procesadores. El hecho de establecer afinidad entre un subproceso de GC significa que solo puede ejecutarse en su CPU concreta. Se crea un montón para cada subproceso de GC.
- Solo se aplica a la recolección de elementos no utilizados del servidor.
- Predeterminado: establecer afinidad entre subprocesos de recolección de elementos no utilizados con procesadores. Esto es equivalente a establecer el valor en `false`.

| | Nombre de valor | Valores | Versión introducida |
| - | - | - | - |
| **runtimeconfig.json** | `System.GC.NoAffinitize` | `false`: establecer afinidad.<br/>`true`: no establecer afinidad. | .NET Core 3.0 |
| **Variable del entorno** | `COMPlus_GCNoAffinitize` | `0`: establecer afinidad.<br/>`1`: no establecer afinidad. | .NET Core 3.0 |
| **app.config para .NET Framework** | [GCNoAffinitize](../../framework/configure-apps/file-schema/runtime/gcnoaffinitize-element.md) | `false`: establecer afinidad.<br/>`true`: no establecer afinidad. | .NET Framework 4.6.2 |

Ejemplo:

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.NoAffinitize": true
      }
   }
}
```

### <a name="heap-limit"></a>Heap limit (Límite del montón)

- Especifica el tamaño máximo de confirmación, en bytes, para el montón de GC y la contabilidad de GC.
- Esta configuración solo se aplica a los equipos de 64 bits.
- Este valor se omite si se configuran los [límites por cada montón de objetos](#per-object-heap-limits).
- El valor predeterminado, que solo se aplica en ciertos casos, es el mayor de 20 MB o de 75 % del límite de memoria del contenedor. El valor predeterminado se aplica si:

  - El proceso se ejecuta dentro de un contenedor que tiene un límite de memoria especificado.
  - No se ha establecido [System.GC.HeapHardLimitPercent](#heap-limit-percent).

| | Nombre de valor | Valores | Versión introducida |
| - | - | - | - |
| **runtimeconfig.json** | `System.GC.HeapHardLimit` | *valor decimal* | .NET Core 3.0 |
| **Variable del entorno** | `COMPlus_GCHeapHardLimit` | *valor hexadecimal* | .NET Core 3.0 |

Ejemplo:

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.HeapHardLimit": 209715200
      }
   }
}
```

> [!TIP]
> Si configura la opción en *runtimeconfig.json*, especifique un valor decimal. Si configura la opción como una variable de entorno, especifique un valor hexadecimal. Por ejemplo, para especificar un límite de montón de 200 mebibytes (MiB), los valores serían 209715200 para el archivo JSON y 0xC800000 o C800000 para la variable de entorno.

### <a name="heap-limit-percent"></a>Heap limit percent (Límite del montón (porcentaje))

- Especifica el uso del montón de GC permitido como porcentaje de la memoria física total.
- Si también se establece [System.GC.HeapHardLimit](#heap-limit), este valor se omite.
- Esta configuración solo se aplica a los equipos de 64 bits.
- Si el proceso se ejecuta dentro de un contenedor que tiene un límite de memoria especificado, el porcentaje se calcula como un porcentaje de ese límite de memoria.
- Este valor se omite si se configuran los [límites por cada montón de objetos](#per-object-heap-limits).
- El valor predeterminado, que solo se aplica en ciertos casos, es el menor de 20 MB o 75 % del límite de memoria del contenedor. El valor predeterminado se aplica si:

  - El proceso se ejecuta dentro de un contenedor que tiene un límite de memoria especificado.
  - No se ha establecido [System.GC.HeapHardLimit](#heap-limit).

| | Nombre de valor | Valores | Versión introducida |
| - | - | - | - |
| **runtimeconfig.json** | `System.GC.HeapHardLimitPercent` | *valor decimal* | .NET Core 3.0 |
| **Variable del entorno** | `COMPlus_GCHeapHardLimitPercent` | *valor hexadecimal* | .NET Core 3.0 |

Ejemplo:

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.HeapHardLimitPercent": 30
      }
   }
}
```

> [!TIP]
> Si configura la opción en *runtimeconfig.json*, especifique un valor decimal. Si configura la opción como una variable de entorno, especifique un valor hexadecimal. Por ejemplo, para limitar el uso del montón al 30 %, los valores serían 30 para el archivo JSON y 0x1E o 1E para la variable de entorno.

### <a name="per-object-heap-limits"></a>Límites por cada montón de objetos

Puede especificar el uso de montones permitidos de la recolección de elementos no utilizados por cada objeto. Los diferentes montones son el montón de objetos grandes (LOH), el montón de objetos pequeños (SOH) y el montón de objetos anclados (POH).

- Si especifica un valor para `COMPLUS_GCHeapHardLimitSOH`, `COMPLUS_GCHeapHardLimitLOH` o `COMPLUS_GCHeapHardLimitPOH`, también debe especificar un valor para `COMPLUS_GCHeapHardLimitSOH` y `COMPLUS_GCHeapHardLimitLOH`. Si no lo hace, el runtime no se inicializará.
- El valor predeterminado para `COMPLUS_GCHeapHardLimitPOH` es 0. `COMPLUS_GCHeapHardLimitSOH` y `COMPLUS_GCHeapHardLimitLOH` no tienen valores predeterminados.

| | Nombre de valor | Valores | Versión introducida |
| - | - | - | - |
| **runtimeconfig.json** | `System.GC.HeapHardLimitSOH` | *valor decimal* | .NET 5.0 |
| **Variable del entorno** | `COMPLUS_GCHeapHardLimitSOH` | *valor hexadecimal* | .NET 5.0 |

| | Nombre de valor | Valores | Versión introducida |
| - | - | - | - |
| **runtimeconfig.json** | `System.GC.HeapHardLimitLOH` | *valor decimal* | .NET 5.0 |
| **Variable del entorno** | `COMPLUS_GCHeapHardLimitLOH` | *valor hexadecimal* | .NET 5.0 |

| | Nombre de valor | Valores | Versión introducida |
| - | - | - | - |
| **runtimeconfig.json** | `System.GC.HeapHardLimitPOH` | *valor decimal* | .NET 5.0 |
| **Variable del entorno** | `COMPLUS_GCHeapHardLimitPOH` | *valor hexadecimal* | .NET 5.0 |

> [!TIP]
> Si configura la opción en *runtimeconfig.json*, especifique un valor decimal. Si configura la opción como una variable de entorno, especifique un valor hexadecimal. Por ejemplo, para especificar un límite de montón de 200 mebibytes (MiB), los valores serían 209715200 para el archivo JSON y 0xC800000 o C800000 para la variable de entorno.

### <a name="per-object-heap-limit-percents"></a>Per-object-heap limit percents (Límite por montón de objetos (porcentaje))

Puede especificar el uso de montones permitidos de la recolección de elementos no utilizados por cada objeto. Los diferentes montones son el montón de objetos grandes (LOH), el montón de objetos pequeños (SOH) y el montón de objetos anclados (POH).

- Si especifica un valor para `COMPLUS_GCHeapHardLimitSOHPercent`, `COMPLUS_GCHeapHardLimitLOHPercent` o `COMPLUS_GCHeapHardLimitPOHPercent`, también debe especificar un valor para `COMPLUS_GCHeapHardLimitSOHPercent` y `COMPLUS_GCHeapHardLimitLOHPercent`. Si no lo hace, el runtime no se inicializará.
- Estos valores se omiten si se especifican `COMPLUS_GCHeapHardLimitSOH`, `COMPLUS_GCHeapHardLimitLOH` y `COMPLUS_GCHeapHardLimitPOH`.
- Un valor de 1 significa que la recolección de elementos no utilizados usa el 1 % de la memoria física total para ese montón de objetos.
- Cada valor debe ser mayor que cero y menor o igual que 100. Además, la suma de los tres valores de porcentaje debe ser inferior a 100. En caso contrario, el runtime no se inicializará.

| | Nombre de valor | Valores | Versión introducida |
| - | - | - | - |
| **runtimeconfig.json** | `System.GC.HeapHardLimitSOHPercent` | *valor decimal* | .NET 5.0 |
| **Variable del entorno** | `COMPLUS_GCHeapHardLimitSOHPercent` | *valor hexadecimal* | .NET 5.0 |

| | Nombre de valor | Valores | Versión introducida |
| - | - | - | - |
| **runtimeconfig.json** | `System.GC.HeapHardLimitLOHPercent` | *valor decimal* | .NET 5.0 |
| **Variable del entorno** | `COMPLUS_GCHeapHardLimitLOHPercent` | *valor hexadecimal* | .NET 5.0 |

| | Nombre de valor | Valores | Versión introducida |
| - | - | - | - |
| **runtimeconfig.json** | `System.GC.HeapHardLimitPOHPercent` | *valor decimal* | .NET 5.0 |
| **Variable del entorno** | `COMPLUS_GCHeapHardLimitPOHPercent` | *valor hexadecimal* | .NET 5.0 |

> [!TIP]
> Si configura la opción en *runtimeconfig.json*, especifique un valor decimal. Si configura la opción como una variable de entorno, especifique un valor hexadecimal. Por ejemplo, para limitar el uso del montón al 30 %, los valores serían 30 para el archivo JSON y 0x1E o 1E para la variable de entorno.

### <a name="high-memory-percent"></a>High memory percent (Uso de memoria alto (porcentaje))

La carga de memoria se indica mediante el porcentaje de memoria física en uso. De forma predeterminada, cuando la carga de memoria física alcanza el **90 %** , la recolección de elementos no utilizados se vuelve más agresiva a la hora de realizar recolecciones de elementos no utilizados completas y compactas para evitar la paginación. Cuando la carga de memoria está por debajo del 90 %, la recolección de elementos no utilizados favorece las recolecciones en segundo plano de recolecciones de elementos no utilizados completas, que tienen pausas más cortas pero no reducen mucho el tamaño total del montón. En los equipos con una cantidad de memoria considerable (80 GB o más), el umbral de carga predeterminado está entre el 90 % y el 97 %.

El umbral de carga de uso de memoria alto se puede ajustar mediante la variable de entorno `COMPlus_GCHighMemPercent` o la opción de configuración JSON `System.GC.HighMemoryPercent`. Considere la posibilidad de ajustar el umbral si quiere controlar el tamaño del montón. Por ejemplo, en el proceso dominante de un equipo con 64 GB de memoria, es razonable que la recolección de elementos no utilizados empiece a reaccionar cuando haya un 10 % de memoria disponible. Pero en el caso de procesos más pequeños, por ejemplo, un proceso que solo usa 1 GB de memoria, la recolección de elementos no utilizados puede ejecutarse cómodamente con menos del 10 % de memoria disponible. En estos procesos más pequeños, considere la posibilidad de establecer un umbral más alto. Por otro lado, si quiere que los procesos más grandes tengan tamaños de montón más pequeños (incluso cuando haya mucha memoria física disponible), la reducción de este umbral es una manera eficaz de que la recolección de elementos no utilizados reaccione antes para reducir el montón.

> [!NOTE]
> En el caso de los procesos que se ejecutan en un contenedor, la recolección de elementos no utilizados considera la memoria física según el límite del contenedor.

| | Nombre de valor | Valores | Versión introducida |
| - | - | - | - |
| **runtimeconfig.json** | `System.GC.HighMemoryPercent` | *valor decimal* | .NET 5.0 |
| **Variable del entorno** | `COMPlus_GCHighMemPercent` | *valor hexadecimal* | |

> [!TIP]
> Si configura la opción en *runtimeconfig.json*, especifique un valor decimal. Si configura la opción como una variable de entorno, especifique un valor hexadecimal. Por ejemplo, para establecer el umbral de uso de memoria alto en el 75 %, los valores serían 75 para el archivo JSON y 0x4B o 4B para la variable de entorno.

### <a name="retain-vm"></a>Retain VM (Conservar VM)

- Configura si los segmentos que se deben eliminar se ponen en una lista en espera para usarlos en el futuro o se devuelven al sistema operativo (SO).
- Predeterminado: devolver los segmentos al sistema operativo. Esto es equivalente a establecer el valor en `false`.

| | Nombre de valor | Valores | Versión introducida |
| - | - | - | - |
| **runtimeconfig.json** | `System.GC.RetainVM` | `false`: liberar al sistema operativo.<br/>`true`: poner en espera. | .NET Core 1.0 |
| **Propiedad de MSBuild** | `RetainVMGarbageCollection` | `false`: liberar al sistema operativo.<br/>`true`: poner en espera. | .NET Core 1.0 |
| **Variable del entorno** | `COMPlus_GCRetainVM` | `0`: liberar al sistema operativo.<br/>`1`: poner en espera. | .NET Core 1.0 |

#### <a name="examples"></a>Ejemplos

Archivo *runtimeconfig.json*:

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.RetainVM": true
      }
   }
}
```

Archivo del proyecto:

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <RetainVMGarbageCollection>true</RetainVMGarbageCollection>
  </PropertyGroup>

</Project>
```

## <a name="large-pages"></a>Páginas grandes

- Especifica si se deben usar páginas grandes cuando se establece un límite máximo de montones.
- Predeterminado: no utilizar páginas grandes cuando se establezca un límite rígido de montones. Esto es equivalente a establecer el valor en `0`.
- Se trata de un valor de configuración experimental.

| | Nombre de valor | Valores | Versión introducida |
| - | - | - | - |
| **runtimeconfig.json** | N/D | N/D | N/D |
| **Variable del entorno** | `COMPlus_GCLargePages` | `0`: deshabilitado.<br/>`1`: habilitado. | .NET Core 3.0 |

## <a name="allow-large-objects"></a>Allow large objects (Permitir objetos grandes)

- Configura la compatibilidad del recolector de elementos no utilizados en plataformas de 64 bits para matrices de más de 2 gigabytes (GB) de tamaño total.
- Predeterminado: GC admite matrices de más de 2 GB. Esto es equivalente a establecer el valor en `1`.
- Esta opción puede quedar obsoleta en una versión futura de .NET.

| | Nombre de valor | Valores | Versión introducida |
| - | - | - | - |
| **runtimeconfig.json** | N/D | N/D | N/D |
| **Variable del entorno** | `COMPlus_gcAllowVeryLargeObjects` | `1`: habilitado.<br/> `0`: deshabilitado. | .NET Core 1.0 |
| **app.config para .NET Framework** | [gcAllowVeryLargeObjects](../../framework/configure-apps/file-schema/runtime/gcallowverylargeobjects-element.md) | `1`: habilitado.<br/> `0`: deshabilitado. | .NET Framework 4.5 |

## <a name="large-object-heap-threshold"></a>Umbral del montón de objetos grandes

- Especifica el tamaño del umbral, en bytes, que provoca que los objetos vayan al montón de objetos grandes (LOH).
- El valor predeterminado del umbral es de 85 000 bytes.
- El valor que especifique debe ser mayor que el umbral predeterminado.

| | Nombre de valor | Valores | Versión introducida |
| - | - | - | - |
| **runtimeconfig.json** | `System.GC.LOHThreshold` | *valor decimal* | .NET Core 1.0 |
| **Variable del entorno** | `COMPlus_GCLOHThreshold` | *valor hexadecimal* | .NET Core 1.0 |
| **app.config para .NET Framework** | [GCLOHThreshold](../../framework/configure-apps/file-schema/runtime/gclohthreshold-element.md) | *valor decimal* | .NET Framework 4.8 |

Ejemplo:

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.LOHThreshold": 120000
      }
   }
}
```

> [!TIP]
> Si configura la opción en *runtimeconfig.json*, especifique un valor decimal. Si configura la opción como una variable de entorno, especifique un valor hexadecimal. Por ejemplo, para establecer un tamaño de umbral de 120 000 bytes, los valores serían 120000 para el archivo JSON y 0x1D4C0 o 1D4C0 para la variable de entorno.

## <a name="standalone-gc"></a>GC independiente

- Especifica una ruta de acceso a la biblioteca que contiene el recolector de elementos no utilizados que el entorno de ejecución pretende cargar.
- Para obtener más información, vea [Diseño del cargador de GC independiente](https://github.com/dotnet/runtime/blob/master/docs/design/features/standalone-gc-loading.md).

| | Nombre de valor | Valores | Versión introducida |
| - | - | - | - |
| **runtimeconfig.json** | N/D | N/D | N/D |
| **Variable del entorno** | `COMPlus_GCName` | *string_path* | .NET Core 2.0 |
