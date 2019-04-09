---
title: <forcePerformanceCounterUniqueSharedMemoryReads> Elemento
ms.date: 03/30/2017
helpviewer_keywords:
- forcePerformanceCounterUniqueSharedMemoryReads element
- <forcePerformanceCounterUniqueSharedMemoryReads> element
ms.assetid: 91149858-4810-4f65-9b48-468488172c9b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1d4a205f643c844b2fe77d3aa5211b4bc1f322fd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59186971"
---
# <a name="forceperformancecounteruniquesharedmemoryreads-element"></a>\<forcePerformanceCounterUniqueSharedMemoryReads> Element
Especifica si PerfCounter.dll usa la configuración del Registro CategoryOptions en una aplicación de .NET Framework 1.1 para determinar si se van a cargar los datos del contador de rendimiento desde la memoria compartida específica de la categoría o la memoria global.  
  
 \<configuration>  
\<runtime>  
\<forcePerformanceCounterUniqueSharedMemoryReads>  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<forcePerformanceCounterUniqueSharedMemoryReads   
enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`enabled`|Atributo necesario.<br /><br /> Indica si PerfCounter.dll usa el valor del Registro CategoryOptions para determinar si se debe cargar los datos del contador de rendimiento de memoria compartida específica de la categoría o la memoria global.|  
  
## <a name="enabled-attribute"></a>Atributo enabled  
  
|Valor|Descripción|  
|-----------|-----------------|  
|`false`|PerfCounter.dll no utiliza el CategoryOptions esta configuración del registro es el valor predeterminado.|  
|`true`|PerfCounter.dll usa el valor del Registro CategoryOptions.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.|  
  
## <a name="remarks"></a>Comentarios  
 En las versiones de .NET Framework anteriores a la [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], la versión de PerfCounter.dll que cargó correspondía a la que se cargó en el proceso en tiempo de ejecución. Si un equipo tenía tanto la versión de .NET Framework 1.1 y la [!INCLUDE[dnprdnlong](../../../../../includes/dnprdnlong-md.md)] instalado, una aplicación de .NET Framework 1.1 cargaría la versión de .NET Framework 1.1 de PerfCounter.dll. A partir de la [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], se carga la versión instalada más reciente de PerfCounter.dll. Esto significa que una aplicación de .NET Framework 1.1 se cargará el [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] versión de PerfCounter.dll si el [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] está instalado en el equipo.  
  
 A partir de la [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], al consumir los contadores de rendimiento, PerfCounter.dll comprueba la entrada del Registro CategoryOptions de cada proveedor para determinar si debe leer desde la memoria compartida específica de la categoría o la memoria compartida global. El PerfCounter.dll de .NET Framework 1.1 no lee esa entrada del registro, porque no es consciente de la memoria compartida específica de la categoría; siempre lee la memoria compartida global.  
  
 Por compatibilidad con versiones anteriores, el [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] PerfCounter.dll no comprueba la entrada del Registro CategoryOptions al ejecutarse en una aplicación de .NET Framework 1.1. Simplemente usa memoria compartida global, al igual que el PerfCounter.dll de .NET Framework 1.1. Sin embargo, puede indicar la [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] PerfCounter.dll para comprobar la configuración del Registro habilitando el `<forcePerformanceCounterUniqueSharedMemoryReads>` elemento.  
  
> [!NOTE]
>  Habilitar la `<forcePerformanceCounterUniqueSharedMemoryReads>` elemento no garantiza que se utilizará memoria compartida específica de la categoría. El valor habilitado para `true` sólo hace que PerfCounter.dll hacer referencia a la configuración del Registro CategoryOptions. La configuración predeterminada para CategoryOptions es usar la memoria compartida específica de la categoría; Sin embargo, puede cambiar CategoryOptions para indicar que se debe usar la memoria compartida global.  
  
 La clave del registro que contiene el valor CategoryOptions es HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\\< categoryName\>\Performance. De forma predeterminada, CategoryOptions se establece en 3, que indica a PerfCounter.dll para usar memoria compartida específica de la categoría. Si CategoryOptions está establecido en 0, PerfCounter.dll usa memoria compartida global. Datos de instancia se reutilizará solo si el nombre de la instancia que se va a crear es idéntico a la instancia que se va a volver a usar. Todas las versiones podrán escribir en la categoría. Si CategoryOptions está establecido en 1, se utiliza la memoria compartida global, pero se pueden reutilizar los datos de instancia si el nombre de categoría es la misma longitud que la categoría que se va a volver a usar.  
  
 Los valores 0 y 1 pueden dar lugar a pérdidas de memoria y el rellenado de la memoria del contador de rendimiento.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente muestra cómo especificar que PerfCounter.dll debe hacer referencia a la entrada del Registro CategoryOptions para determinar si debe usar la memoria compartida específica de la categoría.  
  
```xml  
<configuration>  
  <runtime>  
    <forcePerformanceCounterUniqueSharedMemoryReads enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vea también

- [Esquema de la configuración de Common Language Runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [Esquema de los archivos de configuración](../../../../../docs/framework/configure-apps/file-schema/index.md)
