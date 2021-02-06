---
description: 'Más información sobre: <Parameter> elemento (.net Native)'
title: <Parameter> Elemento (.NET Native)
ms.date: 03/30/2017
ms.assetid: 22aaa1f3-596f-4733-93db-f4bcabcb5240
ms.openlocfilehash: 53b84027e8393e0a799d9652767d173c2787cd27
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99662798"
---
# <a name="parameter-element-net-native"></a>\<Parameter> Elemento (.NET Native)

Aplica la directiva de reflexión al tipo del argumento que se pasa a un método.  
  
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
|`Name`|General|Atributo necesario. Nombre del parámetro. Por ejemplo, para la signatura del método `String.CompareTo(Object value)`, el valor del atributo `Name` es "value".|  
|`Activate`|Reflexión|Atributo opcional. Controla el acceso en tiempo de ejecución a los constructores para permitir la activación de instancias.|  
|`Browse`|Reflexión|Atributo opcional. Controla la consulta para obtener información sobre los elementos de programa, pero no permite el acceso en tiempo de ejecución.|  
|`Dynamic`|Reflexión|Atributo opcional. Controla el acceso en tiempo de ejecución a todos los miembros de tipo (incluidos constructores, métodos, campos, propiedades y eventos) para permitir la programación dinámica.|  
|`Serialize`|Serialización|Atributo opcional. Controla el acceso en tiempo de ejecución a constructores, campos y propiedades para permitir que bibliotecas como el serializador JSON Newtonsoft puedan serializar y deserializar instancias de tipo.|  
|`DataContractSerializer`|Serialización|Atributo opcional. Controla la directiva de serialización que usa la clase <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>.|  
|`DataContractJsonSerializer`|Serialización|Atributo opcional. Controla la directiva de serialización JSON que usa la clase <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>.|  
|`XmlSerializer`|Serialización|Atributo opcional. Controla la directiva de serialización XML que usa la clase <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>.|  
|`MarshalObject`|Interop|Atributo opcional. Controla la directiva de cálculo de referencias de tipos de referencia para WinRT y COM.|  
|`MarshalDelegate`|Interop|Atributo opcional. Controla la directiva de serialización de tipos de delegado como punteros de función a código nativo.|  
|`MarshalStructure`|Interop|Atributo opcional. Controla la directiva de cálculo de referencias de tipos de valor a código nativo.|  
  
## <a name="name-attribute"></a>Name (atributo)  
  
|Value|Descripción|  
|-----------|-----------------|  
|*parameter_name*|Nombre del parámetro de método al que se aplica la directiva. Por ejemplo, para la signatura del método `String.CompareTo(Object value)`, el valor del atributo `Name` es "value".|  
  
## <a name="all-other-attributes"></a>Resto de atributos  
  
|Value|Descripción|  
|-----------|-----------------|  
|*policy_setting*|Configuración que se va a aplicar a este tipo de directiva. Los valores posibles son `All`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` y `Required All`. Para obtener más información, vea [Runtime Directive Policy Settings](runtime-directive-policy-settings.md) (Configuración de directiva de la directiva en tiempo de ejecución).|  
  
### <a name="child-elements"></a>Elementos secundarios  

 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<Method>](method-element-net-native.md)|Aplica la directiva de reflexión en tiempo de ejecución a un constructor o método.|  
  
## <a name="remarks"></a>Observaciones  

 El `<Parameter>` elemento es un elemento secundario del [\<Method>](method-element-net-native.md) elemento y se utiliza para aplicar la Directiva a un parámetro de método determinado. El parámetro de método determinado se especifica mediante el nombre en lugar del tipo. Debe haber presente al menos un atributo que represente un tipo de directiva, como `Activate` o `Dynamic`.  
  
## <a name="see-also"></a>Vea también

- [Elemento \<Method>](method-element-net-native.md)
- [Referencia del archivo de configuración de directivas en tiempo de ejecución (rd.xml)](runtime-directives-rd-xml-configuration-file-reference.md)
- [Configuración de directiva de la directiva en tiempo de ejecución](runtime-directive-policy-settings.md)
- [Elementos de directivas en tiempo de ejecución](runtime-directive-elements.md)
