---
title: '&lt;legacyCorruptedStateExceptionsPolicy&gt; elemento'
ms.date: 03/30/2017
helpviewer_keywords:
- <legacyCorruptedStateExceptionsPolicy> element
- legacyCorruptedStateExceptionsPolicy element
ms.assetid: e0a55ddc-bfa8-4f3e-ac14-d1fc3330e4bb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6228aaf4c7da70337d9d1a99adcb78f71a0039b2
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltlegacycorruptedstateexceptionspolicygt-element"></a>&lt;legacyCorruptedStateExceptionsPolicy&gt; elemento
Especifica si common language runtime permite al código administrado detectar infracciones de acceso y otras excepciones de estado dañado.  
  
 \<configuration>  
\<en tiempo de ejecución >  
\<legacyCorruptedStateExceptionsPolicy >  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<legacyCorruptedStateExceptionsPolicy enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`enabled`|Atributo necesario.<br /><br /> Especifica que la aplicación detectará errores de excepción de estado, como las infracciones de acceso de daño.|  
  
## <a name="enabled-attribute"></a>Atributo enabled  
  
|Valor|Descripción|  
|-----------|-----------------|  
|`false`|La aplicación no detectará errores de excepción de estado, como las infracciones de acceso de daño. Este es el valor predeterminado.|  
|`true`|La aplicación detectará errores de excepción de estado, como las infracciones de acceso de daño.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.|  
  
## <a name="remarks"></a>Comentarios  
 En la versión 3.5 y versiones anterior de .NET Framework, common language runtime permite al código administrado detectar las excepciones producidas por Estados de procesos dañados. Una infracción de acceso es un ejemplo de este tipo de excepción.  
  
 A partir de la [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)]administrada código ya no detecta estos tipos de excepciones en `catch` bloques. Sin embargo, puede invalidar este cambio y mantener el control de excepciones de estado dañado de dos maneras:  
  
-   Establecer el `<legacyCorruptedStateExceptionsPolicy>` del elemento `enabled` atribuir a `true`. Esta opción de configuración aplicados a todo el proceso y afecta a todos los métodos.  
  
 -o bien-  
  
-   Aplicar el <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute?displayProperty=nameWithType> atributo al método que contiene las excepciones `catch` bloque.  
  
 Este elemento de configuración solo está disponible en la [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] y versiones posteriores.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo especificar que la aplicación debe revertir al comportamiento antes de la [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]y detectar la corrupción de todos los errores de excepción de estado.  
  
```xml  
<configuration>  
   <runtime>  
      <legacyCorruptedStateExceptionsPolicy enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute>  
 [Esquema de la configuración de Common Language Runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [Esquema de los archivos de configuración](../../../../../docs/framework/configure-apps/file-schema/index.md)
