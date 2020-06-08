---
title: ICorProfilerCallback::ExceptionSearchCatcherFound (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionSearchCatcherFound
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionSearchCatcherFound
helpviewer_keywords:
- ExceptionSearchCatcherFound method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionSearchCatcherFound method [.NET Framework profiling]
ms.assetid: 190f424d-5e37-4163-a191-0895686e9476
topic_type:
- apiref
ms.openlocfilehash: 70c03d34bdf9bd315994b2bfa09631efac2565ef
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500226"
---
# <a name="icorprofilercallbackexceptionsearchcatcherfound-method"></a><span data-ttu-id="69a7c-102">ICorProfilerCallback::ExceptionSearchCatcherFound (Método)</span><span class="sxs-lookup"><span data-stu-id="69a7c-102">ICorProfilerCallback::ExceptionSearchCatcherFound Method</span></span>
<span data-ttu-id="69a7c-103">Notifica al generador de perfiles que la fase de búsqueda del control de excepciones ha encontrado un controlador para la excepción que se produjo.</span><span class="sxs-lookup"><span data-stu-id="69a7c-103">Notifies the profiler that the search phase of exception handling has located a handler for the exception that was thrown.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69a7c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="69a7c-104">Syntax</span></span>  
  
```cpp  
RESULT ExceptionSearchCatcherFound(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="69a7c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="69a7c-105">Parameters</span></span>

- `functionId`

  <span data-ttu-id="69a7c-106">\[in] identificador de la función que contiene el controlador de excepciones.</span><span class="sxs-lookup"><span data-stu-id="69a7c-106">\[in] The ID of the function that contains the exception handler.</span></span>

## <a name="requirements"></a><span data-ttu-id="69a7c-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="69a7c-107">Requirements</span></span>  
 <span data-ttu-id="69a7c-108">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="69a7c-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="69a7c-109">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="69a7c-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="69a7c-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="69a7c-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="69a7c-111">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="69a7c-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69a7c-112">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="69a7c-112">See also</span></span>

- [<span data-ttu-id="69a7c-113">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="69a7c-113">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
