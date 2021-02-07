---
description: 'Más información sobre: dataContractSerializer'
title: dataContractSerializer
ms.date: 03/30/2017
ms.assetid: a47513a4-a96c-4350-8586-daacb05dee71
ms.openlocfilehash: 5dee59ba97a1632c142179aee79058dd3ce8c349
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99754412"
---
# <a name="datacontractserializer"></a>dataContractSerializer

Contiene los datos de configuración para <xref:System.Runtime.Serialization.DataContractSerializer>.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
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
|ignoreExtensionDataObject|Un valor booleano que especifica si se omiten los datos proporcionados por el extremo, cuando se serializa o deserializa.|  
|maxItemsInObjectGraph|Un entero que especifica el número máximo de elementos para serializar o deserializar.|  
  
### <a name="child-elements"></a>Elementos secundarios  

 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<behavior>](behavior-of-endpointbehaviors.md)|Especifica el comportamiento de un punto de conexión.|  
  
## <a name="remarks"></a>Observaciones  

 Para obtener más información sobre los tipos conocidos, vea la documentación <xref:System.Runtime.Serialization.DataContractSerializer>.  
  
> [!CAUTION]
> El elemento de comportamiento `<dataContractSerializer>` (si está presente) debe aparecer siempre antes del elemento de comportamiento `<enableWebScript>` del archivo de configuración. En caso contrario, el comportamiento resultante no está definido.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Runtime.Serialization.DataContractSerializer>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>
- <xref:System.ServiceModel.Configuration.DataContractSerializerElement>
- [Tipos conocidos de contratos de datos](../../../wcf/feature-details/data-contract-known-types.md)
- [Transferencia y serialización de datos](../../../wcf/feature-details/data-transfer-and-serialization.md)
