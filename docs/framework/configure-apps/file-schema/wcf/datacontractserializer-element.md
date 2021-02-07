---
description: 'Más información acerca de: <dataContractSerializer>'
title: <dataContractSerializer>
ms.date: 03/30/2017
helpviewer_keywords:
- dataContractSerializer element
- <dataContractSerializer> element
- DataContractSerializer
- KnownTypes
ms.assetid: f41fb4d5-24e7-4059-8010-286a30bfea93
ms.openlocfilehash: 0705a40f55d76ef46a7debcd4ecfb5235c7c0d21
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99754438"
---
# \<dataContractSerializer>

Contiene los datos de configuración para <xref:System.Runtime.Serialization.DataContractSerializer>. Este elemento se produce en dos jerarquías diferentes. Uno aparece en la lista de la siguiente sección, Jerarquía del esquema, y el otro se enumera en la sección Comentarios.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dataContractSerializer>**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<dataContractSerializer ignoreExtensionDataObject="Boolean"
                        maxItemsInObjectGraph="Integer" />
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  

 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|ignoreExtensionDataObject|Un valor booleano que especifica si se omiten los datos proporcionados por el punto de conexión cuando se serializa o deserializa. Este atributo se puede configurar sólo en `<dataContractSerializer>` bajo el elemento `<behavior>`.|  
|maxItemsInObjectGraph|Un entero que especifica el número máximo de elementos para serializar o deserializar. Este atributo es 65536.|  
  
### <a name="child-elements"></a>Elementos secundarios  

 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-servicebehaviors.md)|Una colección de valores para el comportamiento de un servicio.|  
|[\<system.runtime.serialization>](system-runtime-serialization.md)|Representa el elemento raíz para la sección de espacio de nombres <xref:System.Runtime.Serialization> y contiene elementos para establecer opciones de <xref:System.Runtime.Serialization.DataContractSerializer>.|  
  
## <a name="remarks"></a>Observaciones  

 Como se indica en la introducción de este tema, esta es la segunda jerarquía en la que \<X509Extension> se produce el elemento.  
  
 [\<system.runtime.serialization>](system-runtime-serialization.md)  
  
 [\<dataContractSerializer>](datacontractserializer-element.md)  
  
 Para obtener más información sobre los tipos conocidos, consulte <xref:System.Runtime.Serialization.DataContractSerializer>.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>
- <xref:System.ServiceModel.Configuration.DataContractSerializerElement>
- [Tipos conocidos de contratos de datos](../../../wcf/feature-details/data-contract-known-types.md)
- [Transferencia y serialización de datos](../../../wcf/feature-details/data-transfer-and-serialization.md)
