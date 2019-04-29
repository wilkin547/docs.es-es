---
title: IGCHost (Interfaz)
ms.date: 03/30/2017
api_name:
- IGCHost
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IGCHost
helpviewer_keywords:
- IGCHost interface [.NET Framework hosting]
ms.assetid: 9ad70ffd-6963-4ab2-8c84-3d86c3fb8deb
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3202aa25261863dae953e3edac36f3406fa001d8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61699764"
---
# <a name="igchost-interface"></a>IGCHost (Interfaz)
Proporciona métodos para obtener información sobre el sistema de recopilación de elementos no utilizados y para controlar algunos aspectos de la recolección de elementos.  
  
> [!NOTE]
>  A partir de la [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], puede usar el [Igchost2](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) método para establecer el tamaño de un segmento de la colección de elementos no utilizados y el tamaño máximo de la generación 0 del sistema de recopilación de elementos no utilizados en los valores de mayor que el `DWORD` límite impuesto por el [SetGCStartupLimits](../../../../docs/framework/unmanaged-api/hosting/igchost-setgcstartuplimits-method.md) método.  
  
> [!NOTE]
>  Esta interfaz es para experto uso exclusivo. Si se utiliza incorrectamente puede afectar al rendimiento de una aplicación.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Collect (método)](../../../../docs/framework/unmanaged-api/hosting/igchost-collect-method.md)|Fuerza una recolección que se produzca la generación determinada, independientemente del estado de la recolección de elementos actual.|  
|[GetStats (método)](../../../../docs/framework/unmanaged-api/hosting/igchost-getstats-method.md)|Obtiene las estadísticas para el estado actual del sistema de recopilación de elementos no utilizados.|  
|[GetThreadStats (método)](../../../../docs/framework/unmanaged-api/hosting/igchost-getthreadstats-method.md)|Obtiene las estadísticas por subproceso para la recolección.|  
|[SetGCStartupLimits (método)](../../../../docs/framework/unmanaged-api/hosting/igchost-setgcstartuplimits-method.md)|Establece el tamaño del segmento y el tamaño máximo para la generación 0.|  
|[SetVirtualMemLimit (método)](../../../../docs/framework/unmanaged-api/hosting/igchost-setvirtualmemlimit-method.md)|Establece el tamaño máximo de memoria virtual de tiempo de ejecución.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: GCHost.idl, GCHost.h  
  
 **Biblioteca:** Incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [CorRuntimeHost (coclase)](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
