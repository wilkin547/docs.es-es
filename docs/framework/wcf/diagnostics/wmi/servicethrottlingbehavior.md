---
title: ServiceThrottlingBehavior
ms.date: 03/30/2017
ms.assetid: 37b9e517-1f1f-4ec4-9fcb-2b8016794f5b
ms.openlocfilehash: 3bcf205964a22cdb418d0158e5ee6439169538ee
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96273989"
---
# <a name="servicethrottlingbehavior"></a>ServiceThrottlingBehavior

ServiceThrottlingBehavior  
  
## <a name="syntax"></a>Syntax  
  
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
  
 Tipo de acceso: solo lectura  
  
 El número máximo de mensajes que se procesan activamente en todos los objetos de distribuidor en un ServiceHost.  
  
### <a name="maxconcurrentinstances"></a>MaxConcurrentInstances  

 Tipo de datos: sint32  
  
 Tipo de acceso: solo lectura  
  
 El número máximo de objetos de servicio que se pueden ejecutar simultáneamente.  
  
### <a name="maxconcurrentsessions"></a>MaxConcurrentSessions  

 Tipo de datos: sint32  
  
 Tipo de acceso: solo lectura  
  
 El número máximo de sesiones que un host puede aceptar al mismo tiempo.  
  
## <a name="requirements"></a>Requisitos  
  
|MOF|Se declara en Servicemodel.mof.|  
|---------|-----------------------------------|  
|Espacio de nombres|Se define en root\ServiceModel|  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Description.ServiceThrottlingBehavior>
