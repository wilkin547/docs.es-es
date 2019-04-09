---
title: <Assembly> Elemento (.NET Native)
ms.date: 03/30/2017
ms.assetid: cfe629eb-1106-4113-86e1-052f402d8d8b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c0788c05edace2142d348c679c73aa1b4404ce75
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59137857"
---
# <a name="assembly-element-net-native"></a>\<Ensamblado > elemento (.NET Native)
Aplica la directiva de reflexión en tiempo de ejecución a todos los tipos en un ensamblado especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<Assembly Name="assembly_name"   
          Activate="policy_setting"  
          Browse="policy_setting"  
          Dynamic="policy_setting"  
          Serialize="policy_setting"  
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
|`Name`|General|Atributo necesario. Especifica el nombre simple de un ensamblado.|  
|`Activate`|Reflexión|Atributo opcional. Controla el acceso en tiempo de ejecución a los constructores para permitir la activación de instancias.|  
|`Browse`|Reflexión|Atributo opcional. Controla la consulta para obtener información acerca de los tipos en el ensamblado o enumerar los tipos en el ensamblado, pero no permite el acceso dinámico en tiempo de ejecución.|  
|`Dynamic`|Reflexión|Atributo opcional. Controla el acceso en tiempo de ejecución a todos los miembros de tipo (incluidos constructores, métodos, campos, propiedades y eventos) para permitir la programación dinámica.|  
|`Serialize`|Serialización|Atributo opcional. Controla el acceso en tiempo de ejecución a constructores, campos y propiedades para permitir que bibliotecas como el serializador JSON Newtonsoft puedan serializar y deserializar instancias de tipo.|  
|`DataContractSerializer`|Serialización|Atributo opcional. Controla la directiva de serialización que usa la clase <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>.|  
|`DataContractJsonSerializer`|Serialización|Atributo opcional. Controla la directiva de serialización JSON que usa la clase <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType>.|  
|`XmlSerializer`|Serialización|Atributo opcional. Controla la directiva de serialización XML que usa la clase <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>.|  
|`MarshalObject`|Interop|Atributo opcional. Controla la directiva de serialización de tipos de referencia a Windows Runtime y COM.|  
|`MarshalDelegate`|Interop|Atributo opcional. Controla la directiva de serialización de tipos de delegado como punteros de función a código nativo.|  
|`MarshalStructure`|Interop|Atributo opcional. Controla la directiva para calcular referencias de estructuras a código nativo.|  
  
## <a name="name-attribute"></a>Name (atributo)  
  
|Valor|Descripción|  
|-----------|-----------------|  
|*assembly_name*|Nombre simple del ensamblado sin la extensión de archivo. Este atributo corresponde a la propiedad <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType>. Por ejemplo, el nombre de un ensamblado denominado Extensions.dll es "Extensions".<br /><br /> También puede especificar la cadena literal `*Application*` para aplicar la directiva a todos los ensamblados en el paquete de la aplicación, independientemente de si se han cargado o no. `*Application*` nunca aplica una directiva a los ensamblados de .NET Framework.|  
  
## <a name="all-other-attributes"></a>Resto de atributos  
  
|Valor|Descripción|  
|-----------|-----------------|  
|*policy_setting*|Configuración que se va a aplicar a este tipo de directiva para todos los tipos en el ensamblado. Los valores posibles son `All`, `Auto`, `Excluded`, `Public`, `PublicAndInternal`, `Required Public`, `Required PublicAndInternal` y `Required All`. Para obtener más información, vea [Runtime Directive Policy Settings](../../../docs/framework/net-native/runtime-directive-policy-settings.md) (Configuración de directiva de la directiva en tiempo de ejecución).|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<Namespace >](../../../docs/framework/net-native/namespace-element-net-native.md)|Aplica la directiva de reflexión a todos los tipos en un espacio de nombres secundario.|  
|[\<tipo >](../../../docs/framework/net-native/type-element-net-native.md)|Aplica la directiva de reflexión a un tipo.|  
|[\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)|Aplica la directiva de reflexión a un tipo genérico construido.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<Aplicación >](../../../docs/framework/net-native/application-element-net-native.md)|Sirve de contenedor de los tipos y miembros de tipo de la aplicación cuyos metadatos están disponibles para la reflexión en tiempo de ejecución. El elemento [\<Application>](../../../docs/framework/net-native/application-element-net-native.md) puede tener cero, uno o más elementos `<Assembly>`.|  
|[\<Biblioteca >](../../../docs/framework/net-native/library-element-net-native.md)|Define el ensamblado que contiene los tipos y miembros de tipo cuyos metadatos están disponibles para la reflexión en tiempo de ejecución. El elemento [\<Library>](../../../docs/framework/net-native/library-element-net-native.md) puede tener cero o un elemento `<Assembly>`.|  
  
## <a name="remarks"></a>Comentarios  
 El elemento `<Assembly>` define la directiva en tiempo de ejecución para todos los tipos en un ensamblado. Difiere del elemento [\<Library>](../../../docs/framework/net-native/library-element-net-native.md), que especifica una biblioteca pero depende de sus elementos secundarios para definir la directiva de reflexión en tiempo de ejecución. El elemento `<Assembly>` se aplica a todos los tipos en un ensamblado, a menos que un elemento secundario los haya invalidado.  
  
 En el siguiente ejemplo se muestra cómo aplicar la directiva en tiempo de ejecución a todos los tipos de los ensamblados del paquete de la aplicación al asignar un valor "*Application\*" al atributo `Name`. El elemento `<Assembly>` debe ser un elemento secundario del elemento [\<Application>](../../../docs/framework/net-native/application-element-net-native.md).  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">   
  <Application>   
     <Assembly Name="*Application*" Dynamic="Required All" />   
  </Application>   
</Directives>  
```  
  
 Los atributos `Activate`, `Browse`, `Dynamic` y `Serialize` son opcionales. Sin embargo, el elemento `<Assembly>` debe contener al menos uno de estos atributos.  
  
## <a name="see-also"></a>Vea también

- [Configuración de directiva de la directiva en tiempo de ejecución](../../../docs/framework/net-native/runtime-directive-policy-settings.md)
- [Referencia del archivo de configuración de directivas en tiempo de ejecución (rd.xml)](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)
- [Elementos de directivas en tiempo de ejecución](../../../docs/framework/net-native/runtime-directive-elements.md)
