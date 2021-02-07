---
description: 'Más información acerca de: IHostThreadPoolManager (interfaz)'
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
ms.openlocfilehash: 0361b7a08f781a8748e43959f65ce0e9f21bbac1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99728426"
---
# <a name="ihostthreadpoolmanager-interface"></a>IHostThreadPoolManager (Interfaz)

Proporciona métodos que permiten al Common Language Runtime (CLR) configurar el grupo de subprocesos y poner en cola los elementos de trabajo en el grupo de subprocesos.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método GetAvailableThreads](ihostthreadpoolmanager-getavailablethreads-method.md)|Obtiene el número de subprocesos del grupo de subprocesos que no están procesando actualmente los elementos de trabajo.|  
|[Método GetMaxThreads](ihostthreadpoolmanager-getmaxthreads-method.md)|Obtiene el número máximo de subprocesos que el host mantiene simultáneamente en el grupo de subprocesos.|  
|[Método GetMinThreads](ihostthreadpoolmanager-getminthreads-method.md)|Obtiene el número mínimo de subprocesos inactivos que el host mantiene en previsión de solicitudes.|  
|[Método QueueUserWorkItem](ihostthreadpoolmanager-queueuserworkitem-method.md)|Pone en cola una función para su ejecución y proporciona un objeto que contiene los datos que va a usar la función.|  
|[Método SetMaxThreads](ihostthreadpoolmanager-setmaxthreads-method.md)|Establece el número máximo de subprocesos que el host puede mantener en el grupo de subprocesos.|  
|[Método SetMinThreads](ihostthreadpoolmanager-setminthreads-method.md)|Establece el número mínimo de subprocesos inactivos que el host debe mantener en previsión de las solicitudes.|  
  
## <a name="remarks"></a>Observaciones  

 No es necesario que el host configure el grupo de subprocesos utilizando los valores especificados en las llamadas a los `SetMaxThreads` `SetMinThreads` métodos y. En este caso, el host debe devolver un valor HRESULT de E_NOTIMPL de estos métodos.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Threading>
- <xref:System.Threading.ThreadPool>
- [Interfaces de hospedaje](hosting-interfaces.md)
