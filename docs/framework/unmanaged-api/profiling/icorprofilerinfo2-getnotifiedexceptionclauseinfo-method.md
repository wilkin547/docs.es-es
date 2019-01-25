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
# <a name="icorprofilerinfo2getnotifiedexceptionclauseinfo-method"></a><span data-ttu-id="a1bc1-102">ICorProfilerInfo2::GetNotifiedExceptionClauseInfo (Método)</span><span class="sxs-lookup"><span data-stu-id="a1bc1-102">ICorProfilerInfo2::GetNotifiedExceptionClauseInfo Method</span></span>
<span data-ttu-id="a1bc1-103">Obtiene la información de dirección y el marco nativa para la cláusula de excepción (`catch`/`finally`/`filter`) que se va a ejecutarse o que recientemente se ha ejecutado.</span><span class="sxs-lookup"><span data-stu-id="a1bc1-103">Gets the native address and frame information for the exception clause (`catch`/`finally`/`filter`) that is about to be run or has just been run.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1bc1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a1bc1-104">Syntax</span></span>  
  
```  
HRESULT GetNotifiedExceptionClauseInfo(  
    [out] COR_PRF_EX_CLAUSE_INFO *pinfo);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a1bc1-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a1bc1-105">Parameters</span></span>  
 `pinfo`  
 <span data-ttu-id="a1bc1-106">[out] Un puntero a un [COR_PRF_EX_CLAUSE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-ex-clause-info-structure.md) estructura que describe la instancia actual de cláusula de excepción y su marco asociado.</span><span class="sxs-lookup"><span data-stu-id="a1bc1-106">[out] A pointer to a [COR_PRF_EX_CLAUSE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-ex-clause-info-structure.md) structure that describes the current exception clause instance and its associated frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a1bc1-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a1bc1-107">Remarks</span></span>  
 <span data-ttu-id="a1bc1-108">Cuando se recibe una notificación de excepción, `GetNotifiedExceptionClauseInfo` puede usarse para obtener la información de dirección y el marco nativa para la cláusula de excepción (`catch`/`finally`/`filter`) que está a punto de ejecutarse ([ ExceptionCatcherEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherenter-method.md), [ExceptionUnwindFinallyEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyenter-method.md), o [ExceptionSearchFilterEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterenter-method.md)el generador de perfiles recibe la devolución de llamada) o recientemente ejecutado ([ExceptionCatcherLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherleave-method.md), [ExceptionUnwindFinallyLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyleave-method.md), o [ ExceptionSearchFilterLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterleave-method.md) el generador de perfiles recibe la devolución de llamada).</span><span class="sxs-lookup"><span data-stu-id="a1bc1-108">When an exception notification is received, `GetNotifiedExceptionClauseInfo` can be used to get the native address and frame information for the exception clause (`catch`/`finally`/`filter`) that is about to be run ([ICorProfilerCallback::ExceptionCatcherEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherenter-method.md), [ICorProfilerCallback::ExceptionUnwindFinallyEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyenter-method.md), or [ICorProfilerCallback::ExceptionSearchFilterEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterenter-method.md) callback is received by the profiler) or has just been run ([ICorProfilerCallback::ExceptionCatcherLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherleave-method.md), [ICorProfilerCallback::ExceptionUnwindFinallyLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyleave-method.md), or [ICorProfilerCallback::ExceptionSearchFilterLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterleave-method.md) callback is received by the profiler).</span></span>  
  
 <span data-ttu-id="a1bc1-109">Esta llamada se puede realizar en cualquier momento después de una de las devoluciones de llamada ENTRAR anteriores hasta que se recibe la devolución de llamada deje coincidente o se produce una excepción anidada en la cláusula actual, en cuyo caso hay no es ninguna notificación deje de dicha cláusula.</span><span class="sxs-lookup"><span data-stu-id="a1bc1-109">This call can be made at any time after one of the Enter callbacks above until either the matching Leave callback is received or a nested exception is thrown in the current clause, in which case there is no Leave notification for that clause.</span></span> <span data-ttu-id="a1bc1-110">Tenga en cuenta que no es posible que produzca una excepción de escape un `filter` cláusula de excepción, por lo que siempre hay una notificación Leave en ese caso.</span><span class="sxs-lookup"><span data-stu-id="a1bc1-110">Note that it is not possible for a thrown exception to escape a `filter` exception clause, so there is always a Leave notification in that case.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1bc1-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a1bc1-111">Requirements</span></span>  
 <span data-ttu-id="a1bc1-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a1bc1-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1bc1-113">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a1bc1-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a1bc1-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a1bc1-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a1bc1-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a1bc1-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1bc1-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="a1bc1-116">See also</span></span>
- [<span data-ttu-id="a1bc1-117">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a1bc1-117">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="a1bc1-118">ICorProfilerInfo2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a1bc1-118">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
