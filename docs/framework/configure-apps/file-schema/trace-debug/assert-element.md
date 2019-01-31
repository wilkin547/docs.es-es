---
title: <assert> (Elemento)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/assert
- http://schemas.microsoft.com/.NetConfiguration/v2.0#assert
helpviewer_keywords:
- <assert> element
- assert element
ms.assetid: ef4c3229-b151-4d85-8091-e6456af9b935
ms.openlocfilehash: aa5682c1cb2d662e1352c1d6c78e1a4a7e41f760
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55259523"
---
# <a name="assert-element"></a>\<Assert > elemento
Especifica si se muestra un cuadro de mensaje cuando se llama al método <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>; también indica el nombre del archivo para el que se van a escribir los mensajes.  
  
 \<configuration>  
\<system.diagnostics>  
\<assert>  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<assert assertuienabled="true|false" logfilename="file name"/>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`assertuienabled`|Atributo opcional.<br /><br /> Especifica si mostrar un cuadro de mensaje cuando el **Debug.Assert** se evalúa como método **false**.|  
|`logfilename`|Atributo opcional.<br /><br /> Especifica el nombre de archivo que se escribirá el mensaje como si **Debug.Assert** se evalúa como **false**.|  
  
## <a name="assertuienabled-attribute"></a>Atributo AssertUiEnabled  
  
|Valor|Descripción|  
|-----------|-----------------|  
|`true`|Muestra el cuadro de mensaje. Este es el valor predeterminado.|  
|`false`|No muestra el cuadro de mensaje.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`system.diagnostics`|Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.|  
  
## <a name="remarks"></a>Comentarios  
 Ambos atributos en el  **\<assert >** elemento son opcionales. Puede deshabilitar los cuadros de mensaje sin especificar un archivo para escribir los mensajes a, o puede especificar un archivo para escribir mensajes mientras deja cuadros habilitados del mensaje.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente muestra cómo deshabilitar la presentación de cuadros de mensaje cuando se llama a **Debug.Assert** y escribir los mensajes a `c:\log.txt`.  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <assert assertuienabled="false" logfilename="c:\log.txt"/>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a>Vea también
- <xref:System.Diagnostics.Debug>
- [Esquema de la configuración de seguimiento y depuración](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
