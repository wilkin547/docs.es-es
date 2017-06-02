---
title: "Elemento &lt;GenericParameter&gt; (.NET Native) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: cbd49732-3615-49a5-a900-f96947cdc3e6
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# Elemento &lt;GenericParameter&gt; (.NET Native)
Aplica la directiva al tipo de parámetro de un método o tipo genérico.  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
  
<GenericParameter Name="generic_parameter_name"  
                  Activate="policy_type"  
                  Browse="policy_type"  
                  Dynamic="policy_type"  
                  Serialize="policy_type" />  
                  DataContractSerializer="policy_type"  
                  DataContractJsonSerializer="policy_type"  
                  XmlSerializer="policy_type"  
                  MarshalObject="policy_type"  
                  MarshalDelegate="policy_type"  
                  MarshalStructure="policy_type"  
  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Tipo de atributo|Descripción|  
|---------------|--------------------|-----------------|  
|`Name`|General|Atributo necesario. Nombre del parámetro genérico. Por ejemplo, para el delegado genérico <xref:System.Func%603>, el valor de la `Name` atributo es "TResult" para aplicar directivas de tiempo de ejecución al valor devuelto del delegado.\</T1, T2, TResult>|  
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
|*generic_parameter_name*|Atributo necesario. Nombre del parámetro de tipo genérico. Por ejemplo, para el delegado genérico <xref:System.Func%603>, *generic_parameter_name* valor "TResult" aplica la directiva de tiempo de ejecución al valor devuelto del delegado.\</T1, T2, TResult>|  
  
## <a name="all-other-attributes"></a>Resto de atributos  
  
|Valor|Descripción|  
|-----------|-----------------|  
|*policy_setting*|Configuración que se va a aplicar a este tipo de directiva. Los valores posibles son `All`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` y `Required All`. Para obtener más información, consulte [configuración de directiva de directiva en tiempo de ejecución](../../../docs/framework/net-native/runtime-directive-policy-settings.md).|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[<>\>](../../../docs/framework/net-native/method-element-net-native.md)|Aplica la directiva de reflexión en tiempo de ejecución a un constructor o un método.|  
|[<>\>](../../../docs/framework/net-native/type-element-net-native.md)|Aplica la directiva de reflexión en tiempo de ejecución a un tipo determinado, como una clase o una estructura.|  
  
## <a name="remarks"></a>Comentarios  
 El `<GenericParameter>` es un elemento secundario de uno de ellos la [ <> \> ](../../../docs/framework/net-native/method-element-net-native.md) o [ <> \> ](../../../docs/framework/net-native/type-element-net-native.md) elemento y se utiliza para aplicar directivas a un parámetro de tipo genérico concreto especificado por su nombre en la firma de método o tipo genérica.  
  
 El elemento `<GenericParameter>` es de mayor utilidad cuando se usa con serializadores. En el ejemplo siguiente se utiliza la `<GenericParameter>` elemento que se va a aplicar la directiva al tipo `T` en las llamadas al serializador JSON NewtonSoft [JsonConvert.DeserializeObject<>\>(cadena)](http://james.newtonking.com/json/help/index.html?topic=html/T_Newtonsoft_Json_JsonConvert.htm) sobrecargas del método.  
  
```xml  
  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <Type Name="Newtonsoft.Json.JsonConvert" >  
      <Method Name="DeserializeObject{T}">  
         <GenericParameter Name="T" Serialize="Required All" />  
      </Method>  
   </Type>  
</Directives>  
  
```  
  
## <a name="see-also"></a>Vea también  
 [<>\>Elemento](../../../docs/framework/net-native/method-element-net-native.md)   
 [<>\>Elemento](../../../docs/framework/net-native/type-element-net-native.md)   
 [Referencia del archivo de configuración de tiempo de ejecución de directivas (rd.xml)](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)   
 [Configuración de la directiva de directiva en tiempo de ejecución](../../../docs/framework/net-native/runtime-directive-policy-settings.md)   
 [Elementos de directiva en tiempo de ejecución](../../../docs/framework/net-native/runtime-directive-elements.md)