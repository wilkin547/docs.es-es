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
ms.openlocfilehash: d9989ef8b1ae50202ba6900b95504a7d50e10dfc
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/20/2021
ms.locfileid: "104759487"
---
# <a name="icorprofilercallbackexceptionsearchfunctionenter-method"></a><span data-ttu-id="3b792-103">ICorProfilerCallback::ExceptionSearchFunctionEnter (Método)</span><span class="sxs-lookup"><span data-stu-id="3b792-103">ICorProfilerCallback::ExceptionSearchFunctionEnter Method</span></span>

<span data-ttu-id="3b792-104">Notifica al generador de perfiles que la fase de búsqueda del control de excepciones ha empezado a buscar una función para encontrar un controlador para la excepción actual.</span><span class="sxs-lookup"><span data-stu-id="3b792-104">Notifies the profiler that the search phase of exception handling has begun searching a function to find a handler for the current exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b792-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3b792-105">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionSearchFunctionEnter(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3b792-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3b792-106">Parameters</span></span>

<span data-ttu-id="3b792-107">`functionId` de IDENTIFICADOR de la función que se ha especificado.</span><span class="sxs-lookup"><span data-stu-id="3b792-107">`functionId` [in] The ID of the function that has been entered.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="3b792-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3b792-108">Requirements</span></span>  

 <span data-ttu-id="3b792-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3b792-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3b792-110">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3b792-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3b792-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3b792-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3b792-112">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3b792-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b792-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3b792-113">See also</span></span>

- [<span data-ttu-id="3b792-114">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3b792-114">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="3b792-115">Método ExceptionSearchFunctionLeave</span><span class="sxs-lookup"><span data-stu-id="3b792-115">ExceptionSearchFunctionLeave Method</span></span>](icorprofilercallback-exceptionsearchfunctionleave-method.md)
