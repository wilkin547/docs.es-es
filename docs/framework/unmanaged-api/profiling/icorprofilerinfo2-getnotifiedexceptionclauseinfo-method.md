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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 736fde9de1a7d4fa50d6a07bf17eacd742a6b86d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54683890"
---
# <a name="icorprofilerinfo2getnotifiedexceptionclauseinfo-method"></a>ICorProfilerInfo2::GetNotifiedExceptionClauseInfo (Método)
Obtiene la información de dirección y el marco nativa para la cláusula de excepción (`catch`/`finally`/`filter`) que se va a ejecutarse o que recientemente se ha ejecutado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetNotifiedExceptionClauseInfo(  
    [out] COR_PRF_EX_CLAUSE_INFO *pinfo);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `pinfo`  
 [out] Un puntero a un [COR_PRF_EX_CLAUSE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-ex-clause-info-structure.md) estructura que describe la instancia actual de cláusula de excepción y su marco asociado.  
  
## <a name="remarks"></a>Comentarios  
 Cuando se recibe una notificación de excepción, `GetNotifiedExceptionClauseInfo` puede usarse para obtener la información de dirección y el marco nativa para la cláusula de excepción (`catch`/`finally`/`filter`) que está a punto de ejecutarse ([ ExceptionCatcherEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherenter-method.md), [ExceptionUnwindFinallyEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyenter-method.md), o [ExceptionSearchFilterEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterenter-method.md)el generador de perfiles recibe la devolución de llamada) o recientemente ejecutado ([ExceptionCatcherLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherleave-method.md), [ExceptionUnwindFinallyLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyleave-method.md), o [ ExceptionSearchFilterLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterleave-method.md) el generador de perfiles recibe la devolución de llamada).  
  
 Esta llamada se puede realizar en cualquier momento después de una de las devoluciones de llamada ENTRAR anteriores hasta que se recibe la devolución de llamada deje coincidente o se produce una excepción anidada en la cláusula actual, en cuyo caso hay no es ninguna notificación deje de dicha cláusula. Tenga en cuenta que no es posible que produzca una excepción de escape un `filter` cláusula de excepción, por lo que siempre hay una notificación Leave en ese caso.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [ICorProfilerInfo (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [ICorProfilerInfo2 (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
