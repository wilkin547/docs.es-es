---
description: 'Más información sobre: <elemento System. Diagnostics>'
title: <System. Diagnostics (elemento>)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.diagnostics
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics
helpviewer_keywords:
- <system.diagnostics> element
- system.diagnostics element
ms.assetid: 3f348f42-fa72-4ff2-aa1c-bb9eecad4bb2
ms.openlocfilehash: ac5b1feaa6c8e7ab25a5210999040835322ac7a9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99750460"
---
# <a name="systemdiagnostics-element"></a>\<system.diagnostics> (Elemento)

Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;**\<system.diagnostics>**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<system.diagnostics>
</system.diagnostics>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  

 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  

 Ninguno.  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<assert>](assert-element.md)|Especifica si se muestra un cuadro de mensaje cuando se llama al método <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>; también indica el nombre del archivo para el que se van a escribir los mensajes.|  
|[\<performanceCounters>](performancecounters-element.md)|Especifica el tamaño de la memoria global que comparten los contadores de rendimiento.|  
|[\<sharedListeners>](sharedlisteners-element.md)|Contiene los agentes de escucha a los que puede hacer referencia cualquier origen o elemento de seguimiento. Los agentes de escucha identificados como agentes de escucha compartidos se pueden agregar a orígenes o seguimientos por nombre.|  
|[\<sources>](sources-element.md)|Especifica los orígenes de seguimiento que inician los mensajes de seguimiento.|  
|[\<switches>](switches-element.md)|Contiene modificadores de seguimiento y los niveles en los que se establecen los modificadores de seguimiento.|  
|[\<trace>](trace-element.md)|Contiene agentes de escucha que recopilan, almacenan y enrutan los mensajes de seguimiento.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se muestra cómo insertar un modificador de seguimiento y un agente de escucha de seguimiento dentro del **\<system.diagnostics>** elemento. El `General` modificador de seguimiento se establece en el <xref:System.Diagnostics.TraceLevel> nivel. El agente de escucha de seguimiento `myListener` crea un archivo denominado `MyListener.log` y escribe el resultado en el archivo.  
  
> [!NOTE]
> En la versión 2.0 de .NET Framework, puede utilizar texto para especificar el valor de un modificador. Por ejemplo, puede especificar `true` para un <xref:System.Diagnostics.BooleanSwitch> o usar el texto que representa un valor de enumeración como `Error` para <xref:System.Diagnostics.TraceSwitch> . La línea `<add name="myTraceSwitch" value="Error" />` es equivalente a `<add name="myTraceSwitch" value="1" />`.  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <switches>  
         <add name="General" value="4" />  
      </switches>  
      <trace autoflush="true" indentsize="2">  
         <listeners>  
            <add name="myListener" type="System.Diagnostics.TextWriterTraceListener, System, Version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" initializeData="MyListener.log" traceOutputOptions="ProcessId, LogicalOperationStack, Timestamp, ThreadId, Callstack, DateTime" />  
         </listeners>  
      </trace>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a>Vea también

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- [Esquema de configuración de seguimiento y depuración](index.md)
