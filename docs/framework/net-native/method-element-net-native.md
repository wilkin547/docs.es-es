---
title: "Elemento &lt;Method&gt; (.NET Native) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 348b49e5-589d-4eb2-a597-d6ff60ab52d1
caps.latest.revision: 22
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 22
---
# Elemento &lt;Method&gt; (.NET Native)
Aplica la directiva de reflexión en tiempo de ejecución a un constructor o un método.  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
  
<Method Name="method_name"  
        Signature="method_signature"  
        Browse="policy_type"  
        Dynamic="policy_type" />  
  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Tipo de atributo|Descripción|  
|---------------|--------------------|-----------------|  
|`Name`|General|Atributo necesario. Especifica el nombre del método.|  
|`Signature`|General|Atributo opcional. Especifica la signatura del método. Si hay varios parámetros, se separan mediante coma. Por ejemplo, la siguiente `<Method>` elemento define la directiva de la <xref:System.DateTimeOffset.ToString%28System.String%2CSystem.IFormatProvider%29> (método).<br /><br /> `<Type Name="System.DateTime">    <Method Name="ToString" Signature="System.String,System.IFormatProvider"            Dynamic="Required" /> </Type>`<br /><br /> Si el atributo no está presente, la directiva de tiempo de ejecución se aplica a todas las sobrecargas del método.|  
|`Browse`|Reflexión|Atributo opcional. Controla la consulta para obtener información acerca de un método o la enumeración de un método, pero no permite la invocación dinámica en tiempo de ejecución.|  
|`Dynamic`|Reflexión|Atributo opcional. Controla el acceso en tiempo de ejecución a un constructor o un método para habilitar la programación dinámica. Esta directiva garantiza que un miembro se puede invocar dinámicamente en tiempo de ejecución.|  
  
## <a name="name-attribute"></a>Name (atributo)  
  
|Valor|Descripción|  
|-----------|-----------------|  
|*NombreMétodo*|El nombre del método. El tipo del método se define por el elemento primario [ <> \> ](../../../docs/framework/net-native/type-element-net-native.md) o [ <> \> ](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) elemento.|  
  
## <a name="signature-attribute"></a>Signature (atributo)  
  
|Valor|Descripción|  
|-----------|-----------------|  
|*method_signature*|Los tipos de parámetros que constituyen la signatura del método. Si hay varios parámetros, se separan por comas; por ejemplo, `"System.String,System.Int32,System.Int32)"`. Los nombres de tipo de parámetro deben ser completos.|  
  
## <a name="all-other-attributes"></a>Todos los demás atributos  
  
|Valor|Descripción|  
|-----------|-----------------|  
|*policy_setting*|Configuración que se va a aplicar a este tipo de directiva. Los valores posibles son `Auto`, `Excluded`, `Included` y `Required`. Para obtener más información, consulte [configuración de directiva de directiva en tiempo de ejecución](../../../docs/framework/net-native/runtime-directive-policy-settings.md).|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[<>\>](../../../docs/framework/net-native/parameter-element-net-native.md)|Aplica la directiva al tipo del argumento que se pasa a un método.|  
|[<>\>](../../../docs/framework/net-native/genericparameter-element-net-native.md)|Aplica la directiva al tipo de parámetro de un método o tipo genérico.|  
|[<>\>](../../../docs/framework/net-native/impliestype-element-net-native.md)|Aplica la directiva a un tipo, si esa directiva se ha aplicado al método representado por el elemento `<Method>` contenedor.|  
|[<>\>](../../../docs/framework/net-native/typeparameter-element-net-native.md)|Aplica la directiva al tipo representado por un <xref:System.Type> argumento pasado a un método.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[<>\>](../../../docs/framework/net-native/type-element-net-native.md)|Aplica la directiva de reflexión a un tipo y a todos sus miembros.|  
|[<>\>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)|Aplica la directiva de reflexión a un tipo genérico construido y a todos sus miembros.|  
  
## <a name="remarks"></a>Comentarios  
 Un elemento `<Method>` de un método genérico aplica su directiva a todas las instancias que no tienen su propia directiva.  
  
 Puede utilizar el atributo `Signature` para especificar la directiva de sobrecarga de un método determinado. Por otra parte, si el atributo `Signature` no está presente, la directiva de tiempo de ejecución se aplica a todas las sobrecargas del método.  
  
 No se puede definir la directiva de reflexión en tiempo de ejecución para un constructor mediante el uso del elemento `<Method>`. Instead, use the `Activate` attribute of the  [<>\>](../../../docs/framework/net-native/assembly-element-net-native.md), [<>\>](../../../docs/framework/net-native/namespace-element-net-native.md), [<>\>](../../../docs/framework/net-native/type-element-net-native.md), or [<>\>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md) element.  
  
## <a name="example"></a>Ejemplo  
 El método `Stringify` del siguiente ejemplo es un método de formato de uso general que utiliza la reflexión para convertir un objeto en su representación de cadena. Además de llamar al valor predeterminado del objeto `ToString` método, el método puede generar una cadena de resultado con formato pasando un objeto `ToString` método una cadena de formato, un <xref:System.IFormatProvider> implementación o ambos. También puede llamar una de las <xref:System.Convert.ToString%2A?displayProperty=fullName> sobrecargas que convierte un número en su representación binaria, octal o hexadecimal.  
  
 [!code-csharp[ProjectN_Reflection#7](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn_reflection/cs/method1.cs#7)]  
  
 El método `Stringify` puede llamarse mediante código como el siguiente:  
  
 [!code-csharp[ProjectN_Reflection#7](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn_reflection/cs/method1.cs#7)]  
  
 Sin embargo, cuando se compila con .NET Native, el ejemplo puede producir un número de excepciones en tiempo de ejecución, incluidos <xref:System.NullReferenceException> y [MissingRuntimeArtifactException](../../../docs/framework/net-native/missingruntimeartifactexception-class-net-native.md) excepciones, esto se produce porque el `Stringify` método está pensado principalmente para admitir el formato dinámico de los tipos primitivos de la biblioteca de clases de .NET Framework. No obstante, sus metadatos no están disponibles en el archivo de directivas predeterminado. Incluso cuando sus metadatos están disponibles, sin embargo, el ejemplo genera [MissingRuntimeArtifactException](../../../docs/framework/net-native/missingruntimeartifactexception-class-net-native.md) excepciones porque adecuado `ToString` implementaciones no se han incluido en el código nativo.  
  
 Estas excepciones pueden eliminarse mediante el uso de la [ <> \> ](../../../docs/framework/net-native/type-element-net-native.md) elemento para definir los tipos cuyos metadatos deben estar presentes y agregando `<Method>` elementos para asegurarse de que la implementación del método sobrecargas que se pueden llamar dinámicamente también está presente. El siguiente es el archivo default.rd.xml que elimina estas excepciones y permite que el ejemplo se ejecute sin errores.  
  
```xml  
  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
  <Application>  
     <Assembly Name="*Application*" Dynamic="Required All" />  
  
     <Type Name = "System.Convert" Browse="Required Public" Dynamic="Required Public" >  
        <Method Name="ToString"    Dynamic ="Required" />  
     </Type>  
     <Type Name="System.Double" Browse="Required Public">  
        <Method Name="ToString" Dynamic="Required" />  
     </Type>  
     <Type Name ="System.Int32" Browse="Required Public" >  
        <Method Name="ToString" Dynamic="Required" />  
     </Type>  
     <Type Name ="System.Int64" Browse="Required Public" >  
        <Method Name="ToString" Dynamic="Required" />  
     </Type>  
     <Namespace Name="System" >  
        <Type Name="Byte" Browse="Required Public" >  
           <Method Name="ToString" Dynamic="Required" />  
        </Type>  
        <Type Name="DateTime" Browse="Required Public" >  
           <Method Name="ToString" Dynamic="Required" />  
        </Type>  
        <Type Name="Decimal" Browse="Required Public" >  
           <Method Name="ToString" Dynamic="Required" />  
        </Type>  
        <Type Name="Guid" Browse ="Required Public" >  
           <Method Name="ToString" Dynamic="Required" />  
        </Type>  
        <Type Name="Int16" Browse="Required Public" >  
           <Method Name="ToString" Dynamic="Required" />  
        </Type>  
        <Type Name="SByte" Browse="Required Public" >  
           <Method Name="ToString" Dynamic="Required" />  
        </Type>  
        <Type Name="Single" Browse="Required Public" >  
          <Method Name="ToString" Dynamic="Required" />           
        </Type>  
        <Type Name="TimeSpan" Browse="Required Public" >  
          <Method Name="ToString" Dynamic="Required" />           
        </Type>  
        <Type Name="UInt16" Browse="Required Public" >  
           <Method Name="ToString" Dynamic="Required" />  
        </Type>  
        <Type Name="UInt32" Browse="Required Public" >  
           <Method Name="ToString" Dynamic="Required" />  
        </Type>  
        <Type Name="UInt64" Browse="Required Public" >  
           <Method Name="ToString" Dynamic="Required" />  
        </Type>  
     </Namespace>  
  </Application>  
</Directives>  
  
```  
  
## <a name="see-also"></a>Vea también  
 [Referencia del archivo de configuración de tiempo de ejecución de directivas (rd.xml)](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)   
 [Elementos de directiva en tiempo de ejecución](../../../docs/framework/net-native/runtime-directive-elements.md)   
 [Configuración de la directiva de directiva en tiempo de ejecución](../../../docs/framework/net-native/runtime-directive-policy-settings.md)   
 [<>\>Elemento](../../../docs/framework/net-native/methodinstantiation-element-net-native.md)