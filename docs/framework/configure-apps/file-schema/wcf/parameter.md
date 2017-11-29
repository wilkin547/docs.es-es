---
title: "&lt;parámetro&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0fb41e2d-64f7-44ab-993e-05892eac6d82
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: e9db1921e2a6ee1ae2780f744c45fdb25efbf797
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ltparametergt"></a>&lt;parámetro&gt;
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
 [!INCLUDE[crabout](../../../../../includes/crabout-md.md)]los tipos conocidos, consulte [tipos conocidos de contrato de datos](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) y <xref:System.Runtime.Serialization.DataContractSerializer>.  
  
 Consulte la [ \<dataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) para obtener un ejemplo del uso de este elemento.  
  
 Este elemento de configuración no puede tener al mismo tiempo ambos atributos. Si se establecen ambos atributos, se produce un <xref:System.Configuration.ConfigurationErrorsException>.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
 [Los tipos conocidos de contrato de datos](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)  
 [\<dataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)  
 [\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)
