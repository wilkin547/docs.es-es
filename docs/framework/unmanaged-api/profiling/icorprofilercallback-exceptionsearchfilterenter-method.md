---
title: ICorProfilerCallback::ExceptionSearchFilterEnter (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionSearchFilterEnter
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionSearchFilterEnter
helpviewer_keywords:
- ExceptionSearchFilterEnter method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionSearchFilterEnter method [.NET Framework profiling]
ms.assetid: acc239ce-3eef-418c-b1df-c5a6dd8e8a4c
topic_type:
- apiref
ms.openlocfilehash: 710dbe70b0a2498a3d521cdc813c4ead7ba6442e
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866434"
---
# <a name="icorprofilercallbackexceptionsearchfilterenter-method"></a><span data-ttu-id="885f9-102">ICorProfilerCallback::ExceptionSearchFilterEnter (Método)</span><span class="sxs-lookup"><span data-stu-id="885f9-102">ICorProfilerCallback::ExceptionSearchFilterEnter Method</span></span>
<span data-ttu-id="885f9-103">Notifica al generador de perfiles que la fase de búsqueda del control de excepciones ha empezado a ejecutar un filtro de excepción definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="885f9-103">Notifies the profiler that the search phase of exception handling has begun executing a user-defined exception filter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="885f9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="885f9-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionSearchFilterEnter(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="885f9-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="885f9-105">Parameters</span></span>

- `functionId`

  <span data-ttu-id="885f9-106">\[en] identificador de la función que contiene el filtro.</span><span class="sxs-lookup"><span data-stu-id="885f9-106">\[in] The ID of the function that contains the filter.</span></span>

## <a name="requirements"></a><span data-ttu-id="885f9-107">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="885f9-107">Requirements</span></span>  
 <span data-ttu-id="885f9-108">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="885f9-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="885f9-109">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="885f9-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="885f9-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="885f9-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="885f9-111">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="885f9-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="885f9-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="885f9-112">See also</span></span>

- [<span data-ttu-id="885f9-113">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="885f9-113">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="885f9-114">ExceptionSearchFilterLeave (método)</span><span class="sxs-lookup"><span data-stu-id="885f9-114">ExceptionSearchFilterLeave Method</span></span>](icorprofilercallback-exceptionsearchfilterleave-method.md)
