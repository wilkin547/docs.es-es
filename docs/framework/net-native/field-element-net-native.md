---
title: <Field> Elemento (.NET Native)
ms.date: 03/30/2017
ms.assetid: 6a14125f-1a8d-41a1-8a32-659ca0ad12de
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c58be27334bcb862367464475a4eade5e01bdbb2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59221618"
---
# <a name="field-element-net-native"></a>\<Campo > elemento (.NET Native)
Aplica la directiva de reflexión en tiempo de ejecución a un campo.  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<Field Name="field_name"  
       Browse="policy_type"  
       Dynamic="policy_type"  
       Serialize="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Tipo de atributo|Descripción|  
|---------------|--------------------|-----------------|  
|`Name`|General|Atributo necesario. Especifica el nombre del campo.|  
|`Browse`|Reflexión|Atributo opcional. Controla la consulta para obtener información sobre el campo o para enumerar el campo, pero no habilita ningún acceso dinámico en tiempo de ejecución.|  
|`Dynamic`|Reflexión|Atributo opcional. Controla el acceso en tiempo de ejecución al campo para habilitar la programación dinámica. Esta directiva garantiza que un campo se pueda establecer o recuperar dinámicamente en tiempo de ejecución.|  
|`Serialize`|Serialización|Atributo opcional. Controla el acceso en tiempo de ejecución a un campo para permitir que las instancias de tipos puedan ser serializadas por bibliotecas (como el serializador de JSON Newtonsoft) o para que puedan usarse en el enlace de datos.|  
  
## <a name="name-attribute"></a>Name (atributo)  
  
|Valor|Descripción|  
|-----------|-----------------|  
|*method_name*|Nombre de campo. El tipo del campo está definido por el elemento primario [\<Type>](../../../docs/framework/net-native/type-element-net-native.md) o [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md).|  
  
## <a name="all-other-attributes"></a>Resto de atributos  
  
|Valor|Descripción|  
|-----------|-----------------|  
|*policy_setting*|La configuración que se aplica a este tipo de política para el campo. Los valores posibles son `Auto`, `Excluded`, `Included` y `Required`. Para obtener más información, vea [Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md) (Configuración de directiva de la directiva en tiempo de ejecución).|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<tipo >](../../../docs/framework/net-native/type-element-net-native.md)|Aplica la directiva de reflexión a un tipo y a todos sus miembros.|  
|[\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)|Aplica la directiva de reflexión a un tipo genérico construido y a todos sus miembros.|  
  
## <a name="remarks"></a>Comentarios  
 Si la directiva de un campo no se define explícitamente, entonces hereda la directiva de tiempo de ejecución de su elemento primario.  
  
## <a name="see-also"></a>Vea también

- [Elementos de directivas en tiempo de ejecución](../../../docs/framework/net-native/runtime-directive-elements.md)
- [Referencia del archivo de configuración de directivas en tiempo de ejecución (rd.xml)](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)
- [Configuración de directiva de la directiva en tiempo de ejecución](../../../docs/framework/net-native/runtime-directive-policy-settings.md)
