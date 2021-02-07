---
description: 'Más información acerca de: ICorProfilerInfo2:: Getnotifiedexceptionclauseinfo ((método)'
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
ms.openlocfilehash: f297689ccdd1b600fe86db16940434c990e4b084
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99716489"
---
# <a name="icorprofilerinfo2getnotifiedexceptionclauseinfo-method"></a><span data-ttu-id="41fad-103">ICorProfilerInfo2::GetNotifiedExceptionClauseInfo (Método)</span><span class="sxs-lookup"><span data-stu-id="41fad-103">ICorProfilerInfo2::GetNotifiedExceptionClauseInfo Method</span></span>

<span data-ttu-id="41fad-104">Obtiene la información de la dirección nativa y el marco de la cláusula de excepción ( `catch` / `finally` / `filter` ) que está a punto de ejecutarse o que se acaba de ejecutar.</span><span class="sxs-lookup"><span data-stu-id="41fad-104">Gets the native address and frame information for the exception clause (`catch`/`finally`/`filter`) that is about to be run or has just been run.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41fad-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="41fad-105">Syntax</span></span>  
  
```cpp  
HRESULT GetNotifiedExceptionClauseInfo(  
    [out] COR_PRF_EX_CLAUSE_INFO *pinfo);  
```  
  
## <a name="parameters"></a><span data-ttu-id="41fad-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="41fad-106">Parameters</span></span>  

 `pinfo`  
 <span data-ttu-id="41fad-107">enuncia Puntero a una estructura de [COR_PRF_EX_CLAUSE_INFO](cor-prf-ex-clause-info-structure.md) que describe la instancia de la cláusula de excepción actual y su marco asociado.</span><span class="sxs-lookup"><span data-stu-id="41fad-107">[out] A pointer to a [COR_PRF_EX_CLAUSE_INFO](cor-prf-ex-clause-info-structure.md) structure that describes the current exception clause instance and its associated frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="41fad-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="41fad-108">Remarks</span></span>  

 <span data-ttu-id="41fad-109">Cuando se recibe una notificación de excepción, `GetNotifiedExceptionClauseInfo` se puede usar para obtener la información de la dirección nativa y el marco de la cláusula de excepción ( `catch` / `finally` / `filter` ) que está a punto de ejecutarse (el generador de perfiles recibe las llamadas a[ICorProfilerCallback:: exceptioncatcherenter (](icorprofilercallback-exceptioncatcherenter-method.md), [ICorProfilerCallback:: exceptionunwindfinallyenter (](icorprofilercallback-exceptionunwindfinallyenter-method.md)o [ICorProfilerCallback:: exceptionsearchfilterenter (](icorprofilercallback-exceptionsearchfilterenter-method.md) ) o se acaba de ejecutar (el generador de perfiles recibe la llamada a[ICorProfilerCallback:: exceptioncatcherleave (](icorprofilercallback-exceptioncatcherleave-method.md), [ICorProfilerCallback:: ExceptionUnwindFinallyLeave (](icorprofilercallback-exceptionunwindfinallyleave-method.md)o [ICorProfilerCallback:](icorprofilercallback-exceptionsearchfilterleave-method.md)</span><span class="sxs-lookup"><span data-stu-id="41fad-109">When an exception notification is received, `GetNotifiedExceptionClauseInfo` can be used to get the native address and frame information for the exception clause (`catch`/`finally`/`filter`) that is about to be run ([ICorProfilerCallback::ExceptionCatcherEnter](icorprofilercallback-exceptioncatcherenter-method.md), [ICorProfilerCallback::ExceptionUnwindFinallyEnter](icorprofilercallback-exceptionunwindfinallyenter-method.md), or [ICorProfilerCallback::ExceptionSearchFilterEnter](icorprofilercallback-exceptionsearchfilterenter-method.md) callback is received by the profiler) or has just been run ([ICorProfilerCallback::ExceptionCatcherLeave](icorprofilercallback-exceptioncatcherleave-method.md), [ICorProfilerCallback::ExceptionUnwindFinallyLeave](icorprofilercallback-exceptionunwindfinallyleave-method.md), or [ICorProfilerCallback::ExceptionSearchFilterLeave](icorprofilercallback-exceptionsearchfilterleave-method.md) callback is received by the profiler).</span></span>  
  
 <span data-ttu-id="41fad-110">Esta llamada se puede realizar en cualquier momento después de una de las devoluciones de llamada Enter anteriores hasta que se reciba la devolución de llamada Leave correspondiente o se produzca una excepción anidada en la cláusula actual, en cuyo caso no hay ninguna notificación Leave para esa cláusula.</span><span class="sxs-lookup"><span data-stu-id="41fad-110">This call can be made at any time after one of the Enter callbacks above until either the matching Leave callback is received or a nested exception is thrown in the current clause, in which case there is no Leave notification for that clause.</span></span> <span data-ttu-id="41fad-111">Tenga en cuenta que no es posible que una excepción iniciada escape una `filter` cláusula de excepción, por lo que siempre hay una notificación Leave en ese caso.</span><span class="sxs-lookup"><span data-stu-id="41fad-111">Note that it is not possible for a thrown exception to escape a `filter` exception clause, so there is always a Leave notification in that case.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="41fad-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="41fad-112">Requirements</span></span>  

 <span data-ttu-id="41fad-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="41fad-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="41fad-114">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="41fad-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="41fad-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="41fad-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="41fad-116">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="41fad-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41fad-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="41fad-117">See also</span></span>

- [<span data-ttu-id="41fad-118">ICorProfilerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="41fad-118">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="41fad-119">ICorProfilerInfo2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="41fad-119">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
