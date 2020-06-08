---
title: ICorProfilerInfo4::EnumJITedFunctions2 (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.EnumJITedFunctions2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::EnumJITedFunctions2
helpviewer_keywords:
- EnumJITedFunctions2 method, ICorProfilerInfo4 interface [.NET Framework profiling]
- ICorProfilerInfo4::EnumJITedFunctions2 method [.NET Framework profiling]
ms.assetid: 40e9a1be-9bd2-4fad-9921-34a84b61c1e3
topic_type:
- apiref
ms.openlocfilehash: 2c4a89d5f96ef572518f25bf58a0005454f8e3f0
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84496136"
---
# <a name="icorprofilerinfo4enumjitedfunctions2-method"></a>ICorProfilerInfo4::EnumJITedFunctions2 (Método)
Devuelve un enumerador para todas las funciones compiladas previamente y compiladas con JIT. Este método reemplaza el método [ICorProfilerInfo3:: EnumJITedFunctions (](icorprofilerinfo3-enumjitedfunctions-method.md) , que no enumera los identificadores de recompilación JIT.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT EnumJITedFunctions([out] ICorProfilerFunctionEnum** ppEnum);  
```  
  
## <a name="parameters"></a>Parámetros  
 `ppEnum`  
 enuncia Puntero al enumerador [ICorProfilerFunctionEnum](icorprofilerfunctionenum-interface.md) .  
  
## <a name="remarks"></a>Comentarios  
 Este método se puede superponer con `JITCompilation` devoluciones de llamada como el método [ICorProfilerCallback:: JITCompilationStarted](icorprofilercallback-jitcompilationstarted-method.md) . La enumeración devuelta incluye valores para el `COR_PRF_FUNCTION::reJitId` campo. El método [ICorProfilerInfo3:: EnumJITedFunctions (](icorprofilerinfo3-enumjitedfunctions-method.md) , que este método reemplaza, no enumera los identificadores compilados con JIT, ya que el `COR_PRF_FUNCTION::reJitId` campo siempre se establece en 0. El `ICorProfilerInfo4::EnumJITedFunctions` método enumera los identificadores de recompilación JIT, ya que el `COR_PRF_FUNCTION::reJitId` campo se ha establecido correctamente. Tenga en cuenta que el método [ICorProfilerInfo4:: enumjitedfunctions2 (](icorprofilerinfo4-enumjitedfunctions2-method.md) puede desencadenar una recolección de elementos no utilizados, mientras que el [método ICorProfilerInfo3:: EnumJITedFunctions (](icorprofilerinfo3-enumjitedfunctions-method.md) no lo hará.  Para obtener más información, vea [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](corprof-e-unsupported-call-sequence-hresult.md).  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Consulte también:

- [Método EnumJITedFunctions](icorprofilerinfo3-enumjitedfunctions-method.md)
- [ICorProfilerInfo4 (Interfaz)](icorprofilerinfo4-interface.md)
- [Interfaces para generación de perfiles](profiling-interfaces.md)
- [Generación de perfiles](index.md)
