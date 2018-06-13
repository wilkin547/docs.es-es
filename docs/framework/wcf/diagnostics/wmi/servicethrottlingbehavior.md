---
title: ServiceThrottlingBehavior
ms.date: 03/30/2017
ms.assetid: 37b9e517-1f1f-4ec4-9fcb-2b8016794f5b
ms.openlocfilehash: 9a7fbf93dbdbf1a6debcf865b4883b5784e2ff4a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33487612"
---
# <a name="servicethrottlingbehavior"></a>ServiceThrottlingBehavior
ServiceThrottlingBehavior  
  
## <a name="syntax"></a>Sintaxis  
  
```  
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
 <xref:System.ServiceModel.Description.ServiceThrottlingBehavior>
