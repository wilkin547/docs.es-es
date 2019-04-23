---
title: DeliveryRequirementsAttribute
ms.date: 03/30/2017
ms.assetid: 40c5435c-a325-4cf8-9dd0-d6e24b4a56a3
ms.openlocfilehash: c81e4b27969d879a70806082f48879cbf1b32ccc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2019
ms.locfileid: "59979217"
---
# <a name="deliveryrequirementsattribute"></a>DeliveryRequirementsAttribute
DeliveryRequirementsAttribute  
  
## <a name="syntax"></a>Sintaxis  
  
```csharp
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
  
 Tipo de acceso: De sólo lectura  
  
 Especifica si el enlace para un servicio admite contratos.  
  
### <a name="requireordereddelivery"></a>RequireOrderedDelivery  
 Tipo de datos: booleano  
  
 Tipo de acceso: De sólo lectura  
  
 Especifica si el enlace admite mensajes ordenados.  
  
### <a name="targetcontract"></a>TargetContract  
 Tipo de datos: cadena  
  
 Tipo de acceso: De sólo lectura  
  
 El contrato al que se aplica.  
  
## <a name="requirements"></a>Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-----------------------------------|  
|Espacio de nombres|Se define en root\ServiceModel|  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.DeliveryRequirementsAttribute>
