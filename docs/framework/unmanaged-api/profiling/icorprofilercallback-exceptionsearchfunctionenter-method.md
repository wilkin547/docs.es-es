---
title: "ICorProfilerCallback::ExceptionSearchFunctionEnter (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ExceptionSearchFunctionEnter
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ExceptionSearchFunctionEnter
helpviewer_keywords:
- ExceptionSearchFunctionEnter method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionSearchFunctionEnter method [.NET Framework profiling]
ms.assetid: bfd54573-b7e6-4bd1-a184-7f08a8b39fae
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d410d6ef47dfb0ad33c2a6a03f80d05810182a3b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackexceptionsearchfunctionenter-method"></a><span data-ttu-id="b9753-102">ICorProfilerCallback::ExceptionSearchFunctionEnter (Método)</span><span class="sxs-lookup"><span data-stu-id="b9753-102">ICorProfilerCallback::ExceptionSearchFunctionEnter Method</span></span>
<span data-ttu-id="b9753-103">Notifica al generador de perfiles que la fase de búsqueda del control de excepciones ha empezado a buscar una función para buscar un controlador para la excepción actual.</span><span class="sxs-lookup"><span data-stu-id="b9753-103">Notifies the profiler that the search phase of exception handling has begun searching a function to find a handler for the current exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9753-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b9753-104">Syntax</span></span>  
  
```  
HRESULT ExceptionSearchFunctionEnter(  
    [in] FunctionID functionId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b9753-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b9753-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="b9753-106">[in] El identificador de la función que se ha especificado.</span><span class="sxs-lookup"><span data-stu-id="b9753-106">[in] The ID of the function that has been entered.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9753-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b9753-107">Requirements</span></span>  
 <span data-ttu-id="b9753-108">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b9753-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9753-109">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b9753-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b9753-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b9753-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b9753-111">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9753-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9753-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="b9753-112">See Also</span></span>  
 [<span data-ttu-id="b9753-113">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b9753-113">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="b9753-114">ExceptionSearchFunctionLeave (método)</span><span class="sxs-lookup"><span data-stu-id="b9753-114">ExceptionSearchFunctionLeave Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionleave-method.md)
