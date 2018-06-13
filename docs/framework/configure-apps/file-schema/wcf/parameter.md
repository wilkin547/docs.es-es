---
title: '&lt;Parámetro&gt;'
ms.date: 03/30/2017
ms.assetid: 0fb41e2d-64f7-44ab-993e-05892eac6d82
ms.openlocfilehash: b9cccfe37e7658afbf2e49555e6c505497598fbb
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32754059"
---
# <a name="ltparametergt"></a>&lt;Parámetro&gt;
Especifica el parámetro genérico cuando el tipo declarado es un tipo genérico.  
  
 \<System.Runtime.Serialization >  
\<dataContractSerializer >  
\<declaredTypes > elemento  
\<Agregar > (elemento) para \<declaredTypes >  
\<knownType > elemento  
\<parámetro > elemento  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<parameter index="integer"  
                      type=String" />  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|índice|Cuando el tipo declarado es un tipo genérico, especifica el parámetro genérico que devolverá el tipo conocido.|  
|tipo|Una cadena que describe el tipo conocido usado para la serialización y deserialización.|  
  
## <a name="index-attribute"></a>Atributo index  
  
|Valor|Descripción|  
|-----------|-----------------|  
|"0"|El primer parámetro en el tipo genérico. Por ejemplo, un <xref:System.Collections.Generic.List%601> tiene solo un parámetro. Si se usa como tipo declarado, el índice estaría establecido en "0".|  
|"1"|El segundo parámetro en un tipo genérico. Por ejemplo, un <xref:System.Collections.Generic.Dictionary%602> tiene dos parámetros. Si el segundo parámetro devuelve el tipo conocido, establezca el atributo de índice en "1".|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<knownType >](../../../../../docs/framework/configure-apps/file-schema/wcf/knowntype.md)|Especifica un tipo conocido que un campo o propiedad de un tipo declarado puede devolver.|  
  
## <a name="remarks"></a>Comentarios  
 Para obtener más información sobre los tipos conocidos, consulte [tipos conocidos de contrato de datos](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) y <xref:System.Runtime.Serialization.DataContractSerializer>.  
  
 Consulte la [ \<dataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) para obtener un ejemplo del uso de este elemento.  
  
 Este elemento de configuración no puede tener al mismo tiempo ambos atributos. Si se establecen ambos atributos, se produce un <xref:System.Configuration.ConfigurationErrorsException>.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
 [Tipos conocidos de contratos de datos](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)  
 [\<dataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)  
 [\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)
