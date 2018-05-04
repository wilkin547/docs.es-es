---
title: '&lt;knownType&gt;'
ms.date: 03/30/2017
ms.assetid: ee2b7be3-7148-4a3a-b861-48e7330615e5
ms.openlocfilehash: b2445f12f1eaac03b3f3ab66f3d13a5f465a1133
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltknowntypegt"></a>&lt;knownType&gt;
Especifica un tipo que <xref:System.Runtime.Serialization.DataContractSerializer> va a usar durante la deserialización. El elemento especifica un "tipo conocido" que es devuelto por un campo o propiedad de un "tipo declarado." Para obtener más información, consulte [tipos conocidos de contrato de datos](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).  
  
 \<System.Runtime.Serialization >  
\<dataContractSerializer >  
\<declaredTypes > elemento  
\<Agregar > de \<declaredTypes >  
\<knownType > elemento  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<knownType type="String">  
     <parameter index="Integer"  
                type="String" />  
</knownType>  
```  
  
## <a name="type"></a>Tipo  
 `string`  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|tipo|Especifica el tipo (incluso el espacio de nombres), nombre de ensamblado, versión, referencia cultural y token de clave pública.|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<parámetro >](../../../../../docs/framework/configure-apps/file-schema/wcf/parameter.md)|Especifica un índice de parámetro cuando el tipo declarado es un tipo genérico.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)|Agrega un tipo declarado a la colección de tipos declarados.|  
  
## <a name="remarks"></a>Comentarios  
 Para obtener más información sobre los tipos conocidos, consulte [tipos conocidos de contrato de datos](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) y <xref:System.Runtime.Serialization.DataContractSerializer>.  
  
 Consulte la [ \<dataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) para obtener un ejemplo del uso de este elemento.  
  
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
 <xref:System.Runtime.Serialization.DataContractSerializer>  
 [Tipos conocidos de contratos de datos](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)  
 [\<dataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)  
 [\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)
