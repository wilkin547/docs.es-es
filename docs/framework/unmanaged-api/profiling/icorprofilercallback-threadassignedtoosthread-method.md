---
description: 'Más información sobre: ICorProfilerCallback:: Threadassignedtoosthread ((método)'
title: ICorProfilerCallback::ThreadAssignedToOSThread (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ThreadAssignedToOSThread
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ThreadAssignedToOSThread
helpviewer_keywords:
- ThreadAssignedToOSThread method [.NET Framework profiling]
- ICorProfilerCallback::ThreadAssignedToOSThread method [.NET Framework profiling]
ms.assetid: f9671e5a-7b14-4f5b-8404-58136422c8b2
topic_type:
- apiref
ms.openlocfilehash: 04fba4cabb0ac58b3afeaae1fd579865335a9e14
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99647991"
---
# <a name="icorprofilercallbackthreadassignedtoosthread-method"></a>ICorProfilerCallback::ThreadAssignedToOSThread (Método)

Notifica al generador de perfiles que un subproceso administrado se está implementando utilizando un subproceso del sistema operativo determinado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT ThreadAssignedToOSThread(  
    [in] ThreadID managedThreadId,  
    [in] DWORD    osThreadId);  
```  
  
## <a name="parameters"></a>Parámetros  

 `managedThreadId`  
 de Identificador del subproceso administrado.  
  
 `osThreadId`  
 de Identificador del subproceso del sistema operativo.  
  
## <a name="remarks"></a>Observaciones  

 La `ThreadAssignedToOSThread` devolución de llamada existe para que el generador de perfiles pueda mantener una asignación precisa entre fibras de subprocesos del sistema operativo y subprocesos administrados.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerCallback (Interfaz)](icorprofilercallback-interface.md)
