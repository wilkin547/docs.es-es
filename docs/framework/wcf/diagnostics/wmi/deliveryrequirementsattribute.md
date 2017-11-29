---
title: DeliveryRequirementsAttribute
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 40c5435c-a325-4cf8-9dd0-d6e24b4a56a3
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 40bdc27337daae02795137fc3ac67575787018c1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="deliveryrequirementsattribute"></a>DeliveryRequirementsAttribute
DeliveryRequirementsAttribute  
  
## <a name="syntax"></a>Sintaxis  
  
```  
class DeliveryRequirementsAttribute : Behavior  
{  
  string QueuedDeliveryRequirements;  
  boolean RequireOrderedDelivery;  
  string TargetContract;  
};  
```  
  
## <a name="methods"></a>Métodos  
 La clase DeliveryRequirementsAttribute no define ningún método.  
  
## <a name="properties"></a>Propiedades  
 La clase DeliveryRequirementsAttribute tiene las propiedades siguientes:  
  
### <a name="queueddeliveryrequirements"></a>QueuedDeliveryRequirements  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 Especifica si el enlace para un servicio admite contratos.  
  
### <a name="requireordereddelivery"></a>RequireOrderedDelivery  
 Tipo de datos: booleano  
  
 Tipo de acceso: solo lectura  
  
 Especifica si el enlace admite mensajes ordenados.  
  
### <a name="targetcontract"></a>TargetContract  
 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 El contrato al que se aplica.  
  
## <a name="requirements"></a>Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-----------------------------------|  
|Espacio de nombres|Se define en root\ServiceModel|  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.DeliveryRequirementsAttribute>
