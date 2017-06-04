---
title: "Elemento &lt;Type&gt; (.NET Native) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1e88d368-a886-4f1e-8eb6-6127979a9fce
caps.latest.revision: 33
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 33
---
# Elemento &lt;Type&gt; (.NET Native)
Aplica la directiva de tiempo de ejecución a un tipo determinado, como una clase o estructura.  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
  
<Type Name="type_name"  
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
|`Activate`|Reflexión|Atributo opcional. Controla el acceso en tiempo de ejecución a los constructores para permitir la activación de instancias.|  
|`Browse`|Reflexión|Atributo opcional. Controla la consulta para obtener información sobre los elementos de programa, pero no permite el acceso en tiempo de ejecución.|  
|`Dynamic`|Reflexión|Atributo opcional. Controla el acceso en tiempo de ejecución a todos los miembros de tipo (incluidos constructores, métodos, campos, propiedades y eventos) para permitir la programación dinámica.|  
|`Serialize`|Serialización|Atributo opcional. Controla el acceso en tiempo de ejecución a constructores, campos y propiedades para permitir que bibliotecas como el serializador JSON Newtonsoft puedan serializar y deserializar instancias de tipo.|  
|`DataContractSerializer`|Serialización|Atributo opcional. Controla la directiva de serialización que usa el <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=fullName> clase.|  
|`DataContractJsonSerializer`|Serialización|Atributo opcional. Controla la directiva de serialización JSON que usa el <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=fullName> clase.|  
|`XmlSerializer`|Serialización|Atributo opcional. Controla la directiva de serialización XML que usa el <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName> clase.|  
|`MarshalObject`|Interop|Atributo opcional. Controla la directiva de serialización de tipos de referencia a Windows Runtime y COM.|  
|`MarshalDelegate`|Interop|Atributo opcional. Controla la directiva de serialización de tipos de delegado como punteros de función a código nativo.|  
|`MarshalStructure`|Interop|Atributo opcional. Controla la directiva de cálculo de referencias de tipos de valor a código nativo.|  
  
## <a name="name-attribute"></a>Name (atributo)  
  
|Valor|Descripción|  
|-----------|-----------------|  
|*TYPE_NAME*|Nombre del tipo. Si este `<Type>` elemento es el elemento secundario de un [ <> \> ](../../../docs/framework/net-native/namespace-element-net-native.md) elemento u otro `<Type>` elemento, *type_name* puede incluir el nombre del tipo sin su espacio de nombres. De lo contrario, *type_name* debe incluir el nombre de tipo completo.|  
  
## <a name="all-other-attributes"></a>Resto de atributos  
  
|Valor|Descripción|  
|-----------|-----------------|  
|*policy_setting*|Configuración que se va a aplicar a este tipo de directiva. Los valores posibles son `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` y `Required All`. Para obtener más información, consulte [configuración de directiva de directiva en tiempo de ejecución](../../../docs/framework/net-native/runtime-directive-policy-settings.md).|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[<>\>](../../../docs/framework/net-native/attributeimplies-element-net-native.md)|Si el tipo contenedor es un atributo, define la directiva de tiempo de ejecución para elementos de código a los que se aplica el atributo.|  
|[<>\>](../../../docs/framework/net-native/event-element-net-native.md)|Aplica la directiva de reflexión a un evento perteneciente a este tipo.|  
|[<>\>](../../../docs/framework/net-native/field-element-net-native.md)|Aplica la directiva de reflexión a un campo perteneciente a este tipo.|  
|[<>\>](../../../docs/framework/net-native/genericparameter-element-net-native.md)|Aplica la directiva al tipo del parámetro de tipo genérico.|  
|[<>\>](../../../docs/framework/net-native/impliestype-element-net-native.md)|Aplica la directiva a un tipo, en caso de que dicha directiva se haya aplicado al tipo representado por el elemento `<Type>` que lo contiene.|  
|[<>\>](../../../docs/framework/net-native/method-element-net-native.md)|Aplica la directiva de reflexión a un método perteneciente a este tipo.|  
|[<>\>](../../../docs/framework/net-native/methodinstantiation-element-net-native.md)|Aplica la directiva de reflexión a un método genérico construido perteneciente a este tipo.|  
|[<>\>](../../../docs/framework/net-native/property-element-net-native.md)|Aplica la directiva de reflexión a una propiedad perteneciente a este tipo.|  
|[<>\>](../../../docs/framework/net-native/subtypes-element-net-native.md)|Aplica la directiva en tiempo de ejecución a todas las clases heredadas del tipo contenedor.|  
|`<Type>`|Aplica la directiva de reflexión a un tipo anidado.|  
|[<>\>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)|Aplica la directiva de reflexión a un tipo genérico construido.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[<>\>](../../../docs/framework/net-native/application-element-net-native.md)|Sirve de contenedor de los tipos y miembros de tipo de la aplicación cuyos metadatos están disponibles para la reflexión en tiempo de ejecución.|  
|[<>\>](../../../docs/framework/net-native/assembly-element-net-native.md)|Aplica la directiva de reflexión a todos los tipos en un ensamblado especificado.|  
|[<>\>](../../../docs/framework/net-native/library-element-net-native.md)|Define el ensamblado que contiene los tipos y miembros de tipo cuyos metadatos están disponibles para la reflexión en tiempo de ejecución.|  
|[<>\>](../../../docs/framework/net-native/namespace-element-net-native.md)|Aplica la directiva de reflexión a todos los tipos en un espacio de nombres.|  
|`<Type>`|Aplica la directiva de reflexión a un tipo y a todos sus miembros.|  
|[<>\>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)|Aplica la directiva de reflexión a un tipo genérico construido y a todos sus miembros.|  
  
## <a name="remarks"></a>Comentarios  
 Los atributos de reflexión, serialización e interoperabilidad son opcionales. Si ninguno de ellos está presente, el elemento `<Type>` actúa como un contenedor cuyos tipos secundarios definen directivas para los miembros individuales.  
  
 Si un `<Type>` elemento es el elemento secundario de un [ <> \</> \> ](../../../docs/framework/net-native/assembly-element-net-native.md), [ <> \</> \> ](../../../docs/framework/net-native/namespace-element-net-native.md), `<Type>`, o [ <> \> ](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) elemento, invalida la configuración de directiva definida por el elemento primario.  
  
 Un elemento `<Type>` de un tipo genérico aplica su directiva a todas las instancias que no tienen su propia directiva. La directiva de tipos genéricos construidos se define mediante la [ <> \> ](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) elemento.  
  
 Si el tipo es un tipo genérico, su nombre se decora con un símbolo de acento grave ('' ') seguido por el número de parámetros genéricos. Por ejemplo, el `Name` atributo de un `<Type>` (elemento) para la <xref:System.Collections.Generic.List%601?displayProperty=fullName> clase aparece como `Name="System.Collections.Generic.List`1"'.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se utiliza la reflexión para mostrar información sobre los campos, propiedades y métodos de la <xref:System.Collections.Generic.List%601?displayProperty=fullName> clase. La variable `b` en el ejemplo es un [TextBlock](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.controls.textblock.aspx) control. Dado que el ejemplo simplemente recupera información de tipos, la disponibilidad de los metadatos se controla mediante la configuración de directiva `Browse`.  
  
 [!code-csharp[ProjectN_Reflection#3](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn_reflection/cs/browsegenerictype1.cs#3)]  
  
 Porque los metadatos para la <xref:System.Collections.Generic.List%601> clase no se incluye automáticamente en el [!INCLUDE[net_native](../../../includes/net-native-md.md)] cadena de herramientas, el ejemplo no se puede mostrar la información del miembro solicitada en tiempo de ejecución. Para proporcionar los metadatos necesarios, agregue el elemento `<Type>` siguiente al archivo de directivas en tiempo de ejecución. Tenga en cuenta que, dado que hemos proporcionado un elemento primario [ <> \> ](../../../docs/framework/net-native/namespace-element-net-native.md) elemento, no es necesario proporcionar un nombre de tipo completo en el `<Type>` elemento.  
  
```xml  
  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <Application>  
      <Assembly Name="*Application*" Dynamic="Required All" />  
      <Namespace Name ="System.Collections.Generic" >  
        <Type Name="List`1" Browse="Required All" />   
     </Namespace>  
   </Application>  
</Directives>  
  
```  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se utiliza la reflexión para recuperar un <xref:System.Reflection.PropertyInfo> objeto que representa el <xref:System.String.Chars%2A?displayProperty=fullName> propiedad. A continuación, utiliza el [PropertyInfo.GetValue (Object, Object\<xref:System.Reflection.PropertyInfo.GetValue%28System.Object%2CSystem.Object%5B%5D%29?displayProperty=fullName> método para recuperar el valor del séptimo carácter en una cadena y para mostrar todos los caracteres de la cadena. La variable `b` en el ejemplo es un [TextBlock](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.controls.textblock.aspx) control.  
  
 [!code-csharp[ProjectN_Reflection#1](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn_reflection/cs/propertyinfo1.cs#1)]  
  
 Porque metadatos para la <xref:System.String> objeto no está disponible, la llamada a la [PropertyInfo.GetValue (Object, Object\<xref:System.Reflection.PropertyInfo.GetValue%28System.Object%2CSystem.Object%5B%5D%29?displayProperty=fullName> método produce un <xref:System.NullReferenceException> excepción en ejecución tiempo cuando se compila con la [!INCLUDE[net_native](../../../includes/net-native-md.md)] cadena de herramientas. Para eliminar la excepción y proporcionar los metadatos necesarios, agregue el siguiente elemento `<Type>` al archivo de directivas en tiempo de ejecución:  
  
```xml  
  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
  <Application>  
    <Assembly Name="*Application*" Dynamic="Required All" />  
    <Type Name="System.String" Dynamic="Required Public"/> -->  
  </Application>  
</Directives>  
  
```  
  
## <a name="see-also"></a>Vea también  
 [Referencia del archivo de configuración de tiempo de ejecución de directivas (rd.xml)](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)   
 [Elementos de directiva en tiempo de ejecución](../../../docs/framework/net-native/runtime-directive-elements.md)   
 [Configuración de la directiva de directiva en tiempo de ejecución](../../../docs/framework/net-native/runtime-directive-policy-settings.md)