---
title: Valores de configuración del recolector de elementos no utilizados
description: Obtenga información sobre los valores del entorno de ejecución para configurar el modo en el que el recolector de elementos no utilizados administra la memoria de las aplicaciones de .NET Core.
ms.date: 01/09/2020
ms.topic: reference
ms.openlocfilehash: dfb641eeda03d1acaa4771bd6253fcb33c4082a6
ms.sourcegitcommit: d9470d8b2278b33108332c05224d86049cb9484b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/17/2020
ms.locfileid: "81607815"
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

Los dos tipos principales de recolección de elementos no utilizados son la GC de estación de trabajo y la de servidor. Para obtener más información sobre la diferencia entre estos dos tipos, vea [Fundamentos de la recolección de elementos no utilizados](../../standard/garbage-collection/fundamentals.md#workstation-and-server-garbage-collection).

Los subtipos de la recolección de elementos no utilizados son en segundo plano y no simultáneos.

Use la configuración siguiente para seleccionar los tipos de la recolección de elementos no utilizados:

### <a name="systemgcservercomplus_gcserver"></a>System.GC.Server/COMPlus_gcServer

- Configura si la aplicación usa la recolección de elementos no utilizados de estación de trabajo o la de servidor.
- Predeterminado: recolección de elementos no utilizados de estación de trabajo (`false`).

| | Nombre de valor | Valores | Versión introducida |
| - | - | - | - |
| **runtimeconfig.json** | `System.GC.Server` | `false`: estación de trabajo.<br/>`true`: servidor. | .NET Core 1.0 |
| **Propiedad de MSBuild** | `ServerGarbageCollection` | `false`: estación de trabajo.<br/>`true`: servidor. | .NET Core 1.0 |
| **Variable del entorno** | `COMPlus_gcServer` | `0`: estación de trabajo.<br/>`1`: servidor. | .NET Core 1.0 |
| **app.config para .NET Framework** | [GCServer](../../framework/configure-apps/file-schema/runtime/gcserver-element.md) | `false`: estación de trabajo.<br/>`true`: servidor. |  |

### <a name="examples"></a>Ejemplos

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

### <a name="systemgcconcurrentcomplus_gcconcurrent"></a>System.GC.Concurrent/COMPlus_gcConcurrent

- Configura si está habilitada la recolección de elementos no utilizados en segundo plano (simultánea).
- Predeterminado: habilitado (`true`).
- Para obtener más información, vea [Recolección de elementos no utilizados en segundo plano](../../standard/garbage-collection/fundamentals.md#background-workstation-garbage-collection) y [Recolección de elementos no utilizados de servidor en segundo plano](../../standard/garbage-collection/fundamentals.md#background-server-garbage-collection).

| | Nombre de valor | Valores | Versión introducida |
| - | - | - | - |
| **runtimeconfig.json** | `System.GC.Concurrent` | `true`: GC en segundo plano.<br/>`false`: GC no simultáneo. | .NET Core 1.0 |
| **Propiedad de MSBuild** | `ConcurrentGarbageCollection` | `true`: GC en segundo plano.<br/>`false`: GC no simultáneo. | .NET Core 1.0 |
| **Variable del entorno** | `COMPlus_gcConcurrent` | `true`: GC en segundo plano.<br/>`false`: GC no simultáneo. | .NET Core 1.0 |
| **app.config para .NET Framework** | [gcConcurrent](../../framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) | `true`: GC en segundo plano.<br/>`false`: GC no simultáneo. |  |

### <a name="examples"></a>Ejemplos

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

Use los valores descritos en esta sección para administrar el uso del procesador y la memoria del recolector de elementos no utilizados.

Para obtener más información sobre algunos de estos valores, vea la entrada de blog en la que se detalla el [término medio entre la GC de la estación de trabajo y del servidor](https://devblogs.microsoft.com/dotnet/middle-ground-between-server-and-workstation-gc/).

### <a name="systemgcheapcountcomplus_gcheapcount"></a>System.GC.HeapCount/COMPlus_GCHeapCount

- Limita el número de montones creados por el recolector de elementos no utilizados.
- Solo se aplica a la recolección de elementos no utilizados del servidor.
- Si la [afinidad del procesador de GC](#systemgcnoaffinitizecomplus_gcnoaffinitize) está habilitada (el valor predeterminado) el valor del recuento de montones establece afinidad entre `n` montones o subprocesos de GC en los primeros `n` procesadores. (Use los valores [affinitize mask](#systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask) o [affinitize ranges](#systemgcgcheapaffinitizerangescomplus_gcheapaffinitizeranges) para especificar exactamente los procesadores entre los que se va a establecer afinidad).
- Si la [afinidad del procesador de GC](#systemgcnoaffinitizecomplus_gcnoaffinitize) está deshabilitada, esta configuración limita el número de montones de GC.
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

### <a name="systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask"></a>System.GC.HeapAffinitizeMask/COMPlus_GCHeapAffinitizeMask

- Especifica los procesadores exactos que deben usar los subprocesos del recolector de elementos no utilizados.
- Si la [afinidad del procesador de GC](#systemgcnoaffinitizecomplus_gcnoaffinitize) está deshabilitada, esta configuración se ignora.
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

### <a name="systemgcgcheapaffinitizerangescomplus_gcheapaffinitizeranges"></a>System.GC.GCHeapAffinitizeRanges/COMPlus_GCHeapAffinitizeRanges

- Especifica la lista de procesadores que se van a usar para los subprocesos del recolector de elementos no utilizados.
- Este valor es similar a [System.GC.HeapAffinitizeMask](#systemgcheapaffinitizemaskcomplus_gcheapaffinitizemask), salvo que permite especificar más de 64 procesadores.
- En el caso de los sistemas operativos Windows, agregue el prefijo con el [grupo de CPU](/windows/win32/procthread/processor-groups) correspondiente al número o el rango del procesador, por ejemplo, "0:1-10,0:12,1:50-52,1:70".
- Si la [afinidad del procesador de GC](#systemgcnoaffinitizecomplus_gcnoaffinitize) está deshabilitada, esta configuración se ignora.
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

### <a name="complus_gccpugroup"></a>COMPlus_GCCpuGroup

- Configura si el recolector de elementos no utilizados usa [grupos de CPU](/windows/win32/procthread/processor-groups) o no.

  Cuando un equipo Windows de 64 bits tiene varios grupos de CPU, es decir, hay más de 64 procesadores, la habilitación de este elemento amplía la recolección de elementos no utilizados en todos los grupos de CPU. El recolector de elementos no utilizados usa todos los núcleos para crear y equilibrar montones.

- Solo se aplica a la recolección de elementos no utilizados del servidor en sistemas operativos Windows de 64 bits.
- Predeterminado: deshabilitado (`0`).
- Para obtener más información, vea el artículo del blog de Maoni Stephens sobre la [mejora de la configuración de la CPU para la GC en máquinas con > 64 CPU](https://devblogs.microsoft.com/dotnet/making-cpu-configuration-better-for-gc-on-machines-with-64-cpus/).

| | Nombre de valor | Valores | Versión introducida |
| - | - | - | - |
| **runtimeconfig.json** | N/D | N/D | N/D |
| **Variable del entorno** | `COMPlus_GCCpuGroup` | `0`: deshabilitado.<br/>`1`: habilitado. | .NET Core 1.0 |
| **app.config para .NET Framework** | [GCCpuGroup](../../framework/configure-apps/file-schema/runtime/gccpugroup-element.md) | `false`: deshabilitado.<br/>`true`: habilitado. |  |

> [!NOTE]
> Para configurar Common Language Runtime (CLR) con el fin de distribuir también los subprocesos del grupo de subprocesos entre todos los grupos de CPU, habilite la opción [Elemento Thread_UseAllCpuGroups](../../framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md). En el caso de las aplicaciones de .NET Core, se puede habilitar esta opción estableciendo el valor de la variable de entorno `COMPlus_Thread_UseAllCpuGroups` en `1`.

### <a name="systemgcnoaffinitizecomplus_gcnoaffinitize"></a>System.GC.NoAffinitize/COMPlus_GCNoAffinitize

- Especifica si *establecer afinidad* entre subprocesos de recolección de elementos no utilizados con procesadores. El hecho de establecer afinidad entre un subproceso de GC significa que solo puede ejecutarse en su CPU concreta. Se crea un montón para cada subproceso de GC.
- Solo se aplica a la recolección de elementos no utilizados del servidor.
- Predeterminado: establecer afinidad entre subprocesos de recolección de elementos no utilizados con procesadores (`false`).

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

### <a name="systemgcheaphardlimitcomplus_gcheaphardlimit"></a>System.GC.HeapHardLimit/COMPlus_GCHeapHardLimit

- Especifica el tamaño máximo de confirmación, en bytes, para el montón de GC y la contabilidad de GC.
- Esta configuración solo se aplica a los equipos de 64 bits.
- El valor predeterminado, que solo se aplica en ciertos casos, es el menor de 20 MB o 75 % del límite de memoria del contenedor. El valor predeterminado se aplica si:

  - El proceso se ejecuta dentro de un contenedor que tiene un límite de memoria especificado.
  - No se ha establecido [System.GC.HeapHardLimitPercent](#systemgcheaphardlimitpercentcomplus_gcheaphardlimitpercent).

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

### <a name="systemgcheaphardlimitpercentcomplus_gcheaphardlimitpercent"></a>System.GC.HeapHardLimitPercent/COMPlus_GCHeapHardLimitPercent

- Especifica el uso del montón de GC permitido como porcentaje de la memoria física total.
- Si también se establece [System.GC.HeapHardLimit](#systemgcheaphardlimitcomplus_gcheaphardlimit), este valor se omite.
- Esta configuración solo se aplica a los equipos de 64 bits.
- Si el proceso se ejecuta dentro de un contenedor que tiene un límite de memoria especificado, el porcentaje se calcula como un porcentaje de ese límite de memoria.
- El valor predeterminado, que solo se aplica en ciertos casos, es el menor de 20 MB o 75 % del límite de memoria del contenedor. El valor predeterminado se aplica si:

  - El proceso se ejecuta dentro de un contenedor que tiene un límite de memoria especificado.
  - No se ha establecido [System.GC.HeapHardLimit](#systemgcheaphardlimitcomplus_gcheaphardlimit).

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

### <a name="systemgcretainvmcomplus_gcretainvm"></a>System.GC.RetainVM/COMPlus_GCRetainVM

- Configura si los segmentos que se deben eliminar se ponen en una lista en espera para usarlos en el futuro o se devuelven al sistema operativo (SO).
- Predeterminado: devolver los segmentos al sistema operativo (`false`).

| | Nombre de valor | Valores | Versión introducida |
| - | - | - | - |
| **runtimeconfig.json** | `System.GC.RetainVM` | `false`: liberar al sistema operativo.<br/>`true`: poner en espera. | .NET Core 1.0 |
| **Propiedad de MSBuild** | `RetainVMGarbageCollection` | `false`: liberar al sistema operativo.<br/>`true`: poner en espera. | .NET Core 1.0 |
| **Variable del entorno** | `COMPlus_GCRetainVM` | `0`: liberar al sistema operativo.<br/>`1`: poner en espera. | .NET Core 1.0 |

### <a name="examples"></a>Ejemplos

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

### <a name="complus_gclargepages"></a>COMPlus_GCLargePages

- Especifica si se deben usar páginas grandes cuando se establece un límite máximo de montones.
- Predeterminado: deshabilitado (`0`).
- Se trata de un valor de configuración experimental.

| | Nombre de valor | Valores | Versión introducida |
| - | - | - | - |
| **runtimeconfig.json** | N/D | N/D | N/D |
| **Variable del entorno** | `COMPlus_GCLargePages` | `0`: deshabilitado.<br/>`1`: habilitado. | .NET Core 3.0 |

## <a name="large-objects"></a>Objetos grandes

### <a name="complus_gcallowverylargeobjects"></a>COMPlus_gcAllowVeryLargeObjects

- Configura la compatibilidad del recolector de elementos no utilizados en plataformas de 64 bits para matrices de más de 2 gigabytes (GB) de tamaño total.
- Predeterminado: habilitado (`1`).
- Esta opción puede quedar obsoleta en una versión futura de .NET.

| | Nombre de valor | Valores | Versión introducida |
| - | - | - | - |
| **runtimeconfig.json** | N/D | N/D | N/D |
| **Variable del entorno** | `COMPlus_gcAllowVeryLargeObjects` | `1`: habilitado.<br/> `0`: deshabilitado. | .NET Core 1.0 |
| **app.config para .NET Framework** | [gcAllowVeryLargeObjects](../../framework/configure-apps/file-schema/runtime/gcallowverylargeobjects-element.md) | `1`: habilitado.<br/> `0`: deshabilitado. | .NET Framework 4.5 |

## <a name="large-object-heap-threshold"></a>Umbral del montón de objetos grandes

### <a name="systemgclohthresholdcomplus_gclohthreshold"></a>System.GC.LOHThreshold/COMPlus_GCLOHThreshold

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

### <a name="complus_gcname"></a>COMPlus_GCName

- Especifica una ruta de acceso a la biblioteca que contiene el recolector de elementos no utilizados que el entorno de ejecución pretende cargar.
- Para obtener más información, vea [Diseño del cargador de GC independiente](https://github.com/dotnet/runtime/blob/master/docs/design/features/standalone-gc-loading.md).

| | Nombre de valor | Valores | Versión introducida |
| - | - | - | - |
| **runtimeconfig.json** | N/D | N/D | N/D |
| **Variable del entorno** | `COMPlus_GCName` | *string_path* | .NET Core 2.0 |
