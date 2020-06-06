---
title: <sharedListeners> (Elemento)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#sharedListeners
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sharedListeners
helpviewer_keywords:
- <sharedListeners> element
- listeners
- shared listeners
- trace listeners, <sharedListeners> element
- sharedListeners element
ms.assetid: de200534-19dd-4156-86cf-c50521802c4c
ms.openlocfilehash: 69f15cc9583b397017ac30a0c567914495867c18
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153326"
---
# <a name="sharedlisteners-element"></a>\<sharedListeners> (Elemento)
Contiene los agentes de escucha a los que puede hacer referencia cualquier origen o elemento de seguimiento.  Estos agentes de escucha no reciben ningún seguimiento de forma predeterminada y no es posible recuperar estos agentes de escucha en tiempo de ejecución. Los agentes de escucha identificados como agentes de escucha compartidos se pueden agregar a orígenes o seguimientos por nombre.  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<sharedListeners>**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<sharedListeners>
  <add>...</add>  
</sharedListeners>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
 Ninguno.  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<add>](add-element-for-listeners-for-trace.md)|Agrega un agente de escucha a la colección `sharedListeners`.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`Configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`system.diagnostics`|Especifica el elemento raíz de la sección de configuración de ASP.NET.|  
  
## <a name="remarks"></a>Comentarios  
 Agregar un agente de escucha a la colección de agentes de escucha compartidos no lo convierte en un agente de escucha activo. Todavía se debe agregar a un origen de seguimiento o a un seguimiento agregándolo a la `Listeners` colección para ese elemento Trace. Las clases de agente de escucha del .NET Framework derivan de la <xref:System.Diagnostics.TraceListener> clase.  
  
 Este elemento se puede usar en el archivo de configuración del equipo (Machine. config) y en el archivo de configuración de la aplicación.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo usar el `<sharedListeners>` elemento para agregar el agente `console` de escucha a la `Listeners` colección para <xref:System.Diagnostics.TraceSource> las <xref:System.Diagnostics.Trace> clases y. El agente de escucha de seguimiento de la consola escribe información de seguimiento en la consola a través de llamadas a <xref:System.Diagnostics.TraceSource> o <xref:System.Diagnostics.Trace> .  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sharedListeners>  
      <add name="console" type="System.Diagnostics.ConsoleTraceListener" >  
        <filter type="System.Diagnostics.EventTypeFilter"  
          initializeData="Warning" />  
      </add>  
    </sharedListeners>  
    <sources>  
      <source name="mySource" switchName="sourceSwitch"  >  
        <listeners>  
          <add name="console" />  
        </listeners>  
      </source>  
    </sources>  
    <switches>  
      <add name="sourceSwitch" value="Verbose"/>  
    </switches>  
    <trace>  
      <listeners>  
        <add name="console" />  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration>
```  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Diagnostics.TraceListener>
- [Esquema de la configuración de seguimiento y depuración](index.md)
- [Agentes de escucha de seguimiento](../../../debug-trace-profile/trace-listeners.md)
