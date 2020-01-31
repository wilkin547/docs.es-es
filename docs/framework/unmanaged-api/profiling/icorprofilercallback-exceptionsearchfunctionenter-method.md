---
title: ICorProfilerCallback::ExceptionSearchFunctionEnter (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionSearchFunctionEnter
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionSearchFunctionEnter
helpviewer_keywords:
- ExceptionSearchFunctionEnter method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionSearchFunctionEnter method [.NET Framework profiling]
ms.assetid: bfd54573-b7e6-4bd1-a184-7f08a8b39fae
topic_type:
- apiref
ms.openlocfilehash: a64fe598bd9f50b822edb869fa9efca2a4ff280a
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790128"
---
# <a name="icorprofilercallbackexceptionsearchfunctionenter-method"></a><span data-ttu-id="d360d-102">ICorProfilerCallback::ExceptionSearchFunctionEnter (Método)</span><span class="sxs-lookup"><span data-stu-id="d360d-102">ICorProfilerCallback::ExceptionSearchFunctionEnter Method</span></span>
<span data-ttu-id="d360d-103">Notifica al generador de perfiles que la fase de búsqueda del control de excepciones ha empezado a buscar una función para encontrar un controlador para la excepción actual.</span><span class="sxs-lookup"><span data-stu-id="d360d-103">Notifies the profiler that the search phase of exception handling has begun searching a function to find a handler for the current exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d360d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d360d-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionSearchFunctionEnter(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d360d-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="d360d-105">Parameters</span></span>

- `functionId`

  <span data-ttu-id="d360d-106">\[en] identificador de la función que se ha especificado.</span><span class="sxs-lookup"><span data-stu-id="d360d-106">\[in] The ID of the function that has been entered.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="d360d-107">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="d360d-107">Requirements</span></span>  
 <span data-ttu-id="d360d-108">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d360d-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d360d-109">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d360d-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d360d-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d360d-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d360d-111">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d360d-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d360d-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="d360d-112">See also</span></span>

- [<span data-ttu-id="d360d-113">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d360d-113">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="d360d-114">ExceptionSearchFunctionLeave (método)</span><span class="sxs-lookup"><span data-stu-id="d360d-114">ExceptionSearchFunctionLeave Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionleave-method.md)
