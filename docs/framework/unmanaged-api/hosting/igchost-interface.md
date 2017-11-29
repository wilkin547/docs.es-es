---
title: IGCHost (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IGCHost
api_location: mscoree.dll
api_type: COM
f1_keywords: IGCHost
helpviewer_keywords: IGCHost interface [.NET Framework hosting]
ms.assetid: 9ad70ffd-6963-4ab2-8c84-3d86c3fb8deb
topic_type: apiref
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 5c0f398c09569a855291a1565ce63b513161a803
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="igchost-interface"></a>IGCHost (Interfaz)
Proporciona métodos para obtener información sobre el sistema de recopilación de elementos no utilizados y para controlar algunos aspectos de la recolección de elementos.  
  
> [!NOTE]
>  A partir de la [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], puede usar el [igchost2:: Setgcstartuplimitsex](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) método para establecer el tamaño de un segmento de la colección de elementos no utilizados y el tamaño máximo de la generación 0 del sistema de recopilación de elementos no utilizados en valores mayor que el `DWORD` límite impuesto por la [SetGCStartupLimits](../../../../docs/framework/unmanaged-api/hosting/igchost-setgcstartuplimits-method.md) método.  
  
> [!NOTE]
>  Esta interfaz es solo pueden utilizar expertos. Si se utiliza incorrectamente puede afectar al rendimiento de una aplicación.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Collect (método)](../../../../docs/framework/unmanaged-api/hosting/igchost-collect-method.md)|Fuerza una recolección que se produzca la generación determinada, con independencia del estado de la colección de elementos no utilizados actual.|  
|[GetStats (método)](../../../../docs/framework/unmanaged-api/hosting/igchost-getstats-method.md)|Obtiene las estadísticas para el estado actual del sistema de recopilación de elementos no utilizados.|  
|[GetThreadStats (método)](../../../../docs/framework/unmanaged-api/hosting/igchost-getthreadstats-method.md)|Obtiene las estadísticas por subproceso para la recolección.|  
|[SetGCStartupLimits (método)](../../../../docs/framework/unmanaged-api/hosting/igchost-setgcstartuplimits-method.md)|Establece el tamaño del segmento y el tamaño máximo para la generación 0.|  
|[SetVirtualMemLimit (método)](../../../../docs/framework/unmanaged-api/hosting/igchost-setvirtualmemlimit-method.md)|Establece el tamaño máximo de memoria virtual de tiempo de ejecución.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** GCHost.idl, GCHost.h  
  
 **Biblioteca:** incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Interfaces de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [CorRuntimeHost (Coclase)](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
