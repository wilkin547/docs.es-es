---
title: IHostThreadPoolManager (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostThreadPoolManager
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostThreadPoolManager
helpviewer_keywords: IHostThreadPoolManager interface [.NET Framework hosting]
ms.assetid: c3a2cd90-7c4e-4374-bb87-b41befb8344f
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1cd58c53deec0a895ae6f67cccf26d2c8c2530be
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ihostthreadpoolmanager-interface"></a>IHostThreadPoolManager (Interfaz)
Proporciona métodos que permiten a common language runtime (CLR) para configurar el grupo de subprocesos y poner en cola los elementos de trabajo al grupo de subprocesos.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[GetAvailableThreads (método)](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getavailablethreads-method.md)|Obtiene el número de subprocesos en el grupo de subprocesos que no se están procesando actualmente elementos de trabajo.|  
|[GetMaxThreads (método)](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getmaxthreads-method.md)|Obtiene el número máximo de subprocesos que el host mantiene simultáneamente en el grupo de subprocesos.|  
|[GetMinThreads (método)](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getminthreads-method.md)|Obtiene el número mínimo de subprocesos inactivos que el host mantiene en previsión de solicitudes.|  
|[QueueUserWorkItem (método)](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md)|Pone en cola una función para su ejecución y proporciona un objeto que contiene los datos que va a usar la función.|  
|[SetMaxThreads (método)](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setmaxthreads-method.md)|Establece el número máximo de subprocesos que el host puede mantener en el grupo de subprocesos.|  
|[SetMinThreads (método)](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setminthreads-method.md)|Establece el número mínimo de subprocesos inactivos que el host debe mantener en previsión de solicitudes.|  
  
## <a name="remarks"></a>Comentarios  
 El host no es necesario para configurar el grupo de subprocesos con los valores especificados en las llamadas a la `SetMaxThreads` y `SetMinThreads` métodos. En este caso, el host debe devolver un valor HRESULT de E_NOTIMPL desde estos métodos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE.h  
  
 **Biblioteca:** incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Threading>  
 <xref:System.Threading.ThreadPool>  
 [Interfaces de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
