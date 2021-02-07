---
description: 'Más información sobre: ICorProfilerCallback:: Exceptionsearchfunctionenter ((método)'
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
ms.openlocfilehash: 6e77ab5dc8c15a1d0785fb83310183c0a4693225
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99706206"
---
# <a name="icorprofilercallbackexceptionsearchfunctionenter-method"></a><span data-ttu-id="999b6-103">ICorProfilerCallback::ExceptionSearchFunctionEnter (Método)</span><span class="sxs-lookup"><span data-stu-id="999b6-103">ICorProfilerCallback::ExceptionSearchFunctionEnter Method</span></span>

<span data-ttu-id="999b6-104">Notifica al generador de perfiles que la fase de búsqueda del control de excepciones ha empezado a buscar una función para encontrar un controlador para la excepción actual.</span><span class="sxs-lookup"><span data-stu-id="999b6-104">Notifies the profiler that the search phase of exception handling has begun searching a function to find a handler for the current exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="999b6-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="999b6-105">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionSearchFunctionEnter(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="999b6-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="999b6-106">Parameters</span></span>

- `functionId`

  <span data-ttu-id="999b6-107">\[in] identificador de la función que se ha especificado.</span><span class="sxs-lookup"><span data-stu-id="999b6-107">\[in] The ID of the function that has been entered.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="999b6-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="999b6-108">Requirements</span></span>  

 <span data-ttu-id="999b6-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="999b6-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="999b6-110">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="999b6-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="999b6-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="999b6-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="999b6-112">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="999b6-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="999b6-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="999b6-113">See also</span></span>

- [<span data-ttu-id="999b6-114">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="999b6-114">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="999b6-115">Método ExceptionSearchFunctionLeave</span><span class="sxs-lookup"><span data-stu-id="999b6-115">ExceptionSearchFunctionLeave Method</span></span>](icorprofilercallback-exceptionsearchfunctionleave-method.md)
