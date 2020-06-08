---
title: ICorProfilerInfo::GetFunctionFromToken (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetFunctionFromToken
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetFunctionFromToken
helpviewer_keywords:
- ICorProfilerInfo::GetFunctionFromToken method [.NET Framework profiling]
- GetFunctionFromToken method, ICorProfilerInfo interface [.NET Framework profiling]
ms.assetid: 0eed759f-cce8-405d-88dc-9ee293a38928
topic_type:
- apiref
ms.openlocfilehash: 18c3b6e840ec1f6cb1481c8d752e6399dcdae077
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84498146"
---
# <a name="icorprofilerinfogetfunctionfromtoken-method"></a>ICorProfilerInfo::GetFunctionFromToken (Método)
Obtiene el identificador de una función. Este método está obsoleto en la .NET Framework versión 2,0. Use en su lugar el método [ICorProfilerInfo2:: GetFunctionFromTokenAndTypeArgs (](icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md) .  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetFunctionFromToken(  
    [in]  ModuleID   moduleId,  
    [in]  mdToken    token,  
    [out] FunctionID *pFunctionId);  
```  
  
## <a name="remarks"></a>Comentarios  
 El `GetFunctionFromToken` método no funcionará para funciones o funciones genéricas en tipos genéricos; ahora está obsoleto. Se usa `ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs` para todas las funciones.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** 1,1, 1,0  
  
## <a name="see-also"></a>Consulte también:

- [ICorProfilerInfo (Interfaz)](icorprofilerinfo-interface.md)
