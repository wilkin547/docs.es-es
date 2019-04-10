---
title: IHostThreadPoolManager (Interfaz)
ms.date: 03/30/2017
api_name:
- IHostThreadPoolManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostThreadPoolManager
helpviewer_keywords:
- IHostThreadPoolManager interface [.NET Framework hosting]
ms.assetid: c3a2cd90-7c4e-4374-bb87-b41befb8344f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2e7976740a79efda8e5ab569f2efb55444012c5d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59220375"
---
# <a name="ihostthreadpoolmanager-interface"></a>IHostThreadPoolManager (Interfaz)
Proporciona métodos que permiten a common language runtime (CLR) para configurar el grupo de subprocesos y poner en cola los elementos de trabajo al grupo de subprocesos.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método GetAvailableThreads](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getavailablethreads-method.md)|Obtiene el número de subprocesos en el grupo de subprocesos que no se están procesando actualmente elementos de trabajo.|  
|[Método GetMaxThreads](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getmaxthreads-method.md)|Obtiene el número máximo de subprocesos que el host mantiene simultáneamente en el grupo de subprocesos.|  
|[Método GetMinThreads](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getminthreads-method.md)|Obtiene el número mínimo de subprocesos inactivos que mantiene el host en previsión de solicitudes.|  
|[Método QueueUserWorkItem](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md)|Pone en cola una función para su ejecución y proporciona un objeto que contiene los datos que va a usar la función.|  
|[Método SetMaxThreads](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setmaxthreads-method.md)|Establece el número máximo de subprocesos que el host puede mantener en el grupo de subprocesos.|  
|[Método SetMinThreads](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setminthreads-method.md)|Establece el número mínimo de subprocesos inactivos que el host debe mantener en previsión de solicitudes.|  
  
## <a name="remarks"></a>Comentarios  
 El host no es necesario para configurar el grupo de subprocesos mediante los valores especificados en las llamadas a la `SetMaxThreads` y `SetMinThreads` métodos. En este caso, el host debe devolver un valor HRESULT de E_NOTIMPL desde estos métodos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: MSCorEE.h  
  
 **Biblioteca:** Incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Threading>
- <xref:System.Threading.ThreadPool>
- [Interfaces de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
