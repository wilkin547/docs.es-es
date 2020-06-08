---
title: ICorProfilerCallback3::ProfilerAttachComplete (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback3.ProfilerAttachComplete Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback3::ProfilerAttachComplete
helpviewer_keywords:
- ProfilerAttachComplete method [.NET Framework profiling]
- ICorProfilerCallback3::ProfilerAttachComplete method [.NET Framework profiling]
ms.assetid: 257d6076-06e0-4d93-bb33-651fbb2b92d7
topic_type:
- apiref
ms.openlocfilehash: bcc938ff9322fca4f45366fdc695e0c3901484b5
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499667"
---
# <a name="icorprofilercallback3profilerattachcomplete-method"></a>ICorProfilerCallback3::ProfilerAttachComplete (Método)
Lo llama el Common Language Runtime (CLR) para indicar que el generador de perfiles ahora puede llamar a los métodos de puesta al día de [ICorProfilerInfo3:: EnumJITedFunctions (](icorprofilerinfo3-enumjitedfunctions-method.md) y [Icorprofilerinfo3:: EnumModules (](icorprofilerinfo3-enummodules-method.md) .  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT ProfilerAttachComplete ();  
```  
  
## <a name="remarks"></a>Comentarios  
 La `ProfilerAttachComplete` devolución de llamada se emite después de llamar al método [ICorProfilerCallback3:: InitializeForAttach](icorprofilercallback3-initializeforattach-method.md) . Indica que:  
  
- Las devoluciones de llamada que solicitó el generador de perfiles en `InitializeForAttach` se han activado.  
  
- El generador de perfiles ya puede poner al día los identificadores asociados sin preocuparse sobre las notificaciones que faltan.  
  
 CLR pasa por alto el valor devuelto por esta devolución de llamada.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Consulte también:

- [ICorProfilerCallback (Interfaz)](icorprofilercallback-interface.md)
- [ICorProfilerInfo3 (Interfaz)](icorprofilerinfo3-interface.md)
- [Interfaces para generación de perfiles](profiling-interfaces.md)
- [Generación de perfiles](index.md)
