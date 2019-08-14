---
title: ICorProfilerInfo8::GetFunctionFromIP3
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo8.GetFunctionFromIP3
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: f3c0a3525c87fbf39199c15a6619ff4a0d2acc42
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2019
ms.locfileid: "68973855"
---
# <a name="icorprofilerinfo8getfunctionfromip3-method"></a>ICorProfilerInfo8:: GetFunctionFromIP3 (método)
  
  Asigna un puntero de instrucción de código administrado a un FunctionID. Este método funciona para los métodos dinámicos y no dinámicos.    
  
## <a name="syntax"></a>Sintaxis  
  
```cpp
HRESULT GetFunctionFromIP3([in] LPCBYTE ip,
                           [out] FunctionID *functionId,
                           [out] ReJITID * pReJitId);
```  
  
#### <a name="parameters"></a>Parámetros  
 `ip`  
 de Puntero de instrucción en código administrado.  

 `pFunctionId`  
 enuncia IDENTIFICADOR de la función.  
  
 `pReJitId`  
 enuncia La identidad de la versión recompilada con JIT de la función.  
  
## <a name="remarks"></a>Comentarios  
 Este método funciona para los métodos dinámicos y no dinámicos. Es un supraconjunto de [getfunctionfromip2 (](icorprofilerinfo4-getfunctionfromip2-method.md), que solo funciona con funciones con metadatos.
  

## <a name="requirements"></a>Requisitos  
 **Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Corprof. idl, Corprof. h  
  
 **Biblioteca** CorGuids.lib  
  
 **.NET Framework versiones:** [! INCLUIR[net_current_v472plus](../../../../includes/net-current-v472plus.md)  
  
## <a name="see-also"></a>Vea también
- [Interfaz ICorProfilerInfo8](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo8-interface.md)

