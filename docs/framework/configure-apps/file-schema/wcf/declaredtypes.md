---
title: <declaredTypes>
ms.date: 03/30/2017
helpviewer_keywords:
- dataContractSerializer element
- declaredTypes element
- DataContractSerializer
- KnownTypes
- <declaredTypes> element
ms.assetid: f35184e4-9d9e-4d37-8fb4-d5b58220eb3e
ms.openlocfilehash: c45a4e67d0a2d98c0e9c1a91e07f25b81370244c
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398063"
---
# \<declaredTypes>
Contiene los tipos conocidos que <xref:System.Runtime.Serialization.DataContractSerializer> usa al deserializar.  
  
 Para obtener más información sobre los contratos de datos y los tipos conocidos, consulte [Data Contract known Types](../../../wcf/feature-details/data-contract-known-types.md).  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.runtime.serialization>**](system-runtime-serialization.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<dataContractSerializer>**](datacontractserializer.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<declaredTypes>**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<configuration>
  <system.runtime.serialization>
    <dataContractSerializer>
      <declaredTypes>
        <add type="String ">
          <knownType type="String">
            <parameter index="Integer"/>
          </knownType>
        </add>
      </declaredTypes>
    <dataContractSerializer>
  </system.runtime.serialization>
</configuration>
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
 Ninguno.  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<add>](add-of-declaredtypes-element.md)|Agrega tipos que requieren tipos conocidos.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<dataContractSerializer>](datacontractserializer-of-system-runtime-serialization.md)|Contiene los datos de configuración para <xref:System.Runtime.Serialization.DataContractSerializer>.|  
  
## <a name="remarks"></a>Comentarios  
 Para obtener más información sobre los tipos conocidos, vea [tipos conocidos de contratos de datos](../../../wcf/feature-details/data-contract-known-types.md) y <xref:System.Runtime.Serialization.DataContractSerializer> .  
  
## <a name="example"></a>Ejemplo  
 En el código XML siguiente se muestran los tipos declarados y los tipos conocidos agregados a un `DataContractSerializer` elemento. El ejemplo muestra tres tipos que se va a agregar. El primero es un tipo personalizado denominado "Orders" que usa un tipo conocido denominado "Item". El segundo el tipo declarado es <xref:System.Collections.Generic.List%601> que usa `Item` como un tipo conocido. Finalmente, el tercer tipo declarado es <xref:System.Collections.Generic.Dictionary%602>. El tipo de clase <xref:System.Collections.Generic.Dictionary%602> es un tipo genérico, con dos parámetros de tipo. El primero representa la clave y el segundo representa el valor. El ejemplo siguiente agrega <xref:System.Collections.Generic.List%601> del segundo tipo (el valor) a la lista de tipos conocidos. Debe usar el atributo `index` para especificar qué parámetro de tipo se va a usar en el tipo conocido. En este caso, el atributo de índice indica el tipo de valor establecido en "1" (la colección está basada en cero).  
  
```xml  
<configuration>
  <system.runtime.serialization>
    <dataContractSerializer>
      <declaredTypes>
        <add type="Examples.Types.Orders, SerializationTypes, Version = 2.0.0.0, Culture = neutral, PublicKeyToken=null">
          <knownType type="Examples.Types.Item, SerializationTypes, Version=2.0.0.0, Culture=neutral, PublicKey=null" />
        </add>
        <add type="System.Collections.Generic.List`1, SerializationTypes, Version = 2.0.0.0, Culture = neutral, PublicKeyToken=null">
          <knownType type="Examples.Types.Item, SerializationTypes, Version=2.0.0.0, Culture=neutral, PublicKey=null" />
        </add>
        <add type="System.Collections.Generic.Dictionary`2, SerializationTypes, Version = 2.0.0.0, Culture = neutral, PublicKeyToken=null">
          <knownType type="System.Collections.Generic.List`1, SerializationTypes, Version = 2.0.0.0, Culture = neutral, PublicKeyToken=null">
            <parameter index="1"/>
          </knownType>
        </add>
      </declaredTypes>
    <dataContractSerializer>
  </system.runtime.serialization>
</configuration>
```  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [\<dataContractSerializer>](datacontractserializer-element.md)
- [Tipos conocidos de contratos de datos](../../../wcf/feature-details/data-contract-known-types.md)
- [\<add>](add-of-declaredtypes-element.md)
