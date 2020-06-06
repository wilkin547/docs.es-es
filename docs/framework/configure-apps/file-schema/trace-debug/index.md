---
title: Esquema de la configuración de seguimiento y depuración
ms.date: 03/30/2017
helpviewer_keywords:
- tracing [.NET Framework], trace and debug settings schema
- configuration schema [.NET Framework], trace and debug settings
- configuration settings [.NET Framework], tracing
- schema configuration settings
- configuration settings [.NET Framework], debugging
- trace listeners, trace and debug settings schema
- configuration sections [.NET Framework]
- elements [.NET Framework], trace and debug settings
ms.assetid: 277ca5f6-e1c4-41b6-a47f-3a67ce5b94ac
ms.openlocfilehash: 037d08b33e9aa6a64d236b36ebcf821b604b03df
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "69927117"
---
# <a name="trace-and-debug-settings-schema"></a>Esquema de la configuración de seguimiento y depuración
La configuración de seguimiento y depuración especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.  
  
 En la tabla siguiente se describe la función de cada elemento de configuración de seguimiento y depuración.  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<add>](add-element-for-listeners-for-source.md)|Agrega un agente de escucha a la colección `Listeners` para un origen de seguimiento.|  
|[\<add>](add-element-for-listeners-for-trace.md)|Agrega un agente de escucha a la colección `Listeners`.|  
|[\<add>](add-element-for-sharedlisteners.md)|Agrega un agente de escucha a la colección `sharedListeners`.|  
|[\<add>](add-element-for-switches.md)|Especifica el nivel en el que está establecido un modificador de seguimiento.|  
|[\<assert>](assert-element.md)|Especifica si se muestra un cuadro de mensaje cuando se llama al método <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>; también indica el nombre del archivo para el que se van a escribir los mensajes.|  
|[\<clear>](clear-element-for-listeners-for-source.md)|Borra la colección `Listeners` de un origen de seguimiento.|  
|[\<clear>](clear-element-for-listeners-for-trace.md)|Borra la colección `Listeners` de un seguimiento.|  
|[\<filter>](filter-element-for-add-for-listeners-for-source.md)|Agrega un filtro a un agente de escucha en la colección `Listeners` para un origen de seguimiento.|  
|[\<filter>](filter-element-for-add-for-listeners-for-trace.md)|Agrega un filtro a un agente de escucha en la colección `Listeners` para el seguimiento.|  
|[\<filter>](filter-element-for-add-for-sharedlisteners.md)|Agrega un filtro a un agente de escucha en la colección `sharedListeners`.|  
|[\<listeners>](listeners-element-for-source.md)|Especifica agentes de escucha para la colección `Listeners` para un origen de seguimiento.|  
|[\<listeners>](listeners-element-for-trace.md)|Especifica agentes de escucha para la colección `Listeners` para el seguimiento.|  
|[\<performanceCounters>](performancecounters-element.md)|Especifica el tamaño de la memoria global que comparten los contadores de rendimiento.|  
|[\<remove>](remove-element-for-listeners-for-trace.md)|Quita un agente de escucha de la colección `Listeners` para el seguimiento.|  
|[\<remove>](remove-element-for-listeners-for-source.md)|Quita un agente de escucha de la colección `Listeners` para un origen de seguimiento.|  
|[\<sharedListeners>](sharedlisteners-element.md)|Contiene los agentes de escucha a los que puede hacer referencia cualquier origen o elemento de seguimiento.|  
|[\<sources>](sources-element.md)|Contiene orígenes de seguimiento que inician mensajes de seguimiento.|  
|[\<source>](source-element.md)|Contiene un origen de seguimiento que inicia mensajes de seguimiento.|  
|[\<switches>](switches-element.md)|Contiene modificadores de seguimiento y el nivel en el que están establecidos.|  
|[\<system.diagnostics>](system-diagnostics-element.md)|Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.|  
|[\<trace>](trace-element.md)|Contiene agentes de escucha que recopilan, almacenan y enrutan los mensajes de seguimiento.|  
  
## <a name="see-also"></a>Vea también

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.Debug>
- [Esquema de los archivos de configuración](../index.md)
