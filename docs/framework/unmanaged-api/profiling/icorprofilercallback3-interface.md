---
title: ICorProfilerCallback3 (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback3
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback3
helpviewer_keywords:
- ICorProfilerCallback3 interface [.NET Framework profiling]
ms.assetid: be83af41-3dec-4c77-8529-9dd6b8042af6
topic_type:
- apiref
ms.openlocfilehash: db07e2afa64ea2bf80416e6ab8cba5a4dcdc8dcf
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499680"
---
# <a name="icorprofilercallback3-interface"></a>ICorProfilerCallback3 (Interfaz)
Proporciona métodos de devolución de llamada que el Common Language Runtime (CLR) utiliza para comunicar la información de estado de asociación y desasociación al generador de perfiles.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método InitializeForAttach](icorprofilercallback3-initializeforattach-method.md)|Lo llama el CLR para dar al generador de perfiles una oportunidad de inicializar su estado después de una operación de adjuntar.|  
|[Método ProfilerAttachComplete](icorprofilercallback3-profilerattachcomplete-method.md)|Lo llama el CLR para indicar que el generador de perfiles ahora puede llamar a los métodos de puesta al día.|  
|[Método ProfilerDetachSucceeded](icorprofilercallback3-profilerdetachsucceeded-method.md)|Notifica al generador de perfiles que Common Language Runtime (CLR) está a punto de descargar el archivo DLL del generador de perfiles.|  
  
## <a name="remarks"></a>Observaciones  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Consulte también:

- [Interfaces para generación de perfiles](profiling-interfaces.md)
- [ICorProfilerInfo (Interfaz)](icorprofilerinfo-interface.md)
- [ICorProfilerCallback2 (Interfaz)](icorprofilercallback2-interface.md)
- [ICorProfilerCallback4 (Interfaz)](icorprofilercallback4-interface.md)
