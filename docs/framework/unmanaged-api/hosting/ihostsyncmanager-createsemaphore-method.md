---
description: 'Más información acerca de: IHostSyncManager:: Createsemaphore ((método)'
title: IHostSyncManager::CreateSemaphore (Método)
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateSemaphore
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateSemaphore
helpviewer_keywords:
- CreateSemaphore method [.NET Framework hosting]
- IHostSyncManager::CreateSemaphore method [.NET Framework hosting]
ms.assetid: 37679e94-5ff9-4173-8fa5-457febeb89bf
topic_type:
- apiref
ms.openlocfilehash: 5a03ef7532e2ac8357ec015b40cc54942f5420e5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784748"
---
# <a name="ihostsyncmanagercreatesemaphore-method"></a>IHostSyncManager::CreateSemaphore (Método)

Crea un objeto [IHostSemaphore](ihostsemaphore-interface.md) para el Common Language Runtime (CLR) que se va a usar como semáforo para los eventos de espera.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT CreateSemaphore (  
    [in]  DWORD dwInitial,  
    [in]  DWORD dwMax,  
    [out] IHostSemaphore **ppSemaphore  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `dwInitial`  
 de Número inicial de `ppSemaphore` .  
  
 `dwMax`  
 de Número máximo de `ppSemaphore` .  
  
 `ppSemaphore`  
 enuncia Puntero a la dirección de una `IHostSemaphore` instancia de o null si no se pudo crear el semáforo.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|`CreateSemaphore` se devolvió correctamente.|  
|HOST_E_CLRNOTAVAILABLE|CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|Se agotó el tiempo de espera de la llamada.|  
|HOST_E_NOT_OWNER|El autor de la llamada no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.|  
|E_FAIL|Se produjo un error grave desconocido. Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso. Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
|E_OUTOFMEMORY|No había suficiente memoria disponible para crear el objeto de evento solicitado.|  
  
## <a name="remarks"></a>Observaciones  

 `CreateSemaphore` refleja la función de Win32 que tiene el mismo nombre. Los `dwInitial` `dwMax` parámetros y usan la misma semántica para el recuento de semáforos que los `lInitialCount` parámetros y de Win32 `lMaximumCount` , respectivamente. `dwInitial` debe estar entre cero y `dwMax` , ambos incluidos. `dwMax` debe ser mayor que cero.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRSyncManager (Interfaz)](iclrsyncmanager-interface.md)
- [IHostSemaphore (Interfaz)](ihostsemaphore-interface.md)
- [IHostSyncManager (Interfaz)](ihostsyncmanager-interface.md)
