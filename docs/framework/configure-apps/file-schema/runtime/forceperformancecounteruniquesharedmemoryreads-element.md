---
title: <forcePerformanceCounterUniqueSharedMemoryReads> (Elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- forcePerformanceCounterUniqueSharedMemoryReads element
- <forcePerformanceCounterUniqueSharedMemoryReads> element
ms.assetid: 91149858-4810-4f65-9b48-468488172c9b
ms.openlocfilehash: 742b444c445ba67d6977b622e615a6a8f591826e
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154145"
---
# <a name="forceperformancecounteruniquesharedmemoryreads-element"></a>\<forcePerformanceCounterUniqueSharedMemoryReads> (Elemento)
Especifica si PerfCounter.dll usa la configuración del Registro CategoryOptions en una aplicación de .NET Framework 1.1 para determinar si se van a cargar los datos del contador de rendimiento desde la memoria compartida específica de la categoría o la memoria global.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
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
|`enabled`|Atributo necesario.<br /><br /> Indica si PerfCounter. dll usa la configuración del Registro CategoryOptions para determinar si se van a cargar los datos del contador de rendimiento de la memoria compartida específica de la categoría o de la memoria global.|  
  
## <a name="enabled-attribute"></a>Atributo enabled  
  
|Value|Descripción|  
|-----------|-----------------|  
|`false`|PerfCounter. dll no utiliza la configuración del registro de CategoryOptions es el valor predeterminado.|  
|`true`|PerfCounter. dll usa la configuración del Registro CategoryOptions.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.|  
  
## <a name="remarks"></a>Comentarios  
 En las versiones de la .NET Framework antes del .NET Framework 4, la versión de PerfCounter. dll que se cargó correspondía al tiempo de ejecución que se cargó en el proceso. Si un equipo tenía la .NET Framework la versión 1,1 y el .NET Framework 2,0 instalado, una aplicación .NET Framework 1,1 cargaría la versión .NET Framework 1,1 de PerfCounter. dll. A partir de la .NET Framework 4, se carga la versión más reciente instalada de PerfCounter. dll. Esto significa que una aplicación .NET Framework 1,1 cargará la versión .NET Framework 4 de PerfCounter. dll si el .NET Framework 4 está instalado en el equipo.  
  
 A partir de la .NET Framework 4, cuando se usan contadores de rendimiento, PerfCounter. dll comprueba la entrada del registro de CategoryOptions para cada proveedor para determinar si debe leer la memoria compartida específica de la categoría o la memoria compartida global. La .NET Framework 1,1 PerfCounter. dll no lee la entrada del registro, ya que no es consciente de la memoria compartida específica de la categoría. siempre lee de la memoria compartida global.  
  
 Por compatibilidad con versiones anteriores, el .NET Framework 4 PerfCounter. dll no comprueba la entrada del registro de CategoryOptions cuando se ejecuta en una aplicación .NET Framework 1,1. Simplemente usa la memoria compartida global, como la .NET Framework 1,1 PerfCounter. dll. Sin embargo, puede indicar al .NET Framework 4 PerfCounter. dll que Compruebe la configuración del registro habilitando el `<forcePerformanceCounterUniqueSharedMemoryReads>` elemento.  
  
> [!NOTE]
> Al habilitar el elemento no se `<forcePerformanceCounterUniqueSharedMemoryReads>` garantiza que se utilice la memoria compartida específica de la categoría. Si se establece en habilitado `true` , PerfCounter. dll hará referencia a la configuración del Registro CategoryOptions. La configuración predeterminada de CategoryOptions es usar la memoria compartida específica de la categoría. sin embargo, puede cambiar CategoryOptions para indicar que se debe usar la memoria compartida global.  
  
 La clave del registro que contiene el valor de CategoryOptions es HKEY_LOCAL_MACHINE \System\CurrentControlSet\Services \\<categoryName \> \Performance. De forma predeterminada, CategoryOptions se establece en 3, lo que indica a PerfCounter. dll que use la memoria compartida específica de la categoría. Si CategoryOptions se establece en 0, PerfCounter. dll utiliza la memoria compartida global. Los datos de instancia se reutilizarán solo si el nombre de la instancia que se va a crear es idéntico a la instancia que se va a reutilizar. Todas las versiones podrán escribir en la categoría. Si CategoryOptions está establecido en 1, se usa la memoria compartida global, pero se pueden volver a usar los datos de instancia si el nombre de la categoría tiene la misma longitud que la categoría que se va a reutilizar.  
  
 Los valores 0 y 1 pueden dar lugar a pérdidas de memoria y al rellenar la memoria del contador de rendimiento.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo especificar que PerfCounter. dll debe hacer referencia a la entrada del Registro CategoryOptions para determinar si debe usar la memoria compartida específica de la categoría.  
  
```xml  
<configuration>  
  <runtime>  
    <forcePerformanceCounterUniqueSharedMemoryReads enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Consulte también

- [Esquema de la configuración de Common Language Runtime](index.md)
- [Esquema de los archivos de configuración](../index.md)
