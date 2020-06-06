---
title: <legacyCorruptedStateExceptionsPolicy> (Elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- <legacyCorruptedStateExceptionsPolicy> element
- legacyCorruptedStateExceptionsPolicy element
ms.assetid: e0a55ddc-bfa8-4f3e-ac14-d1fc3330e4bb
ms.openlocfilehash: d1d29a37999a01f3e370897a1052f4f94435a218
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "73116455"
---
# <a name="legacycorruptedstateexceptionspolicy-element"></a>\<legacyCorruptedStateExceptionsPolicy> (Elemento)
Especifica si el Common Language Runtime permite al código administrado detectar infracciones de acceso y otras excepciones de estado dañadas.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<legacyCorruptedStateExceptionsPolicy>**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<legacyCorruptedStateExceptionsPolicy enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`enabled`|Atributo necesario.<br /><br /> Especifica que la aplicación detectará errores de excepción de estado dañados, como infracciones de acceso.|  
  
## <a name="enabled-attribute"></a>Atributo enabled  
  
|Value|Descripción|  
|-----------|-----------------|  
|`false`|La aplicación no detectará errores de excepción de estado dañados, como infracciones de acceso. Este es el valor predeterminado.|  
|`true`|La aplicación detectará errores de excepción de estado dañados, como infracciones de acceso.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.|  
  
## <a name="remarks"></a>Comentarios  
 En la .NET Framework versión 3,5 y versiones anteriores, el Common Language Runtime permitía que el código administrado detectara las excepciones que se producían con Estados de proceso dañados. Una infracción de acceso es un ejemplo de este tipo de excepción.  
  
 A partir de la .NET Framework 4, el código administrado ya no detecta estos tipos de excepciones en `catch` bloques. Sin embargo, puede invalidar este cambio y mantener el control de las excepciones de estado dañadas de dos maneras:  
  
- Establezca el `<legacyCorruptedStateExceptionsPolicy>` atributo del elemento `enabled` en `true` . Esta opción de configuración se aplica processwide y afecta a todos los métodos.  
  
 O bien  
  
- Aplique el <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute?displayProperty=nameWithType> atributo al método que contiene el bloque de excepciones `catch` .  
  
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
  
## <a name="see-also"></a>Consulte también

- <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute>
- [Esquema de la configuración de Common Language Runtime](index.md)
- [Esquema de los archivos de configuración](../index.md)
