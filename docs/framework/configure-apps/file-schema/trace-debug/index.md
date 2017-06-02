---
title: "Esquema de la configuraci&#243;n de seguimiento y depuraci&#243;n | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
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
  - "esquema de configuración [.NET Framework], configuración de seguimiento y depuración"
  - "secciones de configuración [.NET Framework]"
  - "valores de configuración [.NET Framework], depurar"
  - "valores de configuración [.NET Framework], traza"
  - "elementos [.NET Framework], configuración de seguimiento y depuración"
  - "valores de configuración del esquema"
  - "agentes de escucha de seguimiento, esquema de la configuración de seguimiento y depuración"
  - "seguimiento [.NET Framework], esquema de la configuración de seguimiento y depuración"
ms.assetid: 277ca5f6-e1c4-41b6-a47f-3a67ce5b94ac
caps.latest.revision: 14
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 14
---
# Esquema de la configuraci&#243;n de seguimiento y depuraci&#243;n
La configuración de traza y depuración especifica los agentes de escucha de traza que recopilan, almacenan y enrutan mensajes, y el nivel donde se establece un modificador de traza.  
  
 En la siguiente tabla se describe la función de cada elemento de la configuración de traza y depuración.  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<add\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-listeners-for-source.md)|Agrega un agente de escucha a la colección `Listeners` de un origen de traza.|  
|[\<add\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-listeners-for-trace.md)|Agrega un agente de escucha a la colección `Listeners`.|  
|[\<add\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-sharedlisteners.md)|Agrega un agente de escucha a la colección `sharedListeners`.|  
|[\<add\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-switches.md)|Especifica el nivel donde se establece un modificador de seguimiento.|  
|[\<assert\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/assert-element.md)|Especifica si aparecerá o no un cuadro de mensaje al llamar al método <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=fullName>; también especifica el nombre del archivo donde se escriben los mensajes.|  
|[\<clear\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/clear-element-for-listeners-for-source.md)|Borra la colección `Listeners` para un origen de traza.|  
|[\<clear\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/clear-element-for-listeners-for-trace.md)|Borra la colección `Listeners` para traza.|  
|[\<filter\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/filter-element-for-add-for-listeners-for-source.md)|Agrega un filtro a un agente de escucha de la colección `Listeners` para un origen de traza.|  
|[\<filter\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/filter-element-for-add-for-listeners-for-trace.md)|Agrega un filtro a un agente de escucha de la colección `Listeners` para traza.|  
|[\<filter\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/filter-element-for-add-for-sharedlisteners.md)|Agrega un filtro a un agente de escucha contenido en la colección `sharedListeners`.|  
|[\<listeners\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/listeners-element-for-source.md)|Especifica los agentes de escucha de la colección `Listeners` para un origen de traza.|  
|[\<listeners\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/listeners-element-for-trace.md)|Especifica los agentes de escucha de la colección `Listeners` para traza.|  
|[\<performanceCounters\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/performancecounters-element.md)|Especifica el tamaño de la memoria global compartida por los contadores de rendimiento.|  
|[\<remove\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/remove-element-for-listeners-for-trace.md)|Quita un agente de escucha de la colección `Listeners` para traza.|  
|[\<remove\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/remove-element-for-listeners-for-source.md)|Quita un agente de escucha de la colección `Listeners` para un origen de traza.|  
|[\<sharedListeners\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md)|Contiene agentes de escucha a los que puede hacer referencia cualquier origen o elemento de traza.|  
|[\<sources\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sources-element.md)|Contiene orígenes de traza que inician mensajes de traza.|  
|[\<source\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/source-element.md)|Especifica un origen de traza que inicia mensajes de traza.|  
|[\<switches\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/switches-element.md)|Contiene modificadores de seguimiento y el nivel donde éstos se establecen.|  
|[\<system.diagnostics\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/system-diagnostics-element.md)|Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, y el nivel donde se establece un modificador de seguimiento.|  
|[\<trace\>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/trace-element.md)|Contiene agentes de escucha que recopilan, almacenan y enrutan mensajes de traza.|  
  
## Vea también  
 <xref:System.Diagnostics.Trace>   
 <xref:System.Diagnostics.TraceSource>   
 <xref:System.Diagnostics.Debug>   
 [Esquema de los archivos de configuración](../../../../../docs/framework/configure-apps/file-schema/index.md)