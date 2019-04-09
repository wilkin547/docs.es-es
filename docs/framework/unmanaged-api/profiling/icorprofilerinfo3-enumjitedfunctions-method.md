---
title: ICorProfilerInfo3::EnumJITedFunctions (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.EnumJITedFunctions Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::EnumJITedFunctions
helpviewer_keywords:
- ICorProfilerInfo3::EnumJITedFunctions method [.NET Framework profiling]
- EnumJITedFunctions method [.NET Framework profiling]
ms.assetid: e2847a36-f460-45e2-9b6c-b33b008f40d9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7525d107fec7229d9b86eee63bde2aaf2d701b1b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59190306"
---
# <a name="icorprofilerinfo3enumjitedfunctions-method"></a>ICorProfilerInfo3::EnumJITedFunctions (Método)
Devuelve un enumerador para todas las funciones que estaban previamente compiladas con JIT.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT EnumJITedFunctions([out] ICorProfilerFunctionEnum** ppEnum);  
```  
  
## <a name="parameters"></a>Parámetros  
 `ppEnum`  
 [out] Un puntero a la [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) enumerador.  
  
## <a name="remarks"></a>Comentarios  
 Este método se puede superponer con `JITCompilation` las devoluciones de llamada, como el [JITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md) método. El enumerador devuelto por este método no incluye funciones que se cargan desde imágenes nativas generadas con Ngen.exe.  
  
> [!NOTE]
>  La enumeración devuelta incluye solo "0" para el valor de la `COR_PRF_FUNCTION::reJitId` campo.  Si necesita válido `COR_PRF_FUNCTION::reJitId` valores, utilice el [ICorProfilerInfo4::EnumJITedFunctions2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumjitedfunctions2-method.md) método.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerInfo3 (Interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [Interfaces para generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [Generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/index.md)
