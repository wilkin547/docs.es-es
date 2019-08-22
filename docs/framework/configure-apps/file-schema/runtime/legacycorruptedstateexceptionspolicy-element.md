---
title: <legacyCorruptedStateExceptionsPolicy> (Elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- <legacyCorruptedStateExceptionsPolicy> element
- legacyCorruptedStateExceptionsPolicy element
ms.assetid: e0a55ddc-bfa8-4f3e-ac14-d1fc3330e4bb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2715548a40579375cebbdd5fb9003738a42ff714
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663651"
---
# <a name="legacycorruptedstateexceptionspolicy-element"></a>\<legacyCorruptedStateExceptionsPolicy >, elemento
Especifica si el Common Language Runtime permite al código administrado detectar infracciones de acceso y otras excepciones de estado dañadas.  
  
 \<configuration>  
\<> en tiempo de ejecución  
\<legacyCorruptedStateExceptionsPolicy>  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<legacyCorruptedStateExceptionsPolicy enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|DESCRIPCIÓN|  
|---------------|-----------------|  
|`enabled`|Atributo necesario.<br /><br /> Especifica que la aplicación detectará errores de excepción de estado dañados, como infracciones de acceso.|  
  
## <a name="enabled-attribute"></a>Atributo enabled  
  
|Valor|DESCRIPCIÓN|  
|-----------|-----------------|  
|`false`|La aplicación no detectará errores de excepción de estado dañados, como infracciones de acceso. Este es el valor predeterminado.|  
|`true`|La aplicación detectará errores de excepción de estado dañados, como infracciones de acceso.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|DESCRIPCIÓN|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.|  
  
## <a name="remarks"></a>Comentarios  
 En la .NET Framework versión 3,5 y versiones anteriores, el Common Language Runtime permitía que el código administrado detectara las excepciones que se producían con Estados de proceso dañados. Una infracción de acceso es un ejemplo de este tipo de excepción.  
  
 A partir de la .NET Framework 4, el código administrado ya no detecta estos tipos de excepciones `catch` en bloques. Sin embargo, puede invalidar este cambio y mantener el control de las excepciones de estado dañadas de dos maneras:  
  
- Establezca el `<legacyCorruptedStateExceptionsPolicy>` atributo del `enabled` elemento en `true`. Esta opción de configuración se aplica processwide y afecta a todos los métodos.  
  
 -o bien-  
  
- Aplique el <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute?displayProperty=nameWithType> atributo al método que contiene el bloque de `catch` excepciones.  
  
 Este elemento de configuración solo está disponible en el .NET Framework 4 y versiones posteriores.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo especificar que la aplicación debe volver al comportamiento anterior a la .NET Framework 4 y detectar todos los errores de excepción de estado dañado.  
  
```xml  
<configuration>  
   <runtime>  
      <legacyCorruptedStateExceptionsPolicy enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vea también

- <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute>
- [Esquema de la configuración de Common Language Runtime](index.md)
- [Esquema de los archivos de configuración](../index.md)
