---
title: ICLRSyncManager (Interfaz)
ms.date: 03/30/2017
api_name:
- ICLRSyncManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRSyncManager
helpviewer_keywords:
- ICLRSyncManager interface [.NET Framework hosting]
ms.assetid: a49f9d80-1c76-4ddd-8c49-34f913a5c596
topic_type:
- apiref
ms.openlocfilehash: 3593e4d68058a1820f575c92ff9571d43560316a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133934"
---
# <a name="iclrsyncmanager-interface"></a>ICLRSyncManager (Interfaz)
Define métodos que permiten al host obtener información sobre las tareas solicitadas y detectar interbloqueos en su implementación de sincronización.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[CreateRWLockOwnerIterator (método)](iclrsyncmanager-createrwlockowneriterator-method.md)|Solicita que el Common Language Runtime (CLR) cree un iterador para que lo use el host con el fin de determinar el conjunto de tareas que esperan en un bloqueo de lectura y escritura.|  
|[DeleteRWLockOwnerIterator (método)](iclrsyncmanager-deleterwlockowneriterator-method.md)|Solicita que CLR destruya un iterador creado por una llamada a `CreateRWLockOwnerIterator`.|  
|[GetMonitorOwner (método)](iclrsyncmanager-getmonitorowner-method.md)|Obtiene la tarea que posee el monitor especificado.|  
|[GetRWLockOwnerNext (método)](iclrsyncmanager-getrwlockownernext-method.md)|Obtiene la siguiente tarea que está esperando en el bloqueo de lector-Writer actual.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Threading.Thread>
- [IHostSyncManager (interfaz)](ihostsyncmanager-interface.md)
- [Subprocesamiento administrado y no administrado](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/5s8ee185(v=vs.100))
- [Interfaces de hospedaje](hosting-interfaces.md)
