---
title: <knownType>
ms.date: 03/30/2017
ms.assetid: ee2b7be3-7148-4a3a-b861-48e7330615e5
ms.openlocfilehash: a0794314cfcb87df00d66b6832356fb130787eba
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69928868"
---
# <a name="knowntype"></a>\<knownType>
Especifica un tipo que <xref:System.Runtime.Serialization.DataContractSerializer> va a usar durante la deserialización. El elemento especifica un "tipo conocido" que es devuelto por un campo o propiedad de un "tipo declarado." Para obtener más información, vea [tipos conocidos de contratos de datos](../../../wcf/feature-details/data-contract-known-types.md).  
  
 \<system.runtime.serialization>  
\<dataContractSerializer>  
\<declaredTypes >, elemento  
\<Agregar > de \<declaredTypes >  
\<knownType >, elemento  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<knownType type="String">
  <parameter index="Integer"
             type="String" />
</knownType>
```  
  
## <a name="type"></a>Type  
 `string`  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|DESCRIPCIÓN|  
|---------------|-----------------|  
|type|Especifica el tipo (incluso el espacio de nombres), nombre de ensamblado, versión, referencia cultural y token de clave pública.|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|DESCRIPCIÓN|  
|-------------|-----------------|  
|[\<> de parámetros](parameter.md)|Especifica un índice de parámetro cuando el tipo declarado es un tipo genérico.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|DESCRIPCIÓN|  
|-------------|-----------------|  
|[\<add>](add-of-declaredtypes-element.md)|Agrega un tipo declarado a la colección de tipos declarados.|  
  
## <a name="remarks"></a>Comentarios  
 Para obtener más información sobre los tipos conocidos, vea [tipos conocidos](../../../wcf/feature-details/data-contract-known-types.md) de <xref:System.Runtime.Serialization.DataContractSerializer>contratos de datos y.  
  
 Vea el [ \<> dataContractSerializer](datacontractserializer-element.md) para obtener un ejemplo del uso de este elemento.  
  
## <a name="example"></a>Ejemplo  
  
```xml  
<add type="MyCompany.Library.Shape,
           MyAssembly, Version=2.0.0.0, Culture=neutral,
           PublicKeyToken=XXXXXX, processorArchitecture=MSIL">
  <knownType type="MyCompany.Library.Circle,
                   MyAssembly, Version=2.0.0.0, Culture=neutral,
                   PublicKeyToken=XXXXXX,
                   processorArchitecture=MSIL"/>
</add>
```  
  
## <a name="see-also"></a>Vea también

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [Tipos conocidos de contratos de datos](../../../wcf/feature-details/data-contract-known-types.md)
- [\<dataContractSerializer>](datacontractserializer-element.md)
- [\<add>](add-of-declaredtypes-element.md)
