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
ms.openlocfilehash: a430631948230d16e5d04c869625b4c670faaf02
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868647"
---
# <a name="icorprofilerinfo2getnotifiedexceptionclauseinfo-method"></a>ICorProfilerInfo2::GetNotifiedExceptionClauseInfo (Método)
Obtiene la información de la dirección nativa y el marco de la cláusula de excepción (`catch`/`finally`/`filter`) que está a punto de ejecutarse o acaba de ejecutarse.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetNotifiedExceptionClauseInfo(  
    [out] COR_PRF_EX_CLAUSE_INFO *pinfo);  
```  
  
## <a name="parameters"></a>Parameters  
 `pinfo`  
 enuncia Puntero a una estructura de [COR_PRF_EX_CLAUSE_INFO](cor-prf-ex-clause-info-structure.md) que describe la instancia de la cláusula de excepción actual y su marco asociado.  
  
## <a name="remarks"></a>Notas  
 Cuando se recibe una notificación de excepción, `GetNotifiedExceptionClauseInfo` se puede usar para obtener la información de la dirección nativa y el marco de la cláusula de excepción (`catch`/`finally`/`filter`) que está a punto de ejecutarse ([ICorProfilerCallback:: exceptioncatcherenter (](icorprofilercallback-exceptioncatcherenter-method.md), [ICorProfilerCallback:: exceptionunwindfinallyenter (](icorprofilercallback-exceptionunwindfinallyenter-method.md)o [ICorProfilerCallback:: exceptionsearchfilterenter (](icorprofilercallback-exceptionsearchfilterenter-method.md) callback es recibida por el generador de perfiles) o se acaba de ejecutar ([ICorProfilerCallback:: exceptioncatcherleave ( ](icorprofilercallback-exceptioncatcherleave-method.md), El generador de perfiles recibe la devolución de llamada [ICorProfilerCallback:: ExceptionUnwindFinallyLeave (](icorprofilercallback-exceptionunwindfinallyleave-method.md)o [ICorProfilerCallback:: exceptionsearchfilterleave (](icorprofilercallback-exceptionsearchfilterleave-method.md) ).  
  
 Esta llamada se puede realizar en cualquier momento después de una de las devoluciones de llamada Enter anteriores hasta que se reciba la devolución de llamada Leave correspondiente o se produzca una excepción anidada en la cláusula actual, en cuyo caso no hay ninguna notificación Leave para esa cláusula. Tenga en cuenta que no es posible que una excepción iniciada escape una cláusula de excepción `filter`, por lo que siempre hay una notificación Leave en ese caso.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerInfo (interfaz)](icorprofilerinfo-interface.md)
- [ICorProfilerInfo2 (interfaz)](icorprofilerinfo2-interface.md)
