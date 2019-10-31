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
ms.openlocfilehash: 8aef78c7cf70e6b2d97af9c47d57908b86729ff7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122083"
---
# <a name="ihostthreadpoolmanager-interface"></a>IHostThreadPoolManager (Interfaz)
Proporciona métodos que permiten al Common Language Runtime (CLR) configurar el grupo de subprocesos y poner en cola los elementos de trabajo en el grupo de subprocesos.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[GetAvailableThreads (método)](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getavailablethreads-method.md)|Obtiene el número de subprocesos del grupo de subprocesos que no están procesando actualmente los elementos de trabajo.|  
|[GetMaxThreads (método)](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getmaxthreads-method.md)|Obtiene el número máximo de subprocesos que el host mantiene simultáneamente en el grupo de subprocesos.|  
|[GetMinThreads (método)](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getminthreads-method.md)|Obtiene el número mínimo de subprocesos inactivos que el host mantiene en previsión de solicitudes.|  
|[QueueUserWorkItem (método)](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md)|Pone en cola una función para su ejecución y proporciona un objeto que contiene los datos que va a usar la función.|  
|[SetMaxThreads (método)](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setmaxthreads-method.md)|Establece el número máximo de subprocesos que el host puede mantener en el grupo de subprocesos.|  
|[SetMinThreads (método)](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setminthreads-method.md)|Establece el número mínimo de subprocesos inactivos que el host debe mantener en previsión de las solicitudes.|  
  
## <a name="remarks"></a>Comentarios  
 No es necesario que el host configure el grupo de subprocesos utilizando los valores especificados en las llamadas a los métodos `SetMaxThreads` y `SetMinThreads`. En este caso, el host debe devolver un valor HRESULT de E_NOTIMPL desde estos métodos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Threading>
- <xref:System.Threading.ThreadPool>
- [Interfaces de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
