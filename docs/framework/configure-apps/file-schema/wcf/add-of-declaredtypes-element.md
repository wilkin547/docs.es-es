---
title: <add> de <declaredTypes> elemento
ms.date: 03/30/2017
helpviewer_keywords:
- data contracts
- dataContractSerializer element
- DataContractSerializer
- DataContractAttribute
ms.assetid: c3d37ae4-8f1c-463f-b195-658c5a7e90a1
ms.openlocfilehash: 9b280a63e85beac3231bc1a414430239bea4a1f8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59111519"
---
# <a name="add-of-declaredtypes-element"></a>\<Agregar > de \<declaredTypes > elemento
Agrega un tipo usado por <xref:System.Runtime.Serialization.DataContractSerializer> durante la deserialización. Cada tipo declarado incluye los tipos conocidos que se devolverán como un campo o propiedad del tipo declarado.  
  
 system.runtime.serialization  
\<dataContractSerializer>  
\<declaredTypes>  
\<Agregar > de \<declaredTypes >  
  
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
|[\<knownType>](../../../../../docs/framework/configure-apps/file-schema/wcf/knowntype.md)|Especifica el tipo conocido del tipo declarado que se va a agregar. Si el tipo declarado es un tipo genérico, también debe agregar un elemento de parámetro al elemento `<knownType>` para especificar qué parámetro genérico se usa para devolver el tipo conocido.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<declaredTypes>](../../../../../docs/framework/configure-apps/file-schema/wcf/declaredtypes.md)|Contiene los tipos que requieren tipos conocidos durante la deserialización por <xref:System.Runtime.Serialization.DataContractSerializer>.|  
  
## <a name="remarks"></a>Comentarios  
 Para obtener más información sobre los tipos conocidos, consulte [Data Contract Known Types](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) y <xref:System.Runtime.Serialization.DataContractSerializer>.  
  
 Consulte la [ \<dataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) para obtener un ejemplo del uso de este elemento.  
  
> [!NOTE]
>  Si agrega el tipo <xref:System.Object> como `<declaredType>` , a continuación, se inicia <xref:System.Configuration.ConfigurationErrorsException>. Esto se debe a que el tipo <xref:System.Object> no se puede usar como un tipo declarado en configuración.  
  
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
  
## <a name="see-also"></a>Vea también

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [Tipos conocidos de contratos de datos](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)
- [\<dataContractSerializer>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)
- [\<Agregar > de \<declaredTypes >](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)
