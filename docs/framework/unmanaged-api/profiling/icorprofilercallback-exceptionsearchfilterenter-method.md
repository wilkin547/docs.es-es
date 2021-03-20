---
description: 'Más información sobre: ICorProfilerCallback:: Exceptionsearchfilterenter ((método)'
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
ms.openlocfilehash: 29a9eed75e5d8a954dfb23dedf3d2080e0d139d2
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/20/2021
ms.locfileid: "104760226"
---
# <a name="icorprofilercallbackexceptionsearchfilterenter-method"></a><span data-ttu-id="a8ae4-103">ICorProfilerCallback::ExceptionSearchFilterEnter (Método)</span><span class="sxs-lookup"><span data-stu-id="a8ae4-103">ICorProfilerCallback::ExceptionSearchFilterEnter Method</span></span>

<span data-ttu-id="a8ae4-104">Notifica al generador de perfiles que la fase de búsqueda del control de excepciones ha empezado a ejecutar un filtro de excepción definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="a8ae4-104">Notifies the profiler that the search phase of exception handling has begun executing a user-defined exception filter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8ae4-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a8ae4-105">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionSearchFilterEnter(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a8ae4-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a8ae4-106">Parameters</span></span>

<span data-ttu-id="a8ae4-107">`functionId` de IDENTIFICADOR de la función que contiene el filtro.</span><span class="sxs-lookup"><span data-stu-id="a8ae4-107">`functionId` [in] The ID of the function that contains the filter.</span></span>

## <a name="requirements"></a><span data-ttu-id="a8ae4-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a8ae4-108">Requirements</span></span>  

 <span data-ttu-id="a8ae4-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a8ae4-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a8ae4-110">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a8ae4-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a8ae4-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a8ae4-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a8ae4-112">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a8ae4-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8ae4-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a8ae4-113">See also</span></span>

- [<span data-ttu-id="a8ae4-114">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a8ae4-114">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="a8ae4-115">Método ExceptionSearchFilterLeave</span><span class="sxs-lookup"><span data-stu-id="a8ae4-115">ExceptionSearchFilterLeave Method</span></span>](icorprofilercallback-exceptionsearchfilterleave-method.md)
