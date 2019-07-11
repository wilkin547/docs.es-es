---
title: ICorProfilerInfo::GetCurrentThreadID (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetCurrentThreadID
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetCurrentThreadID
helpviewer_keywords:
- GetCurrentThreadID method, ICorProfilerInfo interface [.NET Framework profiling]
- ICorProfilerInfo::GetCurrentThreadID method [.NET Framework profiling]
ms.assetid: 39bbdb30-6a7a-4202-8da3-67ae9a0ab3a8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: db5ed871734205d59c602cc8b5c0cc9e8ac4682a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67762870"
---
# <a name="icorprofilerinfogetcurrentthreadid-method"></a>ICorProfilerInfo::GetCurrentThreadID (Método)
Obtiene el identificador del subproceso actual, si es un subproceso administrado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetCurrentThreadID(  
    [out] ThreadID *pThreadId);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pThreadId`  
 [out] Un puntero al identificador devuelto del subproceso administrado.  
  
## <a name="remarks"></a>Comentarios  
 Si el subproceso actual es un subproceso en tiempo de ejecución interno u otro subproceso no administrado, `GetCurrentThreadID` devuelve CORPROF_E_NOT_MANAGED_THREAD como HRESULT y el valor devuelto de la `pThreadId` parámetro será nulo.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerInfo (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
