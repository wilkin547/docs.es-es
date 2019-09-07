---
title: <parameter>
ms.date: 03/30/2017
ms.assetid: 0fb41e2d-64f7-44ab-993e-05892eac6d82
ms.openlocfilehash: 07fa410109a7bd2fa315132c4737301698bb3a93
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400112"
---
# <a name="parameter"></a>\<> de parámetros
Especifica el parámetro genérico cuando el tipo declarado es un tipo genérico.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. Runtime. Serialization >** ](system-runtime-serialization.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> dataContractSerializer**](datacontractserializer.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> declaredTypes**](declaredtypes.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Agregar >** ](add-of-declaredtypes-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> knownType**](knowntype.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> de parámetros**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<parameter index="Integer"
           type="String" />
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|DESCRIPCIÓN|  
|---------------|-----------------|  
|index|Cuando el tipo declarado es un tipo genérico, especifica el parámetro genérico que devolverá el tipo conocido.|  
|type|Una cadena que describe el tipo conocido usado para la serialización y deserialización.|  
  
## <a name="index-attribute"></a>Atributo index  
  
|Valor|DESCRIPCIÓN|  
|-----------|-----------------|  
|"0"|El primer parámetro en el tipo genérico. Por ejemplo, un <xref:System.Collections.Generic.List%601> tiene solo un parámetro. Si se usa como tipo declarado, el índice estaría establecido en "0".|  
|"1"|El segundo parámetro en un tipo genérico. Por ejemplo, un <xref:System.Collections.Generic.Dictionary%602> tiene dos parámetros. Si el segundo parámetro devuelve el tipo conocido, establezca el atributo de índice en "1".|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|DESCRIPCIÓN|  
|-------------|-----------------|  
|[\<knownType>](knowntype.md)|Especifica un tipo conocido que un campo o propiedad de un tipo declarado puede devolver.|  
  
## <a name="remarks"></a>Comentarios  
 Para obtener más información sobre los tipos conocidos, vea [tipos conocidos](../../../wcf/feature-details/data-contract-known-types.md) de <xref:System.Runtime.Serialization.DataContractSerializer>contratos de datos y.  
  
 Vea el [ \<> dataContractSerializer](datacontractserializer-element.md) para obtener un ejemplo del uso de este elemento.  
  
 Este elemento de configuración no puede tener al mismo tiempo ambos atributos. Si se establecen ambos atributos, se produce un <xref:System.Configuration.ConfigurationErrorsException>.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [Tipos conocidos de contratos de datos](../../../wcf/feature-details/data-contract-known-types.md)
- [\<dataContractSerializer>](datacontractserializer-element.md)
- [\<add>](add-of-declaredtypes-element.md)
