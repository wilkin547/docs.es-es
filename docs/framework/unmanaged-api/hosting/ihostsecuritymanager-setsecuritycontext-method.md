---
title: IHostSecurityManager::SetSecurityContext (Método)
ms.date: 03/30/2017
api_name:
- IHostSecurityManager.SetSecurityContext
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager::SetSecurityContext
helpviewer_keywords:
- SetSecurityContext method [.NET Framework hosting]
- IHostSecurityManager::SetSecurityContext method [.NET Framework hosting]
ms.assetid: e4372384-ee69-48d7-97e0-8fab7866597a
topic_type:
- apiref
ms.openlocfilehash: 79ef08ef70ad1132ceacc3e2b997651e57032b9a
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/22/2020
ms.locfileid: "83803812"
---
# <a name="ihostsecuritymanagersetsecuritycontext-method"></a>IHostSecurityManager::SetSecurityContext (Método)
Establece el contexto de seguridad del subproceso que se está ejecutando actualmente.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT SetSecurityContext (  
    [in]  EContextType eContextType,  
    [out] IHostSecurityContext** ppSecurityContext  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `eContextType`  
 de Uno de los valores de [econtexttype (](econtexttype-enumeration.md) , que indica qué tipo de contexto coloca el Common Language Runtime (CLR) en el host.  
  
 `ppSecurityContext`  
 enuncia Puntero a la dirección de un nuevo objeto [IHostSecurityContext](ihostsecuritycontext-interface.md) .  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|`SetSecurityContext`se devolvió correctamente.|  
|HOST_E_CLRNOTAVAILABLE|CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|Se agotó el tiempo de espera de la llamada.|  
|HOST_E_NOT_OWNER|El autor de la llamada no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.|  
|E_FAIL|Se produjo un error grave desconocido. Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso. Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Observaciones  
 CLR llama a `SetSecurityContext` en varios escenarios. Antes de ejecutar constructores y finalizadores de clases y módulos, CLR llama `SetSecurityContext` a para proteger el host frente a errores de ejecución. A continuación, restablece el contexto de seguridad a su estado original después de la ejecución del constructor o finalizador, mediante otra llamada a `SetSecurityContext` . Se produce un patrón similar con la finalización de e/s. Si el host implementa [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md), CLR llama a `SetSecurityContext` después de que el host llame a [ICLRIoCompletionManager:: alcomplete](iclriocompletionmanager-oncomplete-method.md).  
  
 En los puntos asincrónicos de los subprocesos de trabajo, CLR llama a `SetSecurityContext` dentro <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> o dentro de [IHostThreadPoolManager:: QueueUserWorkItem](ihostthreadpoolmanager-queueuserworkitem-method.md), dependiendo de si el host o CLR está implementando el grupo de subprocesos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Threading.ThreadPool?displayProperty=nameWithType>
- [EContextType (Enumeración)](econtexttype-enumeration.md)
- [ICLRIoCompletionManager (Interfaz)](iclriocompletionmanager-interface.md)
- [IHostIoCompletionManager (Interfaz)](ihostiocompletionmanager-interface.md)
- [IHostSecurityContext (Interfaz)](ihostsecuritycontext-interface.md)
- [IHostSecurityManager (Interfaz)](ihostsecuritymanager-interface.md)
- [IHostThreadPoolManager (Interfaz)](ihostthreadpoolmanager-interface.md)
