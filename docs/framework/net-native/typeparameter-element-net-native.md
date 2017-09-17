---
title: Elemento &lt;TypeParameter&gt; (.NET Native)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d37bb1b7-1ddc-4c6d-8ecf-583f804a2479
caps.latest.revision: 11
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: d170544c6b0bd5d1a7c70e707506bd36ac65ab39
ms.contentlocale: es-es
ms.lasthandoff: 08/21/2017

---
# <a name="lttypeparametergt-element-net-native"></a>Elemento &lt;TypeParameter&gt; (.NET Native)
Aplica la directiva al tipo representado por un argumento Type pasado a un método.  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<Parameter Name="parameter_name"  
           Activate="policy_type"  
           Browse="policy_type"  
           Dynamic="policy_type"  
           Serialize="policy_type"  
           DataContractSerializer="policy_type"  
           DataContractJsonSerializer="policy_type"  
           XmlSerializer="policy_type"  
           MarshalObject="policy_type"  
           MarshalDelegate="policy_type"  
           MarshalStructure="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Tipo de atributo|Descripción|  
|---------------|--------------------|-----------------|  
|`Name`|General|Atributo necesario. Nombre del parámetro de tipo <xref:System.Type>. Por ejemplo, en la firma de método `Type.GetInterfaceMap(Type interfaceType)`, el valor del atributo `Name` es "interfaceType".|  
|`Activate`|Reflexión|Atributo opcional. Controla el acceso en tiempo de ejecución a los constructores para permitir la activación de instancias.|  
|`Browse`|Reflexión|Atributo opcional. Controla la consulta para obtener información sobre los elementos de programa, pero no permite el acceso en tiempo de ejecución.|  
|`Dynamic`|Reflexión|Atributo opcional. Controla el acceso en tiempo de ejecución a todos los miembros de tipo (incluidos constructores, métodos, campos, propiedades y eventos) para permitir la programación dinámica.|  
|`Serialize`|Serialización|Atributo opcional. Controla el acceso en tiempo de ejecución a constructores, campos y propiedades para permitir que bibliotecas como el serializador JSON Newtonsoft puedan serializar y deserializar instancias de tipo.|  
|`DataContractSerializer`|Serialización|Atributo opcional. Controla la directiva de serialización que usa la clase <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=fullName>.|  
|`DataContractJsonSerializer`|Serialización|Atributo opcional. Controla la directiva de serialización JSON que usa la clase <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=fullName>.|  
|`XmlSerializer`|Serialización|Atributo opcional. Controla la directiva de serialización XML que usa la clase <xref:System.Xml.Serialization.XmlSerializer?displayProperty=fullName>.|  
|`MarshalObject`|Interop|Atributo opcional. Controla la directiva de serialización de tipos de referencia a Windows Runtime y COM.|  
|`MarshalDelegate`|Interop|Atributo opcional. Controla la directiva de serialización de tipos de delegado como punteros de función a código nativo.|  
|`MarshalStructure`|Interop|Atributo opcional. Controla la directiva de cálculo de referencias de tipos de valor a código nativo.|  
  
## <a name="name-attribute"></a>Name (atributo)  
  
|Valor|Descripción|  
|-----------|-----------------|  
|*parameter_name*|Nombre del parámetro de tipo <xref:System.Type>. Por ejemplo, en la firma de método `Type.GetInterfaceMap(Type interfaceType)`, el valor del atributo `Name` es "interfaceType".|  
  
## <a name="all-other-attributes"></a>Resto de atributos  
  
|Valor|Descripción|  
|-----------|-----------------|  
|*policy_setting*|Configuración que se va a aplicar a este tipo de directiva. Los valores posibles son `All`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` y `Required All`. Para obtener más información, vea [Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md) (Configuración de directiva de la directiva en tiempo de ejecución).|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<Method>](../../../docs/framework/net-native/method-element-net-native.md)|Aplica la directiva de reflexión en tiempo de ejecución a un constructor o un método.|  
  
## <a name="remarks"></a>Comentarios  
 El elemento `<TypeParameter>` es similar al elemento [\<Parameter>](../../../docs/framework/net-native/parameter-element-net-native.md), salvo que únicamente se puede aplicar a los parámetros de tipo <xref:System.Type>. Aplica la directiva a cualquier tipo que se represente en tiempo de ejecución mediante el argumento de tipo especificado por el atributo `Name`.  
  
 Por ejemplo, el serializador JSON NewtonSoft incluye un método `JsonConvert.DeserializeObject(String value, Type type)` estático. Las siguientes directivas de reflexión:  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <Type Name="Newtonsoft.Json.JsonConvert" >  
      <Method Name="DeserializeObject">  
         <GenericParameter Name="type" Serialize="Required All" />  
      </Method>  
   </Type>  
</Directives>  
```  
  
 especifican que debe haber disponibles metadatos para el tipo en tiempo de ejecución representado por el argumento `type` para poder realizar la serialización. Si estas directivas en tiempo de ejecución se aplican a un proyecto que incluye el siguiente código fuente:  
  
```csharp  
Type t = typeof(StockQuote);  
Object obj = JsonConvert.DeserializeObject(data, t);  
```  
  
 las directivas de reflexión hacen que haya metadatos disponibles para el tipo `StockQuote` para el serializador JSON NewtonSoft en tiempo de ejecución.  
  
## <a name="see-also"></a>Vea también  
 [Elemento \<Method>](../../../docs/framework/net-native/method-element-net-native.md)   
 [Runtime Directives (rd.xml) Configuration File Reference](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)  (Referencia del archivo de configuración de directivas en tiempo de ejecución [rd.xml])  
 [Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md)  (Configuración de directiva de la directiva en tiempo de ejecución)  
 [Runtime Directive Elements (Elementos de directivas en tiempo de ejecución)](../../../docs/framework/net-native/runtime-directive-elements.md)

