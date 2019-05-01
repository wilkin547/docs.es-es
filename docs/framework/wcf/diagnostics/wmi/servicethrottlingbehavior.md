---
title: ServiceThrottlingBehavior
ms.date: 03/30/2017
ms.assetid: 37b9e517-1f1f-4ec4-9fcb-2b8016794f5b
ms.openlocfilehash: 572e458f08c4717207667db9940296c4a957199a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61956876"
---
# <a name="servicethrottlingbehavior"></a>ServiceThrottlingBehavior
ServiceThrottlingBehavior  
  
## <a name="syntax"></a>Sintaxis  
  
```csharp  
class ServiceThrottlingBehavior : Behavior  
{  
  sint32 MaxConcurrentCalls;  
  sint32 MaxConcurrentInstances;  
  sint32 MaxConcurrentSessions;  
};  
```  
  
## <a name="methods"></a>Métodos  
 La clase ServiceThrottlingBehavior no define ningún método.  
  
## <a name="properties"></a>Propiedades  
 La clase ServiceThrottlingBehavior tiene las propiedades siguientes:  
  
### <a name="maxconcurrentcalls"></a>MaxConcurrentCalls  
 Tipo de datos: sint32  
  
 Tipo de acceso: De sólo lectura  
  
 El número máximo de mensajes que se procesan activamente en todos los objetos de distribuidor en un ServiceHost.  
  
### <a name="maxconcurrentinstances"></a>MaxConcurrentInstances  
 Tipo de datos: sint32  
  
 Tipo de acceso: De sólo lectura  
  
 El número máximo de objetos de servicio que se pueden ejecutar simultáneamente.  
  
### <a name="maxconcurrentsessions"></a>MaxConcurrentSessions  
 Tipo de datos: sint32  
  
 Tipo de acceso: De sólo lectura  
  
 El número máximo de sesiones que un host puede aceptar al mismo tiempo.  
  
## <a name="requirements"></a>Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-----------------------------------|  
|Espacio de nombres|Se define en root\ServiceModel|  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Description.ServiceThrottlingBehavior>
