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
ms.openlocfilehash: d58f2013e93eb1c7030d26ec60b0ab5ab08d0524
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699864"
---
# <a name="icorprofilercallbackexceptionsearchfilterenter-method"></a><span data-ttu-id="526a4-102">ICorProfilerCallback::ExceptionSearchFilterEnter (Método)</span><span class="sxs-lookup"><span data-stu-id="526a4-102">ICorProfilerCallback::ExceptionSearchFilterEnter Method</span></span>

<span data-ttu-id="526a4-103">Notifica al generador de perfiles que la fase de búsqueda del control de excepciones ha empezado a ejecutar un filtro de excepción definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="526a4-103">Notifies the profiler that the search phase of exception handling has begun executing a user-defined exception filter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="526a4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="526a4-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionSearchFilterEnter(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="526a4-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="526a4-105">Parameters</span></span>

- `functionId`

  <span data-ttu-id="526a4-106">\[in] identificador de la función que contiene el filtro.</span><span class="sxs-lookup"><span data-stu-id="526a4-106">\[in] The ID of the function that contains the filter.</span></span>

## <a name="requirements"></a><span data-ttu-id="526a4-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="526a4-107">Requirements</span></span>  

 <span data-ttu-id="526a4-108">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="526a4-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="526a4-109">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="526a4-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="526a4-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="526a4-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="526a4-111">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="526a4-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="526a4-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="526a4-112">See also</span></span>

- [<span data-ttu-id="526a4-113">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="526a4-113">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="526a4-114">Método ExceptionSearchFilterLeave</span><span class="sxs-lookup"><span data-stu-id="526a4-114">ExceptionSearchFilterLeave Method</span></span>](icorprofilercallback-exceptionsearchfilterleave-method.md)
