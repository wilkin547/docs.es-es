---
title: <remove>(Elemento <listeners> ) para<source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/remove
helpviewer_keywords:
- remove element for <listeners> for <source>
- <remove> element for <listeners> for <source>
ms.assetid: 3ff6b578-273d-407f-b07f-8251f1f9f5d0
ms.openlocfilehash: edd27dd262004aead7db4d81db8ecab0e831dac1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926990"
---
# <a name="remove-element-for-listeners-for-source"></a>\<quitar > elemento de \<los agentes de escucha \<> para el origen >
Quita un agente de escucha de la colección `Listeners` para un origen de seguimiento.  
  
 \<configuration>  
\<system.diagnostics>  
\<orígenes >  
\<> de origen  
\<listeners>  
\<remove>  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<remove name="listenerName" />  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|DESCRIPCIÓN|  
|---------------|-----------------|  
|`name`|Atributo necesario.<br /><br /> Nombre del agente de escucha que se va a quitar `Listeners` de la colección.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|DESCRIPCIÓN|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`system.diagnostics`|Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.|  
|`sources`|Contiene orígenes de seguimiento que inician mensajes de seguimiento.|  
|`source`|Contiene un origen de seguimiento que inicia mensajes de seguimiento.|  
|`listeners`|Especifica los agentes de escucha que recopilan, almacenan y enrutan los mensajes.|  
  
## <a name="remarks"></a>Comentarios  
 El `<remove>` elemento quita un agente de escucha especificado de `Listeners` la colección para un origen de seguimiento.  
  
 Puede quitar un elemento de `Listeners` la colección para un origen de seguimiento mediante programación llamando al <xref:System.Diagnostics.TraceListenerCollection.Remove%2A> método en la <xref:System.Diagnostics.TraceSource.Listeners%2A> propiedad de la <xref:System.Diagnostics.TraceSource> instancia.  
  
 Este elemento se puede usar en el archivo de configuración del equipo (Machine. config) y en el archivo de configuración de la aplicación.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo utilizar `<remove>` el elemento antes de `<add>` usar el elemento `console` para agregar el agente de `Listeners` escucha a la colección para `TraceSourceApp`el origen de seguimiento.  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="TraceSourceApp" switchName="sourceSwitch"   
         switchType="System.Diagnostics.SourceSwitch" >  
         <listeners>  
           <remove name="Default"/>  
           <add name="console"   
             type="System.Diagnostics.ConsoleTraceListener" />  
         </listeners>  
      </source>  
    </sources>  
  </system.diagnostics>  
</configuration>   
```  
  
## <a name="see-also"></a>Vea también

- <xref:System.Diagnostics.TraceSource.Listeners%2A>
- <xref:System.Diagnostics.TraceSource>
- [Esquema de la configuración de seguimiento y depuración](index.md)
- [\<clear>](clear-element-for-listeners-for-source.md)
- [Agentes de escucha de seguimiento](../../../debug-trace-profile/trace-listeners.md)
