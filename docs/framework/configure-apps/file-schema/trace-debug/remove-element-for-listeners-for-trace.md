---
title: <remove>(Elemento <listeners> ) para<trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/remove
helpviewer_keywords:
- remove element
- <remove> element
ms.assetid: 9a5cd1b5-be1a-485f-8f0c-2890ad3ef3e0
ms.openlocfilehash: 0c5c9efb8a22d26ea5d4467f9628af5935d6dbad
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920484"
---
# <a name="remove-element-for-listeners-for-trace"></a>\<quitar > elemento de \<los agentes de escucha \<> para el seguimiento >
Quita un agente de escucha de la colección Listeners.  
  
 \<configuration>  
\<system.diagnostics>  
\<> de seguimiento  
\<listeners>  
\<remove>  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<remove name="listener name" />  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|DESCRIPCIÓN|  
|---------------|-----------------|  
|**name**|Atributo necesario.<br /><br /> Nombre del agente de escucha que se va a quitar de la colección Listeners.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|DESCRIPCIÓN|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`listeners`|Especifica un agente de escucha que recopila, almacena y enruta los mensajes. Los agentes de escucha dirigen los resultados del seguimiento a un destino adecuado.|  
|`system.diagnostics`|Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.|  
|`trace`|Configura el servicio de seguimiento ASP.NET.|  
  
## <a name="remarks"></a>Comentarios  
  
> [!NOTE]
> <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType> <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType> <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> Al quitar delacolecciónsemodificaelcomportamientodelosmétodos,,y.<xref:System.Diagnostics.DefaultTraceListener> `Listeners` La llamada `Assert` a `Fail` un método o suele tener como resultado la presentación de un cuadro de mensaje; sin embargo, el cuadro <xref:System.Diagnostics.DefaultTraceListener> de mensaje no se `Listeners` muestra si no está en la colección.  
  
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
