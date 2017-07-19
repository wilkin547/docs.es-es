---
title: "Elemento &lt;MethodInstantiation&gt; (.NET Native) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a3355d78-2a88-4109-8521-830d7cae260a
caps.latest.revision: 17
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 17
---
# Elemento &lt;MethodInstantiation&gt; (.NET Native)
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
  
|Atributo|Tipo de atributo|Descripción|  
|---------------|--------------------|-----------------|  
|`Name`|General|Atributo necesario. Especifica el nombre del método.|  
|`Signature`|General|Atributo opcional. Especifica los parámetros con nombre del método. Cuando hay varios parámetros con nombre, se separan mediante coma. El atributo `Signature` se usa para diferenciar los métodos sobrecargados.|  
|`Arguments`|General|Atributo necesario. Especifica los argumentos de tipo genérico. Si hay varios argumentos, se separan mediante coma.|  
|`Browse`|Reflexión|Atributo opcional. Controla la consulta para obtener información acerca de un método o la enumeración de un método, pero no permite la invocación dinámica en tiempo de ejecución.|  
|`Dynamic`|Reflexión|Atributo opcional. Controla el acceso en tiempo de ejecución a un constructor o un método para habilitar la programación dinámica. Esta directiva garantiza que un miembro se puede invocar dinámicamente en tiempo de ejecución.|  
  
## <a name="name-attribute"></a>Name (atributo)  
  
|Valor|Descripción|  
|-----------|-----------------|  
|*NombreMétodo*|El nombre del método. El tipo del método se define por el elemento primario [ <> \> ](../../../docs/framework/net-native/type-element-net-native.md) o [ <> \> ](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) elemento.|  
  
## <a name="signature-attribute"></a>Signature (atributo)  
  
|Valor|Descripción|  
|-----------|-----------------|  
|*method_signature*|Especifica los parámetros con nombre del método. Si hay varios parámetros, se separan mediante coma.|  
  
## <a name="arguments-attribute"></a>Arguments (atributo)  
  
|Valor|Descripción|  
|-----------|-----------------|  
|*method_arguments*|Especifica los argumentos de tipo genérico. Si hay varios argumentos, se separan mediante coma. Cada argumento debe contener el nombre de tipo completo.|  
  
## <a name="all-other-attributes"></a>Resto de atributos  
  
|Valor|Descripción|  
|-----------|-----------------|  
|*policy_setting*|Configuración que se aplica a este tipo de directiva para el método. Los valores posibles son `Auto`, `Excluded`, `Included` y `Required`. Para obtener más información, consulte [configuración de directiva de directiva en tiempo de ejecución](../../../docs/framework/net-native/runtime-directive-policy-settings.md).|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[<>\>](../../../docs/framework/net-native/type-element-net-native.md)|Aplica la directiva de reflexión a un tipo y a todos sus miembros.|  
|[<>\>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)|Aplica la directiva de reflexión a un tipo genérico construido y a todos sus miembros.|  
  
## <a name="remarks"></a>Comentarios  
 El elemento `<MethodInstantiation>` invalida la directiva de reflexión en tiempo de ejecución de su correspondiente método genérico abierto.  
  
## <a name="see-also"></a>Vea también  
 [Referencia del archivo de configuración de tiempo de ejecución de directivas (rd.xml)](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)   
 [Elementos de directiva en tiempo de ejecución](../../../docs/framework/net-native/runtime-directive-elements.md)   
 [Configuración de la directiva de directiva en tiempo de ejecución](../../../docs/framework/net-native/runtime-directive-policy-settings.md)   
 [<>\>Elemento](../../../docs/framework/net-native/method-element-net-native.md)