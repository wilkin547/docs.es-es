---
title: <forcePerformanceCounterUniqueSharedMemoryReads> (Elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- forcePerformanceCounterUniqueSharedMemoryReads element
- <forcePerformanceCounterUniqueSharedMemoryReads> element
ms.assetid: 91149858-4810-4f65-9b48-468488172c9b
ms.openlocfilehash: 742b444c445ba67d6977b622e615a6a8f591826e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154145"
---
# <a name="forceperformancecounteruniquesharedmemoryreads-element"></a>\<forcePerformanceCounterUniqueSharedMemoryReads> Element
Especifica si PerfCounter.dll usa la configuración del Registro CategoryOptions en una aplicación de .NET Framework 1.1 para determinar si se van a cargar los datos del contador de rendimiento desde la memoria compartida específica de la categoría o la memoria global.  
  
[**\<configuración>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<>en tiempo de ejecución**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<forcePerformanceCounterUniqueSharedMemoryReads>**  
  
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
|`enabled`|Atributo necesario.<br /><br /> Indica si PerfCounter.dll usa la configuración del Registro CategoryOptions para determinar si se deben cargar datos del contador de rendimiento desde memoria compartida específica de categoría o memoria global.|  
  
## <a name="enabled-attribute"></a>Atributo enabled  
  
|Value|Descripción|  
|-----------|-----------------|  
|`false`|PerfCounter.dll no usa la configuración del Registro CategoryOptions Este es el valor predeterminado.|  
|`true`|PerfCounter.dll utiliza la configuración del Registro CategoryOptions.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.|  
  
## <a name="remarks"></a>Observaciones  
 En las versiones de .NET Framework anteriores a .NET Framework 4, la versión de PerfCounter.dll que se cargó correspondía al tiempo de ejecución que se cargó en el proceso. Si un equipo tuviera instalada la versión 1.1 de .NET Framework y .NET Framework 2.0, una aplicación de .NET Framework 1.1 cargaría la versión de PerfCounter.dll de .NET Framework 1.1. A partir de .NET Framework 4, se carga la versión instalada más reciente de PerfCounter.dll. Esto significa que una aplicación de .NET Framework 1.1 cargará la versión de .NET Framework 4 de PerfCounter.dll si .NET Framework 4 está instalado en el equipo.  
  
 A partir de .NET Framework 4, al consumir contadores de rendimiento, PerfCounter.dll comprueba la entrada del Registro CategoryOptions para cada proveedor para determinar si debe leer desde memoria compartida específica de categoría o memoria compartida global. .NET Framework 1.1 PerfCounter.dll no lee esa entrada del Registro, porque no es consciente de la memoria compartida específica de la categoría; siempre lee de la memoria compartida global.  
  
 Por compatibilidad con versiones anteriores, .NET Framework 4 PerfCounter.dll no comprueba la entrada del Registro CategoryOptions cuando se ejecuta en una aplicación de .NET Framework 1.1. Simplemente usa memoria compartida global, al igual que .NET Framework 1.1 PerfCounter.dll. Sin embargo, puede indicar a .NET Framework 4 PerfCounter.dll que compruebe la configuración del Registro habilitando el `<forcePerformanceCounterUniqueSharedMemoryReads>` elemento.  
  
> [!NOTE]
> Habilitar `<forcePerformanceCounterUniqueSharedMemoryReads>` el elemento no garantiza que se usará la memoria compartida específica de la categoría. Establecer habilitado `true` solo hace que PerfCounter.dll haga referencia a la configuración del Registro CategoryOptions. La configuración predeterminada para CategoryOptions es usar memoria compartida específica de categoría; sin embargo, puede cambiar CategoryOptions para indicar que se debe usar la memoria compartida global.  
  
 La clave del Registro que contiene la configuración de CategoryOptions se HKEY_LOCAL_MACHINE, System, CurrentControlSet, Services\\<nombredecategoría\>. De forma predeterminada, CategoryOptions se establece en 3, lo que indica a PerfCounter.dll que use memoria compartida específica de la categoría. Si CategoryOptions se establece en 0, PerfCounter.dll utiliza memoria compartida global. Los datos de instancia solo se reutilizarán si el nombre de la instancia que se está creando es idéntico a la instancia que se está reutilizando. Todas las versiones podrán escribir en la categoría. Si CategoryOptions se establece en 1, se utiliza la memoria compartida global, pero los datos de instancia se pueden reutilizar si el nombre de categoría tiene la misma longitud que la categoría que se reutiliza.  
  
 Los ajustes 0 y 1 pueden provocar pérdidas de memoria y el llenado de la memoria del contador de rendimiento.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo especificar que PerfCounter.dll debe hacer referencia a la entrada del Registro CategoryOptions para determinar si debe usar memoria compartida específica de categoría.  
  
```xml  
<configuration>  
  <runtime>  
    <forcePerformanceCounterUniqueSharedMemoryReads enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Consulte también

- [Esquema de la configuración de Common Language Runtime](index.md)
- [Esquema del archivo de configuración](../index.md)
