---
title: DeliveryRequirementsAttribute
ms.date: 03/30/2017
ms.assetid: 40c5435c-a325-4cf8-9dd0-d6e24b4a56a3
ms.openlocfilehash: a70a4ba40b569acc7893b21d796194224dc4ee78
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96274054"
---
# <a name="deliveryrequirementsattribute"></a>DeliveryRequirementsAttribute

DeliveryRequirementsAttribute  
  
## <a name="syntax"></a>Syntax  
  
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

 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 Especifica si el enlace para un servicio admite contratos.  
  
### <a name="requireordereddelivery"></a>RequireOrderedDelivery  

 Tipo de datos: booleano  
  
 Tipo de acceso: solo lectura  
  
 Especifica si el enlace admite mensajes ordenados.  
  
### <a name="targetcontract"></a>TargetContract  

 Tipo de datos: cadena  
  
 Tipo de acceso: solo lectura  
  
 El contrato al que se aplica.  
  
## <a name="requirements"></a>Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-----------------------------------|  
|Espacio de nombres|Se define en root\ServiceModel|  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.DeliveryRequirementsAttribute>
