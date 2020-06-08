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
ms.openlocfilehash: 08337a118a80d213f16e2a16f744b96f5dde2e7f
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84497011"
---
# <a name="icorprofilerinfo2getnotifiedexceptionclauseinfo-method"></a>ICorProfilerInfo2::GetNotifiedExceptionClauseInfo (Método)
Obtiene la información de la dirección nativa y el marco de la cláusula de excepción ( `catch` / `finally` / `filter` ) que está a punto de ejecutarse o que se acaba de ejecutar.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetNotifiedExceptionClauseInfo(  
    [out] COR_PRF_EX_CLAUSE_INFO *pinfo);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pinfo`  
 enuncia Puntero a una estructura de [COR_PRF_EX_CLAUSE_INFO](cor-prf-ex-clause-info-structure.md) que describe la instancia de la cláusula de excepción actual y su marco asociado.  
  
## <a name="remarks"></a>Comentarios  
 Cuando se recibe una notificación de excepción, `GetNotifiedExceptionClauseInfo` se puede usar para obtener la información de la dirección nativa y el marco de la cláusula de excepción ( `catch` / `finally` / `filter` ) que está a punto de ejecutarse (el generador de perfiles recibe las llamadas a[ICorProfilerCallback:: exceptioncatcherenter (](icorprofilercallback-exceptioncatcherenter-method.md), [ICorProfilerCallback:: exceptionunwindfinallyenter (](icorprofilercallback-exceptionunwindfinallyenter-method.md)o [ICorProfilerCallback:: exceptionsearchfilterenter (](icorprofilercallback-exceptionsearchfilterenter-method.md) ) o se acaba de ejecutar (el generador de perfiles recibe la llamada a[ICorProfilerCallback:: exceptioncatcherleave (](icorprofilercallback-exceptioncatcherleave-method.md), [ICorProfilerCallback:: ExceptionUnwindFinallyLeave (](icorprofilercallback-exceptionunwindfinallyleave-method.md)o [ICorProfilerCallback:](icorprofilercallback-exceptionsearchfilterleave-method.md)  
  
 Esta llamada se puede realizar en cualquier momento después de una de las devoluciones de llamada Enter anteriores hasta que se reciba la devolución de llamada Leave correspondiente o se produzca una excepción anidada en la cláusula actual, en cuyo caso no hay ninguna notificación Leave para esa cláusula. Tenga en cuenta que no es posible que una excepción iniciada escape una `filter` cláusula de excepción, por lo que siempre hay una notificación Leave en ese caso.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también:

- [ICorProfilerInfo (Interfaz)](icorprofilerinfo-interface.md)
- [ICorProfilerInfo2 (Interfaz)](icorprofilerinfo2-interface.md)
