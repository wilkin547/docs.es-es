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
ms.openlocfilehash: 91483d5bdf1eb8e6b03d7691e2a95074e3789317
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134878"
---
# <a name="igchost-interface"></a>IGCHost (Interfaz)
Proporciona métodos para obtener información sobre el sistema de recolección de elementos no utilizados y para controlar algunos aspectos de la recolección de elementos no utilizados.  
  
> [!NOTE]
> A partir del .NET Framework 4,5, puede usar el método [igchost2 (:: setgcstartuplimitsex (](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) para establecer el tamaño de un segmento de recolección de elementos no utilizados y el tamaño máximo de la generación 0 del sistema de recolección de elementos no utilizados en valores mayores que el límite de `DWORD` impuesto por el método [setgcstartuplimits (](../../../../docs/framework/unmanaged-api/hosting/igchost-setgcstartuplimits-method.md) .  
  
> [!NOTE]
> Esta interfaz solo es para uso experto. Puede afectar al rendimiento de una aplicación si se usa de forma incorrecta.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Collect (método)](../../../../docs/framework/unmanaged-api/hosting/igchost-collect-method.md)|Obliga a que se produzca una colección para la generación dada, independientemente del estado de la recolección de elementos no utilizados actual.|  
|[GetStats (método)](../../../../docs/framework/unmanaged-api/hosting/igchost-getstats-method.md)|Obtiene las estadísticas para el estado actual del sistema de recolección de elementos no utilizados.|  
|[GetThreadStats (método)](../../../../docs/framework/unmanaged-api/hosting/igchost-getthreadstats-method.md)|Obtiene las estadísticas por subproceso para la recolección de elementos no utilizados.|  
|[SetGCStartupLimits (método)](../../../../docs/framework/unmanaged-api/hosting/igchost-setgcstartuplimits-method.md)|Establece el tamaño del segmento y el tamaño máximo de la generación 0.|  
|[SetVirtualMemLimit (método)](../../../../docs/framework/unmanaged-api/hosting/igchost-setvirtualmemlimit-method.md)|Establece el tamaño máximo de la memoria virtual del tiempo de ejecución.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** GCHost. idl, GCHost. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [CorRuntimeHost (coclase)](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
