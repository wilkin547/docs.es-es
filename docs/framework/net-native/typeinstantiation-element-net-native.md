---
title: "Elemento &lt;TypeInstantiation&gt; (.NET Native) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a5eada64-075b-4162-9655-ded84e4681f2
caps.latest.revision: 21
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 21
---
# Elemento &lt;TypeInstantiation&gt; (.NET Native)
Aplica la directiva de reflexión en tiempo de ejecución a un tipo genérico construido.  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
  
<TypeInstantiation Name="type_name"  
                   Arguments="type_arguments"  
                   Activate="policy_type"  
                   Browse="policy_type"  
                   Dynamic="policy_type"  
                   Serialize="policy_type"  
                   DataContractSerializer="policy_setting"  
                   DataContractJsonSerializer="policy_setting"  
                   XmlSerializer="policy_setting"  
                   MarshalObject="policy_setting"  
                   MarshalDelegate="policy_setting"  
                   MarshalStructure="policy_setting" />  
  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Tipo de atributo|Descripción|  
|---------------|--------------------|-----------------|  
|`Name`|General|Atributo necesario. Especifica el nombre del tipo.|  
|`Arguments`|General|Atributo necesario. Especifica los argumentos de tipo genérico. Si hay varios argumentos, se separan mediante coma.|  
|`Activate`|Reflexión|Atributo opcional. Controla el acceso en tiempo de ejecución a los constructores para permitir la activación de instancias.|  
|`Browse`|Reflexión|Atributo opcional. Controla la consulta para obtener información sobre los elementos de programa, pero no permite el acceso en tiempo de ejecución.|  
|`Dynamic`|Reflexión|Atributo opcional. Controla el acceso en tiempo de ejecución a todos los miembros de tipo (incluidos constructores, métodos, campos, propiedades y eventos) para permitir la programación dinámica.|  
|`Serialize`|Serialización|Atributo opcional. Controla el acceso en tiempo de ejecución a constructores, campos y propiedades para permitir que bibliotecas como el serializador JSON Newtonsoft puedan serializar y deserializar instancias de tipo.|  
|`DataContractSerializer`|Serialización|Atributo opcional. Controla la directiva de serialización que usa el <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=fullName> clase.|  
|`DataContractJsonSerializer`|Serialización|Atributo opcional. Controla la directiva de serialización JSON que usa el <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=fullName> clase.|  
|`XmlSerializer`|Serialización|Atributo opcional. Controla la directiva de serialización XML que usa el <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> clase.|  
|`MarshalObject`|Interop|Atributo opcional. Controla la directiva de serialización de tipos de referencia a Windows Runtime y COM.|  
|`MarshalDelegate`|Interop|Atributo opcional. Controla la directiva de serialización de tipos de delegado como punteros de función a código nativo.|  
|`MarshalStructure`|Interop|Atributo opcional. Controla la directiva de cálculo de referencias de estructuras a código nativo.|  
  
## <a name="name-attribute"></a>Name (atributo)  
  
|Valor|Descripción|  
|-----------|-----------------|  
|*TYPE_NAME*|Nombre del tipo. Si este `<TypeInstantiation>` elemento es el elemento secundario de un [ <> \> ](../../../docs/framework/net-native/namespace-element-net-native.md) elemento, un [ <> \> ](../../../docs/framework/net-native/type-element-net-native.md) elemento u otro `<TypeInstantiation>` elemento, *type_name* puede especificar el nombre del tipo sin su espacio de nombres. De lo contrario, *type_name* debe incluir el nombre de tipo completo. El nombre de tipo no es representativo. Por ejemplo, para un <xref:System.Collections.Generic.List%601?displayProperty=fullName> objeto, el `<TypeInstantiation>` elemento puede aparecer como sigue:<br /><br /> `\<TypeInstantiation Name=System.Collections.Generic.List Dynamic="Required Public" />`|  
  
## <a name="arguments-attribute"></a>Arguments (atributo)  
  
|Valor|Descripción|  
|-----------|-----------------|  
|*type_argument*|Especifica los argumentos de tipo genérico. Si hay varios argumentos, se separan mediante coma. Cada argumento debe contener el nombre de tipo completo.|  
  
## <a name="all-other-attributes"></a>Resto de atributos  
  
|Valor|Descripción|  
|-----------|-----------------|  
|*policy_setting*|Configuración que se aplica a este tipo de directiva para el tipo genérico construido. Los valores posibles son `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` y `Required All`. Para obtener más información, consulte [configuración de directiva de directiva en tiempo de ejecución](../../../docs/framework/net-native/runtime-directive-policy-settings.md).|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[<>\>](../../../docs/framework/net-native/event-element-net-native.md)|Aplica la directiva de reflexión a un evento perteneciente a este tipo.|  
|[<>\>](../../../docs/framework/net-native/field-element-net-native.md)|Aplica la directiva de reflexión a un campo perteneciente a este tipo.|  
|[<>\>](../../../docs/framework/net-native/impliestype-element-net-native.md)|Aplica la directiva a un tipo, en caso de que dicha directiva se haya aplicado al tipo representado por el elemento `<TypeInstantiation>` que lo contiene.|  
|[<>\>](../../../docs/framework/net-native/method-element-net-native.md)|Aplica la directiva de reflexión a un método perteneciente a este tipo.|  
|[<>\>](../../../docs/framework/net-native/methodinstantiation-element-net-native.md)|Aplica la directiva de reflexión a un método genérico construido perteneciente a este tipo.|  
|[<>\>](../../../docs/framework/net-native/property-element-net-native.md)|Aplica la directiva de reflexión a una propiedad perteneciente a este tipo.|  
|[<>\>](../../../docs/framework/net-native/type-element-net-native.md)|Aplica la directiva de reflexión a un tipo anidado.|  
|`<TypeInstantiation>`|Aplica la directiva de reflexión a un tipo genérico construido anidado.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[<>\>](../../../docs/framework/net-native/application-element-net-native.md)|Sirve de contenedor de los tipos y miembros de tipo de la aplicación cuyos metadatos están disponibles para la reflexión en tiempo de ejecución.|  
|[<>\>](../../../docs/framework/net-native/assembly-element-net-native.md)|Aplica la directiva de reflexión a todos los tipos en un ensamblado especificado.|  
|[<>\>](../../../docs/framework/net-native/library-element-net-native.md)|Define el ensamblado que contiene los tipos y miembros de tipo cuyos metadatos están disponibles para la reflexión en tiempo de ejecución.|  
|[<>\>](../../../docs/framework/net-native/namespace-element-net-native.md)|Aplica la directiva de reflexión a todos los tipos en un espacio de nombres.|  
|[<>\>](../../../docs/framework/net-native/type-element-net-native.md)|Aplica la directiva de reflexión a un tipo y a todos sus miembros.|  
|`<TypeInstantiation>`|Aplica la directiva de reflexión a un tipo genérico construido y a todos sus miembros.|  
  
## <a name="remarks"></a>Comentarios  
 Los atributos de reflexión, serialización e interoperabilidad son opcionales. Sin embargo, al menos uno debe estar presente.  
  
 Si un `<TypeInstantiation>` elemento es el elemento secundario de un [ <> \</> \> ](../../../docs/framework/net-native/assembly-element-net-native.md), [ <> \</> \> ](../../../docs/framework/net-native/namespace-element-net-native.md), o [ <> \</> \> ](../../../docs/framework/net-native/type-element-net-native.md), elemento, invalida la configuración de directiva definida por el elemento primario. Si un [ <> \> ](../../../docs/framework/net-native/type-element-net-native.md) elemento define una definición de tipo genérico correspondiente, el `<TypeInstantiation>` elemento invalida la directiva de reflexión en tiempo de ejecución solo para creaciones de instancias de tipo genérico construido especificado.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se utiliza la reflexión para recuperar la definición de tipo genérico de un construido <xref:System.Collections.Generic.Dictionary%602> objeto.</TKey, TValue> También usa la reflexión para mostrar información sobre <xref:System.Type> objetos que representan tipos genéricos construidos y definiciones de tipo genérico. La variable `b` en el ejemplo es un [TextBlock](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.controls.textblock.aspx) control.  
  
 [!code-csharp[ProjectN_Reflection#2](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn_reflection/cs/makegenerictype1.cs#2)]  
  
 Después de la compilación con el [!INCLUDE[net_native](../../../includes/net-native-md.md)] cadena de herramientas, el ejemplo genera un [MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md) excepción en la línea que llama el <xref:System.Type.GetGenericTypeDefinition%2A?displayProperty=fullName> método. Puede eliminar la excepción e indicar los metadatos necesarios agregando el siguiente elemento `<TypeInstantiation>` al archivo de directivas en tiempo de ejecución:  
  
```xml  
  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
  <Application>  
    <Assembly Name="*Application*" Dynamic="Required All" />  
     <TypeInstantiation Name="System.Collections.Generic.Dictionary"  
                        Arguments="System.String,GenericType.Example"  
                        Dynamic="Required Public" />  
  </Application>  
</Directives>  
  
```  
  
## <a name="see-also"></a>Vea también  
 [Referencia del archivo de configuración de tiempo de ejecución de directivas (rd.xml)](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)   
 [Elementos de directiva en tiempo de ejecución](../../../docs/framework/net-native/runtime-directive-elements.md)   
 [Configuración de la directiva de directiva en tiempo de ejecución](../../../docs/framework/net-native/runtime-directive-policy-settings.md)