---
title: '&lt;filtro&gt; (elemento) para &lt;agregar&gt; para &lt;sharedListeners&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sharedListeners/add/filter
helpviewer_keywords:
- filter element for <add> for <sharedListeners>
- initializeData attribute
- <filter> element for <add> for <sharedListeners>
- filters, trace listeners
- trace listeners, filters
ms.assetid: 7d4e7faa-2e4e-4379-ac76-f6cd7f2f8fac
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 3bbba1c805c6b300f7cf7b3d9112cde9df7607a8
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32745060"
---
# <a name="ltfiltergt-element-for-ltaddgt-for-ltsharedlistenersgt"></a>&lt;filtro&gt; (elemento) para &lt;agregar&gt; para &lt;sharedListeners&gt;
Agrega un filtro a un agente de escucha en la colección `sharedListeners`.  
  
 \<configuration>  
\<System.Diagnostics >  
\<sharedListeners > elemento  
\<add>  
\<Filtro >  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<filter type="System.Diagnostics.EventTypeFilter"   
  initializeData="Warning" />  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|**type**|Atributo necesario.<br /><br /> Especifica el tipo de filtro. Puede usar solo el nombre completo del tipo (con el formato de la <xref:System.Type.FullName%2A?displayProperty=nameWithType> propiedad), o puede usar el nombre de tipo completo, incluida la información de ensamblado (en el formato de la <xref:System.Type.AssemblyQualifiedName%2A?displayProperty=nameWithType> propiedad). Para obtener información acerca de cómo crear un nombre de tipo completo, vea [especificar nombres de tipo completos](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).|  
|**initializeData**|Atributo opcional.<br /><br /> La cadena pasada al constructor de la clase especificada.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`system.diagnostics`|Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.|  
|`sharedListeners`|Una colección de agentes de escucha que se puede hacer referencia a cualquier origen o elemento de seguimiento.|  
|`add`|Agrega un agente de escucha para el **sharedListeners** colección.|  
  
## <a name="remarks"></a>Comentarios  
 Si un agente de escucha se define en un `<add>` elemento de la `<sharedListeners>` elemento, el filtro de ese agente de escucha debe definirse en un `<filter>` elemento que es un elemento secundario de la `<add>` elemento.  
  
 Este elemento se puede usar en el archivo de configuración del equipo (Machine.config) y el archivo de configuración de aplicación.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo utilizar el `<filter>` elemento para agregar un filtro al agente de escucha de seguimiento `console` en el `sharedListeners` colección.  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="myTraceSource" >  
        <listeners>  
          <add name="console" />  
          <remove name="Default" />  
        </listeners>  
      </source>  
    </sources>  
    <sharedListeners>  
      <add name="console"   
        type="System.Diagnostics.ConsoleTraceListener" >  
        <filter type="System.Diagnostics.EventTypeFilter"   
          initializeData="Error" />  
      </add>  
    </sharedListeners>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Diagnostics.TraceFilter>  
 <xref:System.Diagnostics.TraceListener>  
 <xref:System.Diagnostics.TraceSource>  
 [Esquema de la configuración de seguimiento y depuración](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
