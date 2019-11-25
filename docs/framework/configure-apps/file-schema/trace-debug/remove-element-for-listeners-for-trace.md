---
title: <remove> elemento de <listeners> para <trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/remove
helpviewer_keywords:
- remove element
- <remove> element
ms.assetid: 9a5cd1b5-be1a-485f-8f0c-2890ad3ef3e0
ms.openlocfilehash: f06973ec30d5061e4a200d6bf7e68adcf6302018
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088846"
---
# <a name="remove-element-for-listeners-for-trace"></a>\<quitar > elemento para \<agentes de escucha > para \<> de seguimiento
Quita un agente de escucha de la colección **Listeners** .  

[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. diagnostics >** ](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<** ](trace-element.md) > de seguimiento\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**agentes de escucha**](listeners-element-for-trace.md) >\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**quitar >**

## <a name="syntax"></a>Sintaxis  
  
```xml  
<remove name="listener name" />  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|**name**|Atributo necesario.<br /><br /> Nombre del agente de escucha que se va a quitar de la colección **Listeners** .|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`listeners`|Especifica un agente de escucha que recopila, almacena y enruta los mensajes. Los agentes de escucha dirigen los resultados del seguimiento a un destino adecuado.|  
|`system.diagnostics`|Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.|  
|`trace`|Configura el servicio de seguimiento ASP.NET.|  
  
## <a name="remarks"></a>Comentarios  
  
> [!NOTE]
> Al quitar el <xref:System.Diagnostics.DefaultTraceListener> de la colección `Listeners` se modifica el comportamiento de los métodos <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>y <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType>. La llamada a un método `Assert` o `Fail` suele tener como resultado la presentación de un cuadro de mensaje; sin embargo, el cuadro de mensaje no se muestra si el <xref:System.Diagnostics.DefaultTraceListener> no está en la colección de `Listeners`.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo quitar el agente de escucha de seguimiento predeterminado de la colección de **agentes de escucha** de seguimiento.  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <trace autoflush="true" indentsize="0">  
         <listeners>  
            <remove name="Default" />  
         </listeners>  
      </trace>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a>Vea también

- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- [Esquema de la configuración de seguimiento y depuración](index.md)
