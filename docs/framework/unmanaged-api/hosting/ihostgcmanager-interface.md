---
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
ms.openlocfilehash: 428e4cf8997713b08e40d9376c34ae5eee8cfa32
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804852"
---
# <a name="ihostgcmanager-interface"></a>IHostGCManager (Interfaz)
Proporciona métodos que notifican al host de eventos en el mecanismo de recolección de elementos no utilizados implementado por el Common Language Runtime (CLR).  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|[Método SuspensionEnding](ihostgcmanager-suspensionending-method.md)|Notifica al host que el CLR está reanudando la ejecución de las tareas en los subprocesos que se han suspendido para una recolección de elementos no utilizados.|  
|[Método SuspensionStarting](ihostgcmanager-suspensionstarting-method.md)|Notifica al host que el CLR está suspendiendo la ejecución de las tareas, para realizar una recolección de elementos no utilizados.|  
|[Método ThreadIsBlockingForSuspension](ihostgcmanager-threadisblockingforsuspension-method.md)|Notifica al host que el subproceso del que se realizó la llamada al método está a punto de bloquearse para una recolección de elementos no utilizados.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICLRTask (Interfaz)](iclrtask-interface.md)
- [ICLRTaskManager (Interfaz)](iclrtaskmanager-interface.md)
- [IHostTask (Interfaz)](ihosttask-interface.md)
- [IHostTaskManager (Interfaz)](ihosttaskmanager-interface.md)
- [Interfaces de hospedaje](hosting-interfaces.md)
