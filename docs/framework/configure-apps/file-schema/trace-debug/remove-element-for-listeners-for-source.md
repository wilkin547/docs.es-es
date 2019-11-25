---
title: <remove> elemento de <listeners> para <source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/remove
helpviewer_keywords:
- remove element for <listeners> for <source>
- <remove> element for <listeners> for <source>
ms.assetid: 3ff6b578-273d-407f-b07f-8251f1f9f5d0
ms.openlocfilehash: 75db45d4e868ce88e030ec6a43c8bdaf788a1102
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088855"
---
# <a name="remove-element-for-listeners-for-source"></a>\<quitar > elemento para \<agentes de escucha > para \<origen >
Quita un agente de escucha de la colección `Listeners` para un origen de seguimiento.  

[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. diagnostics >** ](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<orígenes**](sources-element.md) >\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**origen**](source-element.md) >\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**agentes de escucha**](listeners-element-for-source.md) >\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**quitar >**

## <a name="syntax"></a>Sintaxis  
  
```xml  
<remove name="listenerName" />  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`name`|Atributo necesario.<br /><br /> Nombre del agente de escucha que se va a quitar de la colección de `Listeners`.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`system.diagnostics`|Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.|  
|`sources`|Contiene orígenes de seguimiento que inician mensajes de seguimiento.|  
|`source`|Contiene un origen de seguimiento que inicia mensajes de seguimiento.|  
|`listeners`|Especifica los agentes de escucha que recopilan, almacenan y enrutan los mensajes.|  
  
## <a name="remarks"></a>Comentarios  
 El elemento `<remove>` quita un agente de escucha especificado de la colección de `Listeners` para un origen de seguimiento.  
  
 Puede quitar un elemento de la colección de `Listeners` para un origen de seguimiento mediante programación llamando al método <xref:System.Diagnostics.TraceListenerCollection.Remove%2A> en la propiedad <xref:System.Diagnostics.TraceSource.Listeners%2A> de la instancia de <xref:System.Diagnostics.TraceSource>.  
  
 Este elemento se puede usar en el archivo de configuración del equipo (Machine. config) y en el archivo de configuración de la aplicación.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo utilizar el elemento `<remove>` antes de utilizar el elemento `<add>` para agregar el agente de escucha `console` a la colección de `Listeners` para la `TraceSourceApp`de origen de seguimiento.  
  
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
