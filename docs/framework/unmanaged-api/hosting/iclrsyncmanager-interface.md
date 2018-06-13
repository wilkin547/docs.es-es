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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1b87ccc3d6c3e957d0384499048032e35247093a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33436486"
---
# <a name="iclrsyncmanager-interface"></a>ICLRSyncManager (Interfaz)
Define métodos que permiten al host para obtener información sobre las tareas solicitadas y detectar interbloqueos en su implementación de la sincronización.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[CreateRWLockOwnerIterator (método)](iclrsyncmanager-createrwlockowneriterator-method.md)|Solicita que common language runtime (CLR) cree un iterador para el host se utiliza para determinar el conjunto de tareas que esperan en un bloqueo de lector y escritor.|  
|[DeleteRWLockOwnerIterator (método)](iclrsyncmanager-deleterwlockowneriterator-method.md)|Solicita que CLR destruya un iterador que se creó mediante una llamada a `CreateRWLockOwnerIterator`.|  
|[GetMonitorOwner (método)](iclrsyncmanager-getmonitorowner-method.md)|Obtiene la tarea que posee al monitor especificado.|  
|[GetRWLockOwnerNext (método)](iclrsyncmanager-getrwlockownernext-method.md)|Obtiene la siguiente tarea está esperando el bloqueo de lector y escritor actual.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE.h  
  
 **Biblioteca:** incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Threading.Thread>  
 [IHostSyncManager (interfaz)](ihostsyncmanager-interface.md)  
 [Subprocesamiento administrado y no administrado](https://msdn.microsoft.com/library/db425c20-4b2f-4433-bf96-76071c7881e5(v=vs.100))  
 [Interfaces de hospedaje](hosting-interfaces.md)
