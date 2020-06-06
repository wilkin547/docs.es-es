---
title: <add>del <declaredTypes> elemento
ms.date: 03/30/2017
helpviewer_keywords:
- data contracts
- dataContractSerializer element
- DataContractSerializer
- DataContractAttribute
ms.assetid: c3d37ae4-8f1c-463f-b195-658c5a7e90a1
ms.openlocfilehash: a001e8743b2c24f68b1b23cbccf3e5ac162c4e71
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70400654"
---
# <a name="add-of-declaredtypes-element"></a>\<add>del \<declaredTypes> elemento
Agrega un tipo usado por <xref:System.Runtime.Serialization.DataContractSerializer> durante la deserialización. Cada tipo declarado incluye los tipos conocidos que se devolverán como un campo o propiedad del tipo declarado.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.serialization>**](system-runtime-serialization.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<dataContractSerializer>**](datacontractserializer.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<declaredTypes>**](declaredtypes.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<add type="String">
  <knownType type="String">
    <parameter index="Integer"
               type="String" />
  </knownType>
</add>
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|type|Atributo de cadena necesario.<br /><br /> Especifica el nombre del tipo (incluido el espacio de nombres), nombre de ensamblado, número de versión, referencia cultural y símbolo (token) de clave pública.|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<knownType>](knowntype.md)|Especifica el tipo conocido del tipo declarado que se va a agregar. Si el tipo declarado es un tipo genérico, también debe agregar un elemento de parámetro al elemento `<knownType>` para especificar qué parámetro genérico se usa para devolver el tipo conocido.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<declaredTypes>](declaredtypes.md)|Contiene los tipos que requieren tipos conocidos durante la deserialización por <xref:System.Runtime.Serialization.DataContractSerializer>.|  
  
## <a name="remarks"></a>Comentarios  
 Para obtener más información sobre los tipos conocidos, vea [tipos conocidos de contratos de datos](../../../wcf/feature-details/data-contract-known-types.md) y <xref:System.Runtime.Serialization.DataContractSerializer> .  
  
 Vea [\<dataContractSerializer>](datacontractserializer-element.md) para obtener un ejemplo de uso de este elemento.  
  
> [!NOTE]
> Si agrega el tipo <xref:System.Object> como `<declaredType>` , a continuación, se inicia <xref:System.Configuration.ConfigurationErrorsException>. Esto se debe a que el tipo <xref:System.Object> no se puede usar como un tipo declarado en configuración.  
  
## <a name="example"></a>Ejemplo  
  
```xml  
<add type="MyCompany.Library.Shape,
           MyAssembly, Version=2.0.0.0, Culture=neutral,
           PublicKeyToken=XXXXXX, processorArchitecture=MSIL">
  <knownType type="MyCompany.Library.Circle,
                   MyAssembly, Version=2.0.0.0, Culture=neutral,
                   PublicKeyToken=XXXXXX,
                   processorArchitecture=MSIL" />
</add>
```  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [Tipos conocidos de contratos de datos](../../../wcf/feature-details/data-contract-known-types.md)
- [\<dataContractSerializer>](datacontractserializer-element.md)
- [\<add>de\<declaredTypes>](add-of-declaredtypes-element.md)
