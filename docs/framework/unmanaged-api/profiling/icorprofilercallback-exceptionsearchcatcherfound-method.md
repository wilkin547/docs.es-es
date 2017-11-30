---
title: "ICorProfilerCallback::ExceptionSearchCatcherFound (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ExceptionSearchCatcherFound
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ExceptionSearchCatcherFound
helpviewer_keywords:
- ExceptionSearchCatcherFound method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionSearchCatcherFound method [.NET Framework profiling]
ms.assetid: 190f424d-5e37-4163-a191-0895686e9476
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 434af3fb6201aefac40795ffed7781a72a97b729
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilercallbackexceptionsearchcatcherfound-method"></a><span data-ttu-id="e8254-102">ICorProfilerCallback::ExceptionSearchCatcherFound (Método)</span><span class="sxs-lookup"><span data-stu-id="e8254-102">ICorProfilerCallback::ExceptionSearchCatcherFound Method</span></span>
<span data-ttu-id="e8254-103">Notifica al generador de perfiles que la fase de búsqueda del control de excepciones encuentra un controlador para la excepción que se produjo.</span><span class="sxs-lookup"><span data-stu-id="e8254-103">Notifies the profiler that the search phase of exception handling has located a handler for the exception that was thrown.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8254-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e8254-104">Syntax</span></span>  
  
```  
RESULT ExceptionSearchCatcherFound(  
    [in] FunctionID functionId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e8254-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e8254-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="e8254-106">[in] El identificador de la función que contiene el controlador de excepciones.</span><span class="sxs-lookup"><span data-stu-id="e8254-106">[in] The ID of the function that contains the exception handler.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e8254-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e8254-107">Requirements</span></span>  
 <span data-ttu-id="e8254-108">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e8254-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e8254-109">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e8254-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e8254-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e8254-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e8254-111">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e8254-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8254-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="e8254-112">See Also</span></span>  
 [<span data-ttu-id="e8254-113">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e8254-113">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
