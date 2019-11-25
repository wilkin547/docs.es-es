---
title: Elemento <add> para <switches>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/switches/add
helpviewer_keywords:
- <add> element for <switches>
- add element for <switches>
ms.assetid: 712ac3a7-7abf-4a9e-8db4-acd241c2f369
ms.openlocfilehash: db2de681227dfdb7420808963219b9f52381f8fe
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088957"
---
# <a name="add-element-for-switches"></a>\<agregar > elemento para los modificadores de \<
Especifica el nivel en el que está establecido un modificador de seguimiento.  

[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. diagnostics >** ](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<modificadores**](switches-element.md) >\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**agregar >**

## <a name="syntax"></a>Sintaxis  
  
```xml  
<add name="switch name"  
     value="value"/>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|**name**|Atributo necesario.<br /><br /> Especifica el nombre del modificador. El valor de este atributo corresponde al parámetro *displayName* que se pasa al constructor switch.|  
|**valor**|Atributo necesario.<br /><br /> Especifica el nivel del modificador.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`switches`|Contiene modificadores de seguimiento y el nivel en el que están establecidos.|  
|`system.diagnostics`|Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.|  
  
## <a name="remarks"></a>Comentarios  
 Puede cambiar el nivel de un modificador de seguimiento si lo coloca en un archivo de configuración. Si el modificador es un <xref:System.Diagnostics.BooleanSwitch>, puede activarlo y desactivarlo. Si el modificador es un <xref:System.Diagnostics.TraceSwitch>, puede asignarle niveles diferentes para especificar los tipos de mensajes de seguimiento o de depuración que genera la aplicación.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo utilizar el elemento **\<agregar >** para establecer el modificador de `General` seguimiento en el nivel de <xref:System.Diagnostics.TraceLevel> y habilitar el modificador de seguimiento booleano `Data`.  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <switches>  
         <add name="General" value="4" />  
         <add name="Data" value="1" />  
      </switches>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a>Vea también

- <xref:System.Diagnostics.Switch>
- <xref:System.Diagnostics.TraceSwitch>
- <xref:System.Diagnostics.BooleanSwitch>
- [Esquema de la configuración de seguimiento y depuración](index.md)
