---
title: ETaskType (Enumeración)
ms.date: 03/30/2017
api_name:
- ETaskType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ETaskType
helpviewer_keywords:
- ETaskType enumeration [.NET Framework hosting]
ms.assetid: aa527b31-89d4-41f2-ad6f-63b76950b7df
topic_type:
- apiref
ms.openlocfilehash: 0fa72568df77c4916a3c6676e1dcca7c0c616c4a
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84493323"
---
# <a name="etasktype-enumeration"></a>ETaskType (Enumeración)
Contiene valores que indican el tipo de tarea que está representada por una interfaz [ICLRTask](iclrtask-interface.md) o [IHostTask](ihosttask-interface.md) .  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef enum ETaskType {  
    TT_DEBUGGERHELPER           = 0x1,  
    TT_GC                       = 0x2,  
    TT_FINALIZER                = 0x4,  
    TT_THREADPOOL_TIMER         = 0x8,  
    TT_THREADPOOL_GATE          = 0x10,  
    TT_THREADPOOL_WORKER        = 0x20,  
    TT_THREADPOOL_IOCOMPLETION  = 0x40,  
    TT_ADUNLOAD                 = 0x80,  
    TT_USER                     = 0x100,  
    TT_THREADPOOL_WAIT          = 0x200,  
    TT_UNKNOWN                  = 0x80000000  
} ETaskType;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`TT_ADUNLOAD`|La interfaz representa una tarea de descarga de dominio de aplicación.|  
|`TT_DEBUGGERHELPER`|La interfaz representa una tarea auxiliar del depurador.|  
|`TT_FINALIZER`|La interfaz representa una tarea de finalizador.|  
|`TT_GC`|La interfaz representa una tarea de recolección de elementos no utilizados.|  
|`TT_THREADPOOL_GATE`|La interfaz representa una tarea de subproceso de puerta.|  
|`TT_THREADPOOL_IOCOMPLETION`|La interfaz representa una tarea de subproceso de e/s o una tarea de subproceso de puerto de finalización.|  
|`TT_THREADPOOL_TIMER`|La interfaz representa una tarea de subproceso de temporizador.|  
|`TT_THREADPOOL_WAIT`|La interfaz representa una tarea de subproceso de espera.|  
|`TT_THREADPOOL_WORKER`|La interfaz representa una tarea de subproceso de trabajo.|  
|`TT_UNKNOWN`|La tarea es desconocida.|  
|`TT_USER`|La interfaz representa una tarea de usuario.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** MSCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también:

- [Enumeraciones para hosts](hosting-enumerations.md)
