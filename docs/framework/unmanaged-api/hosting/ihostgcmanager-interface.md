---
description: 'Más información acerca de: interfaz IHostGCManager'
title: IHostGCManager (Interfaz)
ms.date: 03/30/2017
api_name:
- IHostGCManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostGCManager
helpviewer_keywords:
- IHostGCManager interface [.NET Framework hosting]
ms.assetid: 820330a4-244c-4f67-ab5e-f24b0b3c2080
topic_type:
- apiref
ms.openlocfilehash: da229c04eb5f5a27c34c133b5c88183d00f47c40
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99708663"
---
# <a name="ihostgcmanager-interface"></a>IHostGCManager (Interfaz)

Proporciona métodos que notifican al host de eventos en el mecanismo de recolección de elementos no utilizados implementado por el Common Language Runtime (CLR).  
  
## <a name="members"></a>Members  
  
|Miembro|Descripción|  
|------------|-----------------|  
|[Método SuspensionEnding](ihostgcmanager-suspensionending-method.md)|Notifica al host que el CLR está reanudando la ejecución de las tareas en los subprocesos que se han suspendido para una recolección de elementos no utilizados.|  
|[Método SuspensionStarting](ihostgcmanager-suspensionstarting-method.md)|Notifica al host que el CLR está suspendiendo la ejecución de las tareas, para realizar una recolección de elementos no utilizados.|  
|[Método ThreadIsBlockingForSuspension](ihostgcmanager-threadisblockingforsuspension-method.md)|Notifica al host que el subproceso del que se realizó la llamada al método está a punto de bloquearse para una recolección de elementos no utilizados.|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRTask (Interfaz)](iclrtask-interface.md)
- [ICLRTaskManager (Interfaz)](iclrtaskmanager-interface.md)
- [IHostTask (Interfaz)](ihosttask-interface.md)
- [IHostTaskManager (Interfaz)](ihosttaskmanager-interface.md)
- [Interfaces de hospedaje](hosting-interfaces.md)
