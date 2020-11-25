---
title: ICorProfilerCallback::ExceptionSearchFunctionLeave (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionSearchFunctionLeave
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionSearchFunctionLeave
helpviewer_keywords:
- ExceptionSearchFunctionLeave method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionSearchFunctionLeave method [.NET Framework profiling]
ms.assetid: 01de7ac6-0aad-42ef-bf93-50737667b0a4
topic_type:
- apiref
ms.openlocfilehash: 064f87fe0cee8d0ad7efcba478e9cf1954a3f291
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699773"
---
# <a name="icorprofilercallbackexceptionsearchfunctionleave-method"></a><span data-ttu-id="edcae-102">ICorProfilerCallback::ExceptionSearchFunctionLeave (Método)</span><span class="sxs-lookup"><span data-stu-id="edcae-102">ICorProfilerCallback::ExceptionSearchFunctionLeave Method</span></span>

<span data-ttu-id="edcae-103">Notifica al generador de perfiles que la fase de búsqueda del control de excepciones ha terminado de buscar una función.</span><span class="sxs-lookup"><span data-stu-id="edcae-103">Notifies the profiler that the search phase of exception handling has finished searching a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="edcae-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="edcae-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionSearchFunctionLeave();  
```  
  
## <a name="requirements"></a><span data-ttu-id="edcae-105">Requisitos</span><span class="sxs-lookup"><span data-stu-id="edcae-105">Requirements</span></span>  

 <span data-ttu-id="edcae-106">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="edcae-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="edcae-107">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="edcae-107">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="edcae-108">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="edcae-108">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="edcae-109">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="edcae-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="edcae-110">Consulte también</span><span class="sxs-lookup"><span data-stu-id="edcae-110">See also</span></span>

- [<span data-ttu-id="edcae-111">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="edcae-111">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="edcae-112">Método ExceptionSearchFunctionEnter</span><span class="sxs-lookup"><span data-stu-id="edcae-112">ExceptionSearchFunctionEnter Method</span></span>](icorprofilercallback-exceptionsearchfunctionenter-method.md)
