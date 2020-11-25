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
ms.openlocfilehash: 9c39d984db62326b31a4760a817ee82def6dd78f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699825"
---
# <a name="icorprofilercallbackexceptionsearchfunctionenter-method"></a><span data-ttu-id="eb747-102">ICorProfilerCallback::ExceptionSearchFunctionEnter (Método)</span><span class="sxs-lookup"><span data-stu-id="eb747-102">ICorProfilerCallback::ExceptionSearchFunctionEnter Method</span></span>

<span data-ttu-id="eb747-103">Notifica al generador de perfiles que la fase de búsqueda del control de excepciones ha empezado a buscar una función para encontrar un controlador para la excepción actual.</span><span class="sxs-lookup"><span data-stu-id="eb747-103">Notifies the profiler that the search phase of exception handling has begun searching a function to find a handler for the current exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb747-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="eb747-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionSearchFunctionEnter(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eb747-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="eb747-105">Parameters</span></span>

- `functionId`

  <span data-ttu-id="eb747-106">\[in] identificador de la función que se ha especificado.</span><span class="sxs-lookup"><span data-stu-id="eb747-106">\[in] The ID of the function that has been entered.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="eb747-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="eb747-107">Requirements</span></span>  

 <span data-ttu-id="eb747-108">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eb747-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eb747-109">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="eb747-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="eb747-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eb747-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eb747-111">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eb747-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb747-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="eb747-112">See also</span></span>

- [<span data-ttu-id="eb747-113">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="eb747-113">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="eb747-114">Método ExceptionSearchFunctionLeave</span><span class="sxs-lookup"><span data-stu-id="eb747-114">ExceptionSearchFunctionLeave Method</span></span>](icorprofilercallback-exceptionsearchfunctionleave-method.md)
