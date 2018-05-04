---
title: '&lt;seguimiento&gt; elemento'
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
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 59d5083632630513d2afc1f8d78400310451e46f
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="lttracegt-element"></a>&lt;seguimiento&gt; elemento
Contiene agentes de escucha que recopilan, almacenan y enrutan los mensajes de seguimiento.  
  
 \<configuration>  
\<System.Diagnostics >  
\<seguimiento >  
  
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
|`autoflush`|Atributo opcional.<br /><br /> Especifica si los agentes de escucha de seguimiento vacían automáticamente o el búfer de salida después de cada operación de escritura.|  
|`indentsize`|Atributo opcional.<br /><br /> Especifica el número de espacios para la sangría.|  
|`useGlobalLock`|Atributo opcional.<br /><br /> Indica si se debe utilizar el bloqueo global.|  
  
## <a name="autoflush-attribute"></a>Atributo autoflush  
  
|Valor|Descripción|  
|-----------|-----------------|  
|`false`|No se vacíe automáticamente el búfer de salida. Este es el valor predeterminado.|  
|`true`|Automáticamente se vacía el búfer de salida.|  
  
## <a name="usegloballock-attribute"></a>Atributo useGlobalLock  
  
|Valor|Descripción|  
|-----------|-----------------|  
|`false`|No utiliza el bloqueo global si el agente de escucha es seguro para subprocesos; en caso contrario, utiliza el bloqueo global.|  
|`true`|Utiliza el bloqueo global independientemente de si el agente de escucha es seguro para subprocesos. Este es el valor predeterminado.|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<listeners>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/listeners-element-for-trace.md)|Especifica un agente de escucha que recopila, almacena y enruta los mensajes.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`system.diagnostics`|Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.|  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo utilizar el `<trace>` elemento que se va a agregar el agente de escucha `MyListener` a la `Listeners` colección. `MyListener` crea un archivo que se denomina `MyListener.log` y escribe el resultado en el archivo. El `useGlobalLock` atributo está establecido en `false`, lo que hace que el bloqueo global no que se utilizará si el agente de escucha de seguimiento es seguro para subprocesos. El `autoflush` atributo está establecido en `true`, lo que hace que el agente de escucha de seguimiento escribir en el archivo independientemente de si el <xref:System.Diagnostics.Trace.Flush%2A?displayProperty=nameWithType> se llama al método. El `indentsize` atributo está establecido en 0 (cero), lo que hace que el agente de escucha sangre cero espacios cuando el <xref:System.Diagnostics.Trace.Indent%2A?displayProperty=nameWithType> se llama al método.  
  
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
  
## <a name="see-also"></a>Vea también  
 <xref:System.Diagnostics.TraceListener>  
 <xref:System.Diagnostics.DefaultTraceListener>  
 <xref:System.Diagnostics.TextWriterTraceListener>  
 <xref:System.Diagnostics.EventLogTraceListener>  
 [Esquema de la configuración de seguimiento y depuración](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
