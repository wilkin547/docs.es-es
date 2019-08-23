---
title: ICLRGCManager (Interfaz)
ms.date: 03/30/2017
api_name:
- ICLRGCManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRGCManager
helpviewer_keywords:
- ICLRGCManager interface [.NET Framework hosting]
ms.assetid: fb511c9b-3fe4-41b0-822a-6ba4a079d1f5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 76d1071ddde1509f16fd786afa4c05c05224d051
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966212"
---
# <a name="iclrgcmanager-interface"></a>ICLRGCManager (Interfaz)
Proporciona métodos que permiten a un host interactuar con el sistema de recolección de elementos no utilizados del Common Language Runtime.  
  
> [!NOTE]
> A partir del .NET Framework 4,5, puede usar el método [iclrgcmanager2 (:: setgcstartuplimitsex (](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) para establecer el tamaño de un segmento de recolección de elementos no utilizados y el tamaño máximo de la generación 0 del sistema de recolección de elementos no utilizados en valores mayores que el `DWORD`límite impuesto por el método [setgcstartuplimits (](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-setgcstartuplimits-method.md) .  
  
## <a name="methods"></a>Métodos  
  
|Método|DESCRIPCIÓN|  
|------------|-----------------|  
|[Collect (método)](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-collect-method.md)|Fuerza una recolección de elementos no utilizados para la generación especificada.|  
|[GetStats (método)](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md)|Obtiene un conjunto de estadísticas actuales sobre el sistema de recolección de elementos no utilizados.|  
|[SetGCStartupLimits (método)](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-setgcstartuplimits-method.md)|Establece el tamaño de un segmento de recolección de elementos no utilizados y el tamaño máximo de la generación 0 del sistema de recolección de elementos no utilizados.|  
  
## <a name="remarks"></a>Comentarios  
 El Common Language Runtime (CLR) implementa su mecanismo de recolección de elementos no utilizados <xref:System.GC> con el tipo administrado. Para obtener más información sobre el sistema de recolección de elementos no utilizados, consulte recolección de [elementos no utilizados](../../../standard/garbage-collection/index.md).  
  
## <a name="requirements"></a>Requisitos  
 **Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: MSCorEE.h  
  
 **Biblioteca** Se incluye como recurso en MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Administración automática de la memoria](../../../standard/automatic-memory-management.md)
- [COR_GC_STATS (estructura)](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)
- [ICLRControl (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [Interfaces de hospedaje de CLR](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)
- [Interfaces de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [Hospedar aplicaciones de WPF](../../../../docs/framework/unmanaged-api/hosting/index.md)
