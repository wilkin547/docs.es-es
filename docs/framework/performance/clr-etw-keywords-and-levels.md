---
title: Palabras clave y niveles ETW de CLR
ms.date: 03/30/2017
helpviewer_keywords:
- CLR ETW keywords
- CLR ETW levels
- ETW, CLR keywords
- ETW, CLR levels
ms.assetid: fdf5856d-516b-4042-849d-911c4518a6cb
ms.openlocfilehash: 929ed00c44b52dd94fc9d15e564cce7eeff1619e
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75716190"
---
# <a name="clr-etw-keywords-and-levels"></a>Palabras clave y niveles ETW de CLR
El Seguimiento de eventos para Windows (ETW) se puede filtrar por categoría y nivel. Las [Palabras clave ETW de CLR](#clr-etw-keywords) de evento permiten el filtrado de eventos por categoría; se usan en combinaciones para los proveedores de tiempo de ejecución y detención. Los [niveles de evento](#etw-event-levels) se identifican mediante marcas.  
  
## <a name="clr-etw-keywords"></a>Palabras clave ETW de CLR  
 Las palabras clave son marcas que se pueden combinar para generar valores. En la práctica, cuando se llama a las utilidades de línea de comandos, se usan los valores hexadecimales de las palabras clave en lugar de los nombres de palabra clave.  
  
 Las palabras clave se describen en la tabla siguiente.  
  
- [Palabras clave de runtime de ETW de CLR](#runtime)  
  
- [Palabras clave de detención de ETW de CLR](#rundown)  
  
- [Combinaciones de palabras clave para la resolución de símbolos para el proveedor de runtime](#runtime_combo)  
  
- [Combinaciones de palabras clave para la resolución de símbolos para el proveedor de detención](#rundown_combo)  
  
<a name="runtime"></a>   
### <a name="clr-etw-runtime-keywords"></a>Palabras clave de runtime de ETW de CLR  
 En la tabla siguiente se enumeran las palabras clave de runtime de ETW de CLR, sus valores y se explica para qué se usan.  
  
|Nombre de la palabra clave de runtime|{2&gt;Value&lt;2}|Finalidad|  
|--------------------------|-----------|-------------|  
|`GCKeyword`|0x00000001|Habilita la recopilación de [eventos de recolección de elementos no utilizados](garbage-collection-etw-events.md).|  
|`LoaderKeyword`|0x00000008|Habilita la recopilación de [eventos de cargador](loader-etw-events.md).|  
|`JITKeyword`|0x00000010|Habilita la recopilación de [eventos Just-In-Time (JIT)](jit-tracing-etw-events.md).|  
|`NGenKeyword`|0x00000020|Habilita la recopilación de eventos para los métodos de imágenes nativas (métodos procesados por el generador de imágenes nativas, Ngen.exe); se usa con `StartEnumerationKeyword` y `EndEnumerationKeyword`. Esta palabra clave tiene una gran sobrecarga. Genera eventos para todos los métodos que se encuentran en los módulos cargados de NGen. Siempre que sea posible, en lugar de usar esta palabra clave, le recomendamos que use las bases de datos de programa (PDB) generadas por herramientas de generación de perfiles para recuperar información acerca de los métodos de los módulos NGen. Vea también `OverrideAndSuppressNGenEventsKeyword` más adelante en esta tabla.|  
|`StartEnumerationKeyword`|0x00000040|Habilita la enumeración de todos los métodos en runtime; se usa junto con `NGenKeyword`.|  
|`EndEnumerationKeyword`|0x00000080|Habilita la enumeración de todos los métodos destruidos en runtime; se usa junto con `JITKeyword` y `NGenKeyword`.|  
|`SecurityKeyword`|0x00000400|Habilita la recopilación de [eventos de seguridad](security-etw-events.md).|  
|`AppDomainResourceManagementKeyword`|0x00000800|Habilita la recopilación de eventos de supervisión de recursos en un nivel de dominio de aplicación.|  
|`JITTracingKeyword`|0x00001000|Habilita la recopilación de [eventos de seguimiento JIT](jit-tracing-etw-events.md).|  
|`InteropKeyword`|0x00002000|Habilita la recopilación de [eventos de interoperabilidad](interop-etw-events.md).|  
|`ContentionKeyword`|0x00004000|Habilita la recopilación de [eventos de contención](contention-etw-events.md).|  
|`ExceptionKeyword`|0x00008000|Habilita la recopilación de [eventos de excepción](exception-thrown-v1-etw-event.md).|  
|`ThreadingKeyword`|0x00010000|Habilita la recopilación de [eventos de grupo de subprocesos](thread-pool-etw-events.md).|  
|`OverrideAndSuppressNGenEventsKeyword`|0x00040000|(Disponible en el .NET Framework 4,5 y versiones posteriores). Suprime la palabra clave de `NGenKeyword` de sobrecarga alta y evita la generación de eventos para los métodos que están dentro de los módulos NGen. A partir del .NET Framework 4,5, las herramientas de generación de perfiles deben usar `OverrideAndSuppressNGenEventsKeyword` y `NGenKeyword` juntas para suprimir la generación de eventos para los métodos de los módulos NGen. Esto permite que la herramienta de generación de perfiles use de forma más eficaz los archivos PDB de NGen para obtener información sobre los métodos de módulos NGen. En .NET Framework 4 y versiones anteriores, el CLR no admite la creación de archivos PDB de NGen. En estas versiones anteriores, el CLR no reconocerá `OverrideAndSuppressNGenEventsKeyword` y procesará `NGenKeyword` para generar eventos para los métodos de módulos NGen.|  
|`PerfTrackKeyWord`|0x2000000|Habilita la recopilación de eventos `ModuleLoad` y `ModuleRange` .|  
|`StackKeyword`|0x40000000|Habilita la recopilación de [eventos de seguimiento de pila](stack-etw-event.md)de CLR.|  
  
<a name="rundown"></a>   
### <a name="clr-etw-rundown-keywords"></a>Palabras clave de detención de ETW de CLR  
 En la tabla siguiente se enumeran las palabras clave de detención de ETW de CLR, sus valores y se explica para qué se usan.  
  
|Nombre de la palabra clave de detención|{2&gt;Value&lt;2}|Finalidad|  
|--------------------------|-----------|-------------|  
|`LoaderRundownKeyword`|0x00000008|Habilita la recopilación de eventos de cargador cuando se usa con `StartRundownKeyword` y `EndRundownKeyword`.|  
|`JitRundownKeyword`|0x00000010|Habilita la recopilación de eventos de método `DCStart` y `DCEnd` para métodos compilados JIT cuando se usa con `StartRundownKeyword` y `EndRundownKeyword`.|  
|`NGenRundownKeyword`|0x00000020|Habilita la recopilación de eventos de método `DCStart` y `DCEnd` para métodos de imágenes nativas de NGen cuando se usa con `StartRundownKeyword` y `EndRundownKeyword`. Esta palabra clave tiene una gran sobrecarga. Genera eventos para todos los métodos que se encuentran en los módulos cargados de NGen. Siempre que sea posible, en lugar de usar esta palabra clave, le recomendamos que use las bases de datos de programa (PDB) generadas por herramientas de generación de perfiles para recuperar información acerca de los métodos de los módulos NGen. Vea también `OverrideAndSuppressNGenEventsRundownKeyword` más adelante en esta tabla.|  
|`StartRundownKeyword`|0x00000040|Habilita la enumeración del estado del sistema durante una detención de inicio.|  
|`EndRundownKeyword`|0x00000100|Habilita la enumeración del estado del sistema durante una detención de final.|  
|`AppDomainResourceManagementRundownKeyword`|0x00000800|Habilita la recopilación de eventos de supervisión de recursos en un nivel de <xref:System.AppDomain> cuando se usa con `StartRundownKeyword` o `EndRundownKeyword`.|  
|`ThreadingKeyword`|0x00010000|Habilita la recopilación de eventos de grupo de subprocesos.|  
|`OverrideAndSuppressNGenEventsRundownKeyword`|0x00040000|(Disponible en el .NET Framework 4,5 y versiones posteriores). Suprime la palabra clave de `NGenRundownKeyword` de sobrecarga alta y evita la generación de eventos para los métodos que están dentro de los módulos NGen. A partir del .NET Framework 4,5, las herramientas de generación de perfiles deben usar `OverrideAndSuppressNGenEventsRundownKeyword` y `NGenRundownKeyword` juntas para suprimir la generación de eventos para los métodos de los módulos NGen. Esto permite que la herramienta de generación de perfiles use de forma más eficaz los archivos PDB de NGen para obtener información sobre los métodos de módulos NGen. En .NET Framework 4 y versiones anteriores, el CLR no admite la creación de archivos PDB de NGen. En estas versiones anteriores, el CLR no reconocerá `OverrideAndSuppressNGenEventsRundownKeyword` y procesará `NGenRundownKeyword` para generar eventos para los métodos de módulos NGen.|  
|`PerfTrackKeyWord`|0x2000000|Habilita la recopilación de eventos `ModuleDCStart`, `ModuleDCEnd`, `ModuleRangeDCStart`y `ModuleRangeDCEnd` .|   
  
<a name="runtime_combo"></a>   
### <a name="keyword-combinations-for-symbol-resolution-for-the-runtime-provider"></a>Combinaciones de palabras clave para la resolución de símbolos para el proveedor de runtime  
  
|Palabras clave y marcas|Dominio de aplicación, ensamblado, eventos de carga/descarga de módulos|Eventos de carga/descarga de método (excepto eventos dinámicos)|Eventos de carga/destrucción de métodos dinámicos|  
|------------------------|--------------------------------------------------------------|----------------------------------------------------------|-----------------------------------------|  
|`LoaderKeyword`|Eventos de carga y descarga.|Ninguna.|Ninguna.|  
|`JITKeyword`<br /><br /> (+ `StartEnumerationKeyword` no agrega nada)|Ninguna.|Eventos de carga.|Eventos de carga y descarga.|  
|`JITKeyword` +<br /><br /> `EndEnumerationKeyword`|Ninguna.|Eventos de carga y descarga.|Eventos de carga y descarga.|  
|`NGenKeyword`|Ninguna.|Ninguna.|No es aplicable.|  
|`NGenKeyword` +<br /><br /> `StartEnumerationKeyword`|Ninguna.|Eventos de carga.|No es aplicable.|  
|`NGenKeyword` +<br /><br /> `EndEnumerationKeyword`|Ninguna.|Eventos de descarga.|No es aplicable.|  
  
<a name="rundown_combo"></a>   
### <a name="keyword-combinations-for-symbol-resolution-for-the-rundown-provider"></a>Combinaciones de palabras clave para la resolución de símbolos para el proveedor de detención  
  
|Palabras clave y marcas|Dominio de aplicación, ensamblado, eventos DCStart/DCEnd de módulos|Eventos DCStart/DCEnd de método (incluidos los eventos de métodos dinámicos)|  
|------------------------|----------------------------------------------------------------|----------------------------------------------------------------------|  
|`LoaderRundownKeyword` +<br /><br /> `StartRundownKeyword`|Eventos`DCStart` .|Ninguna.|  
|`LoaderRundownKeyword` +<br /><br /> `EndRundownKeyword`|Eventos`DCEnd` .|Ninguna.|  
|`JITKeyword` +<br /><br /> `StartRundownKeyword`|Ninguna.|Eventos`DCStart` .|  
|`JITKeyword` +<br /><br /> `EndRundownKeyword`|Ninguna.|Eventos`DCEnd` .|  
|`NGenKeyword` +<br /><br /> `StartRundownKeyword`|Ninguna.|Eventos`DCStart` .|  
|`NGenKeyword` +<br /><br /> `EndRundownKeyword`|Ninguna.|Eventos`DCEnd` .|  

## <a name="etw-event-levels"></a>Niveles de eventos ETW  
 Los eventos ETW también se pueden filtrar por nivel. Si el nivel se establece en 0x5, se generan eventos de todos los niveles, incluidos 0 x 5 e inferiores (que son eventos que pertenecen a las categorías habilitadas mediante palabras clave). Si el nivel se establece en 0x2, tan solo se producen los eventos que pertenecen al nivel 0x2 e inferiores.  
  
 Los niveles tienen los significados siguientes:  
  
 0x5: Verbose  
  
 0x4: Informativo  
  
 0x3: Advertencia  
  
 0x2: Error  
  
 0x1: Crítico  
  
 0x0: LogAlways  
  
## <a name="see-also"></a>Vea también

- [Proveedores ETW de CLR](clr-etw-providers.md)
- [CLR ETW Events (Eventos ETW de CLR)](clr-etw-events.md)
- [Eventos ETW en Common Language Runtime](etw-events-in-the-common-language-runtime.md)
