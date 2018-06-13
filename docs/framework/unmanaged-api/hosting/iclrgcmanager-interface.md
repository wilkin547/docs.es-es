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
ms.openlocfilehash: 045b924033630ea98d5a532a62f1037a5972df90
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33433929"
---
# <a name="iclrgcmanager-interface"></a>ICLRGCManager (Interfaz)
Proporciona métodos que permiten a un host interactuar con el sistema de recopilación de elementos no utilizados de common language runtime.  
  
> [!NOTE]
>  A partir de la [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], puede usar el [iclrgcmanager2:: Setgcstartuplimitsex](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) método para establecer el tamaño de un segmento de la colección de elementos no utilizados y el tamaño máximo de la generación 0 del sistema de recopilación de elementos no utilizados en valores mayor que el `DWORD` límite impuesto por la [SetGCStartupLimits](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-setgcstartuplimits-method.md) método.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Collect (método)](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-collect-method.md)|Fuerza una recolección de elementos no utilizados para la generación especificada.|  
|[GetStats (método)](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md)|Obtiene un conjunto de estadísticas actuales sobre el sistema de recopilación de elementos no utilizados.|  
|[SetGCStartupLimits (método)](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-setgcstartuplimits-method.md)|Establece el tamaño de un segmento de la colección de elementos no utilizados y el tamaño máximo de la generación 0 del sistema de recopilación de elementos no utilizados.|  
  
## <a name="remarks"></a>Comentarios  
 Common language runtime (CLR) implementa su mecanismo de recopilación de elementos no utilizados con los recursos administrados <xref:System.GC> tipo. Para obtener más información sobre el sistema de recopilación de elementos no utilizados, vea [recolección](../../../../docs/standard/garbage-collection/index.md).  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE.h  
  
 **Biblioteca:** incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Administración automática de la memoria](../../../../docs/standard/automatic-memory-management.md)  
 [COR_GC_STATS (estructura)](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)  
 [ICLRControl (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [Interfaces de hospedaje de CLR](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)  
 [Interfaces de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [Hospedar aplicaciones de WPF](../../../../docs/framework/unmanaged-api/hosting/index.md)
