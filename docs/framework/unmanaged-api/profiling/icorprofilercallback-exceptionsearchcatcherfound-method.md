---
description: 'Más información sobre: ICorProfilerCallback:: ExceptionSearchCatcherFound ((método)'
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
ms.openlocfilehash: 080e9be61e4f10cbfb60696a5089aca0c3f2843f
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/20/2021
ms.locfileid: "104759994"
---
# <a name="icorprofilercallbackexceptionsearchcatcherfound-method"></a><span data-ttu-id="ebcb7-103">ICorProfilerCallback::ExceptionSearchCatcherFound (Método)</span><span class="sxs-lookup"><span data-stu-id="ebcb7-103">ICorProfilerCallback::ExceptionSearchCatcherFound Method</span></span>

<span data-ttu-id="ebcb7-104">Notifica al generador de perfiles que la fase de búsqueda del control de excepciones ha encontrado un controlador para la excepción que se produjo.</span><span class="sxs-lookup"><span data-stu-id="ebcb7-104">Notifies the profiler that the search phase of exception handling has located a handler for the exception that was thrown.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ebcb7-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ebcb7-105">Syntax</span></span>  
  
```cpp  
RESULT ExceptionSearchCatcherFound(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ebcb7-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ebcb7-106">Parameters</span></span>

<span data-ttu-id="ebcb7-107">`functionId` de IDENTIFICADOR de la función que contiene el controlador de excepciones.</span><span class="sxs-lookup"><span data-stu-id="ebcb7-107">`functionId` [in] The ID of the function that contains the exception handler.</span></span>

## <a name="requirements"></a><span data-ttu-id="ebcb7-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ebcb7-108">Requirements</span></span>  

 <span data-ttu-id="ebcb7-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ebcb7-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ebcb7-110">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ebcb7-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ebcb7-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ebcb7-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ebcb7-112">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ebcb7-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebcb7-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ebcb7-113">See also</span></span>

- [<span data-ttu-id="ebcb7-114">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ebcb7-114">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
