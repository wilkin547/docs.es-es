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
ms.openlocfilehash: b222e629cbfce2fde27c2d266b3a343466a1419c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99706323"
---
# <a name="icorprofilercallbackexceptionsearchcatcherfound-method"></a><span data-ttu-id="43dd5-103">ICorProfilerCallback::ExceptionSearchCatcherFound (Método)</span><span class="sxs-lookup"><span data-stu-id="43dd5-103">ICorProfilerCallback::ExceptionSearchCatcherFound Method</span></span>

<span data-ttu-id="43dd5-104">Notifica al generador de perfiles que la fase de búsqueda del control de excepciones ha encontrado un controlador para la excepción que se produjo.</span><span class="sxs-lookup"><span data-stu-id="43dd5-104">Notifies the profiler that the search phase of exception handling has located a handler for the exception that was thrown.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43dd5-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="43dd5-105">Syntax</span></span>  
  
```cpp  
RESULT ExceptionSearchCatcherFound(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="43dd5-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="43dd5-106">Parameters</span></span>

- `functionId`

  <span data-ttu-id="43dd5-107">\[in] identificador de la función que contiene el controlador de excepciones.</span><span class="sxs-lookup"><span data-stu-id="43dd5-107">\[in] The ID of the function that contains the exception handler.</span></span>

## <a name="requirements"></a><span data-ttu-id="43dd5-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="43dd5-108">Requirements</span></span>  

 <span data-ttu-id="43dd5-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="43dd5-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43dd5-110">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="43dd5-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="43dd5-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="43dd5-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="43dd5-112">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43dd5-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43dd5-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="43dd5-113">See also</span></span>

- [<span data-ttu-id="43dd5-114">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="43dd5-114">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
