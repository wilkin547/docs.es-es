---
title: <MethodInstantiation>Elemento (.NET Native)
ms.date: 03/30/2017
ms.assetid: a3355d78-2a88-4109-8521-830d7cae260a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f2c0354853e4725ba3e673fb9142c4a7a85d2121
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2019
ms.locfileid: "71049619"
---
# <a name="methodinstantiation-element-net-native"></a>\<Elemento > MethodInstantiation (.NET Native)
Aplica la directiva de reflexión en tiempo de ejecución a un método genérico construido.  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<MethodInstantiation Name="method_name"  
                     Signature="method_signature"  
                     Arguments="method_arguments"  
                     Browse="policy_type"  
                     Dynamic="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Tipo de atributo|DESCRIPCIÓN|  
|---------------|--------------------|-----------------|  
|`Name`|General|Atributo necesario. Especifica el nombre del método.|  
|`Signature`|General|Atributo opcional. Especifica los parámetros con nombre del método. Cuando hay varios parámetros con nombre, se separan mediante coma. El atributo `Signature` se usa para diferenciar los métodos sobrecargados.|  
|`Arguments`|General|Atributo necesario. Especifica los argumentos de tipo genérico. Si hay varios argumentos, se separan mediante coma.|  
|`Browse`|Reflexión|Atributo opcional. Controla la consulta para obtener información acerca de un método o la enumeración de un método, pero no permite la invocación dinámica en tiempo de ejecución.|  
|`Dynamic`|Reflexión|Atributo opcional. Controla el acceso en tiempo de ejecución a un constructor o un método para habilitar la programación dinámica. Esta directiva garantiza que un miembro se puede invocar dinámicamente en tiempo de ejecución.|  
  
## <a name="name-attribute"></a>Name (atributo)  
  
|Valor|DESCRIPCIÓN|  
|-----------|-----------------|  
|*method_name*|El nombre del método. El tipo del método se define mediante el elemento primario [\<Type>](type-element-net-native.md) o [\<TypeInstantiation>](typeinstantiation-element-net-native.md).|  
  
## <a name="signature-attribute"></a>Signature (atributo)  
  
|Valor|DESCRIPCIÓN|  
|-----------|-----------------|  
|*method_signature*|Especifica los parámetros con nombre del método. Si hay varios parámetros, se separan mediante comas.|  
  
## <a name="arguments-attribute"></a>Arguments (atributo)  
  
|Valor|DESCRIPCIÓN|  
|-----------|-----------------|  
|*method_arguments*|Especifica los argumentos de tipo genérico. Si hay varios argumentos, se separan mediante coma. Cada argumento debe contener el nombre de tipo completo.|  
  
## <a name="all-other-attributes"></a>Resto de atributos  
  
|Valor|DESCRIPCIÓN|  
|-----------|-----------------|  
|*policy_setting*|Configuración que se aplica a este tipo de directiva para el método. Los valores posibles son `Auto`, `Excluded`, `Included` y `Required`. Para obtener más información, vea [Runtime Directive Policy Settings](runtime-directive-policy-settings.md) (Configuración de directiva de la directiva en tiempo de ejecución).|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|DESCRIPCIÓN|  
|-------------|-----------------|  
|[\<Type>](type-element-net-native.md)|Aplica la directiva de reflexión a un tipo y a todos sus miembros.|  
|[\<TypeInstantiation>](typeinstantiation-element-net-native.md)|Aplica la directiva de reflexión a un tipo genérico construido y a todos sus miembros.|  
  
## <a name="remarks"></a>Comentarios  
 El elemento `<MethodInstantiation>` invalida la directiva de reflexión en tiempo de ejecución de su correspondiente método genérico abierto.  
  
## <a name="see-also"></a>Vea también

- [Runtime Directives (rd.xml) Configuration File Reference (Referencia del archivo de configuración de directivas en tiempo de ejecución (rd.xml))](runtime-directives-rd-xml-configuration-file-reference.md)
- [Runtime Directive Elements (Elementos de directivas en tiempo de ejecución)](runtime-directive-elements.md)
- [Runtime Directive Policy Settings](runtime-directive-policy-settings.md) (Configuración de directiva de la directiva en tiempo de ejecución)
- [Elemento \<Method>](method-element-net-native.md)
