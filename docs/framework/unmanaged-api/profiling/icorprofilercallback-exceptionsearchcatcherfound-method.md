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
ms.openlocfilehash: 8f5997dddf78dd75d482bc45d2ee730b20d9ab16
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866483"
---
# <a name="icorprofilercallbackexceptionsearchcatcherfound-method"></a><span data-ttu-id="69731-102">ICorProfilerCallback::ExceptionSearchCatcherFound (Método)</span><span class="sxs-lookup"><span data-stu-id="69731-102">ICorProfilerCallback::ExceptionSearchCatcherFound Method</span></span>
<span data-ttu-id="69731-103">Notifica al generador de perfiles que la fase de búsqueda del control de excepciones ha encontrado un controlador para la excepción que se produjo.</span><span class="sxs-lookup"><span data-stu-id="69731-103">Notifies the profiler that the search phase of exception handling has located a handler for the exception that was thrown.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69731-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="69731-104">Syntax</span></span>  
  
```cpp  
RESULT ExceptionSearchCatcherFound(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="69731-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="69731-105">Parameters</span></span>

- `functionId`

  <span data-ttu-id="69731-106">\[en] identificador de la función que contiene el controlador de excepciones.</span><span class="sxs-lookup"><span data-stu-id="69731-106">\[in] The ID of the function that contains the exception handler.</span></span>

## <a name="requirements"></a><span data-ttu-id="69731-107">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="69731-107">Requirements</span></span>  
 <span data-ttu-id="69731-108">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="69731-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="69731-109">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="69731-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="69731-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="69731-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="69731-111">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="69731-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69731-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="69731-112">See also</span></span>

- [<span data-ttu-id="69731-113">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="69731-113">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
