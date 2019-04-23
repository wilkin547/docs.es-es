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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e41378b314b91f42fca9d1039d3011b5eaafe502
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59074305"
---
# <a name="icorprofilercallbackexceptionsearchcatcherfound-method"></a><span data-ttu-id="24fdd-102">ICorProfilerCallback::ExceptionSearchCatcherFound (Método)</span><span class="sxs-lookup"><span data-stu-id="24fdd-102">ICorProfilerCallback::ExceptionSearchCatcherFound Method</span></span>
<span data-ttu-id="24fdd-103">Notifica al generador de perfiles que la fase de búsqueda del control de excepciones encuentra un controlador para la excepción que se produjo.</span><span class="sxs-lookup"><span data-stu-id="24fdd-103">Notifies the profiler that the search phase of exception handling has located a handler for the exception that was thrown.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24fdd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="24fdd-104">Syntax</span></span>  
  
```  
RESULT ExceptionSearchCatcherFound(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="24fdd-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="24fdd-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="24fdd-106">[in] El identificador de la función que contiene el controlador de excepciones.</span><span class="sxs-lookup"><span data-stu-id="24fdd-106">[in] The ID of the function that contains the exception handler.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="24fdd-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="24fdd-107">Requirements</span></span>  
 <span data-ttu-id="24fdd-108">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="24fdd-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="24fdd-109">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="24fdd-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="24fdd-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="24fdd-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="24fdd-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="24fdd-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24fdd-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="24fdd-112">See also</span></span>

- [<span data-ttu-id="24fdd-113">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="24fdd-113">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
