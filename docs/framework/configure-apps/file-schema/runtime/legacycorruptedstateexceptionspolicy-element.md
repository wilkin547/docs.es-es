---
title: <legacyCorruptedStateExceptionsPolicy> (Elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- <legacyCorruptedStateExceptionsPolicy> element
- legacyCorruptedStateExceptionsPolicy element
ms.assetid: e0a55ddc-bfa8-4f3e-ac14-d1fc3330e4bb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6191ee2169a85725f0367763874e60c0ceb1d7a4
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2019
ms.locfileid: "66489438"
---
# <a name="legacycorruptedstateexceptionspolicy-element"></a>\<legacyCorruptedStateExceptionsPolicy > elemento
Especifica si common language runtime permite código administrado para detectar infracciones de acceso y otras excepciones de estado dañado.  
  
 \<configuration>  
\<runtime>  
\<legacyCorruptedStateExceptionsPolicy>  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<legacyCorruptedStateExceptionsPolicy enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`enabled`|Atributo necesario.<br /><br /> Especifica que la aplicación detectará si se dañan los errores de excepción de estado como infracciones de acceso.|  
  
## <a name="enabled-attribute"></a>Atributo enabled  
  
|Valor|Descripción|  
|-----------|-----------------|  
|`false`|La aplicación no detectará si se dañan los errores de excepción de estado como infracciones de acceso. Este es el valor predeterminado.|  
|`true`|La aplicación detectará si se dañan los errores de excepción de estado como infracciones de acceso.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|  
|`runtime`|Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.|  
  
## <a name="remarks"></a>Comentarios  
 En la versión 3.5 y versiones anterior de .NET Framework, common language runtime permite código administrado detectar excepciones que se han producido por Estados de proceso dañado. Una infracción de acceso es un ejemplo de este tipo de excepción.  
  
 A partir de .NET Framework 4, código administrado ya no detecta estos tipos de excepciones en `catch` bloques. Sin embargo, puede invalidar este cambio y mantener el control de excepciones de estado dañado de dos maneras:  
  
- Establecer el `<legacyCorruptedStateExceptionsPolicy>` del elemento `enabled` atributo `true`. Esta opción de configuración está aplicado a todo el proceso y afecta a todos los métodos.  
  
 -o bien-  
  
- Aplicar el <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute?displayProperty=nameWithType> al método que contiene las excepciones `catch` bloque.  
  
 Este elemento de configuración está disponible solo en .NET Framework 4 y versiones posteriores.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente muestra cómo especificar que la aplicación debe revertir al comportamiento antes de .NET Framework 4 y detectar dañen todos los errores de excepción de estado.  
  
```xml  
<configuration>  
   <runtime>  
      <legacyCorruptedStateExceptionsPolicy enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Vea también

- <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute>
- [Esquema de la configuración de Common Language Runtime](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [Esquema de los archivos de configuración](../../../../../docs/framework/configure-apps/file-schema/index.md)
