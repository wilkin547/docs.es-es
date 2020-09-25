---
title: <trace> (Elemento)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace
- http://schemas.microsoft.com/.NetConfiguration/v2.0#trace
helpviewer_keywords:
- <trace> element
- listeners
- trace element
- trace listener, <trace> element
ms.assetid: 7931c942-63c1-47c3-a045-9d9de3cacdbf
ms.openlocfilehash: 617b42a0be2be272a78b33be997cce632d1c6dcb
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91198930"
---
# <a name="trace-element"></a>\<trace> (Elemento)

Contiene agentes de escucha que recopilan, almacenan y enrutan los mensajes de seguimiento.  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<trace>**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<trace autoflush="true|false"
       indentsize="indent value"  
       useGlobalLock="true| false"/>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  

 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`autoflush`|Atributo opcional.<br /><br /> Especifica si los agentes de escucha de seguimiento vacían automáticamente el búfer de salida después de cada operación de escritura.|  
|`indentsize`|Atributo opcional.<br /><br /> Especifica el número de espacios a los que se va a aplicar sangría.|  
|`useGlobalLock`|Atributo opcional.<br /><br /> Indica si se debe usar el bloqueo global.|  
  
## <a name="autoflush-attribute"></a>AutoFlush (atributo)  
  
|Value|Descripción|  
|-----------|-----------------|  
|`false`|No vacía automáticamente el búfer de salida. Este es el valor predeterminado.|  
|`true`|Vacía automáticamente el búfer de salida.|  
  
## <a name="usegloballock-attribute"></a>Atributo useGlobalLock  
  
|Value|Descripción|  
|-----------|-----------------|  
|`false`|No utiliza el bloqueo global si el agente de escucha es seguro para subprocesos; de lo contrario, utiliza el bloqueo global.|  
|`true`|Utiliza el bloqueo global independientemente de si el agente de escucha es seguro para subprocesos. Este es el valor predeterminado.|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<listeners>](listeners-element-for-trace.md)|Especifica un agente de escucha que recopila, almacena y enruta los mensajes.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`system.diagnostics`|Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.|  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se muestra cómo usar el `<trace>` elemento para agregar el agente de escucha `MyListener` a la `Listeners` colección. `MyListener` crea un archivo denominado `MyListener.log` y escribe el resultado en el archivo. El `useGlobalLock` atributo se establece en `false` , lo que hace que no se use el bloqueo global si el agente de escucha de seguimiento es seguro para subprocesos. El `autoflush` atributo se establece en `true` , que hace que el agente de escucha de seguimiento escriba en el archivo independientemente de si <xref:System.Diagnostics.Trace.Flush%2A?displayProperty=nameWithType> se llama al método. El `indentsize` atributo se establece en 0 (cero), lo que hace que el agente de escucha Aplique sangría a cero espacios cuando <xref:System.Diagnostics.Trace.Indent%2A?displayProperty=nameWithType> se llama al método.  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <trace useGlobalLock="false" autoflush="true" indentsize="0">  
         <listeners>  
            <add name="myListener" type="System.Diagnostics.TextWriterTraceListener, system version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" initializeData="c:\myListener.log" />  
         </listeners>  
      </trace>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- [Esquema de la configuración de seguimiento y depuración](index.md)
