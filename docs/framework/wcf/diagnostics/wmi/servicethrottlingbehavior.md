---
description: 'Más información acerca de: ServiceThrottlingBehavior'
title: ServiceThrottlingBehavior
ms.date: 03/30/2017
ms.assetid: 37b9e517-1f1f-4ec4-9fcb-2b8016794f5b
ms.openlocfilehash: c4cf354c96340b910807bf7904e63a08dc01764b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99715449"
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
