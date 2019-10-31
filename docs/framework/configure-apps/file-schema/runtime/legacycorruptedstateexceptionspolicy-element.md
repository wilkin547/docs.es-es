---
title: <legacyCorruptedStateExceptionsPolicy> (Elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- <legacyCorruptedStateExceptionsPolicy> element
- legacyCorruptedStateExceptionsPolicy element
ms.assetid: e0a55ddc-bfa8-4f3e-ac14-d1fc3330e4bb
ms.openlocfilehash: d1d29a37999a01f3e370897a1052f4f94435a218
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73116455"
---
# <a name="legacycorruptedstateexceptionspolicy-element"></a>\<elemento > legacyCorruptedStateExceptionsPolicy
Especifica si el Common Language Runtime permite al código administrado detectar infracciones de acceso y otras excepciones de estado dañadas.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<en tiempo de ejecución >** ](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp; **\<legacyCorruptedStateExceptionsPolicy >**  
  
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
  
|Valor|Descripción|  
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
  
- Establezca el atributo `enabled` del elemento de `<legacyCorruptedStateExceptionsPolicy>` en `true`. Esta opción de configuración se aplica processwide y afecta a todos los métodos.  
  
 o bien  
  
- Aplique el atributo <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute?displayProperty=nameWithType> al método que contiene las excepciones `catch` bloque.  
  
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
