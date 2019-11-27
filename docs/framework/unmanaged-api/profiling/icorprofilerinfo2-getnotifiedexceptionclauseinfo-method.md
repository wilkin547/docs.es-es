---
title: ICorProfilerInfo2::GetNotifiedExceptionClauseInfo (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetNotifiedExceptionClauseInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetNotifiedExceptionClauseInfo
helpviewer_keywords:
- ICorProfilerInfo2::GetNotifiedExceptionCaluseInfo method [.NET Framework profiling]
- GetNotifiedExceptionCaluseInfo method [.NET Framework profiling]
ms.assetid: f9594a7e-cb0c-4c48-accb-29f762aa0c21
topic_type:
- apiref
ms.openlocfilehash: 52ad124638a1c1ec7d39fa41b9163f3ab50ffe70
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74433072"
---
# <a name="icorprofilerinfo2getnotifiedexceptionclauseinfo-method"></a>ICorProfilerInfo2::GetNotifiedExceptionClauseInfo (Método)
Obtiene la información de la dirección nativa y el marco de la cláusula de excepción (`catch`/`finally`/`filter`) que está a punto de ejecutarse o acaba de ejecutarse.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetNotifiedExceptionClauseInfo(  
    [out] COR_PRF_EX_CLAUSE_INFO *pinfo);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pinfo`  
 enuncia Puntero a una estructura de [COR_PRF_EX_CLAUSE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-ex-clause-info-structure.md) que describe la instancia de la cláusula de excepción actual y su marco asociado.  
  
## <a name="remarks"></a>Comentarios  
 Cuando se recibe una notificación de excepción, `GetNotifiedExceptionClauseInfo` se puede usar para obtener la información de la dirección nativa y el marco de la cláusula de excepción (`catch`/`finally`/`filter`) que está a punto de ejecutarse ([ICorProfilerCallback:: exceptioncatcherenter (](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherenter-method.md), [ICorProfilerCallback:: exceptionunwindfinallyenter (](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyenter-method.md)o [ICorProfilerCallback:: exceptionsearchfilterenter (](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterenter-method.md) callback es recibida por el generador de perfiles) o se acaba de ejecutar ([ICorProfilerCallback:: exceptioncatcherleave ( ](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherleave-method.md), El generador de perfiles recibe la devolución de llamada [ICorProfilerCallback:: ExceptionUnwindFinallyLeave (](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyleave-method.md)o [ICorProfilerCallback:: exceptionsearchfilterleave (](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterleave-method.md) ).  
  
 Esta llamada se puede realizar en cualquier momento después de una de las devoluciones de llamada Enter anteriores hasta que se reciba la devolución de llamada Leave correspondiente o se produzca una excepción anidada en la cláusula actual, en cuyo caso no hay ninguna notificación Leave para esa cláusula. Tenga en cuenta que no es posible que una excepción iniciada escape una cláusula de excepción `filter`, por lo que siempre hay una notificación Leave en ese caso.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerInfo (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [ICorProfilerInfo2 (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
