---
description: 'Más información acerca de: IHostThreadPoolManager:: GetMaxThreads (método)'
title: IHostThreadPoolManager::GetMaxThreads (Método)
ms.date: 03/30/2017
api_name:
- IHostThreadPoolManager.GetMaxThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostThreadPoolManager::GetMaxThreads
helpviewer_keywords:
- IHostThreadPoolManager::GetMaxThreads method [.NET Framework hosting]
- GetMaxThreads method, IHostThreadPoolManager interface [.NET Framework hosting]
ms.assetid: db268876-6178-4a81-aca3-318ee7f96001
topic_type:
- apiref
ms.openlocfilehash: e8cae2aa29a50ef58a5b87deba9e275a441d43ef
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99728390"
---
# <a name="ihostthreadpoolmanagergetmaxthreads-method"></a>IHostThreadPoolManager::GetMaxThreads (Método)

Obtiene el número máximo de subprocesos que el host mantiene simultáneamente en el grupo de subprocesos.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetMaxThreads (  
    [out] DWORD *pdwMaxWorkerThreads  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `pdwMaxWorkerThreads`  
 enuncia Puntero al número máximo de subprocesos que el host mantiene en el grupo de subprocesos.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|`GetMaxThreads` se devolvió correctamente.|  
|HOST_E_CLRNOTAVAILABLE|El Common Language Runtime (CLR (no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente).|  
|HOST_E_TIMEOUT|Se agotó el tiempo de espera de la llamada.|  
|HOST_E_NOT_OWNER|El autor de la llamada no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.|  
|E_FAIL|Se produjo un error grave desconocido. Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso. Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
|E_NOTIMPL|El host no proporciona una implementación de `GetMaxThreads` .|  
  
## <a name="remarks"></a>Observaciones  

 CLR llama `GetMaxThreads` a para determinar el número total de subprocesos del grupo de subprocesos. El método [GetAvailableThreads](ihostthreadpoolmanager-getavailablethreads-method.md) obtiene el número de subprocesos que no están procesando actualmente los elementos de trabajo. Todas las solicitudes por encima del valor devuelto del `pdwMaxWorkerThreads` parámetro permanecen en la cola hasta que los subprocesos están disponibles.  
  
 Si el host no proporciona una implementación de `GetMaxThreads` , debe devolver un valor HRESULT de E_NOTIMPL.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Threading.ThreadPool.GetMaxThreads%2A>
- <xref:System.Threading.ThreadPool>
- [Método GetMinThreads](ihostthreadpoolmanager-getminthreads-method.md)
- [Método SetMaxThreads](ihostthreadpoolmanager-setmaxthreads-method.md)
- [IHostThreadPoolManager (Interfaz)](ihostthreadpoolmanager-interface.md)
