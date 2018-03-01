---
title: "ICorProfilerCallback::ExceptionSearchFunctionLeave (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e63309ea1d92018b41c8ee32fcd66f865af5d891
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackexceptionsearchfunctionleave-method"></a><span data-ttu-id="0cf52-102">ICorProfilerCallback::ExceptionSearchFunctionLeave (Método)</span><span class="sxs-lookup"><span data-stu-id="0cf52-102">ICorProfilerCallback::ExceptionSearchFunctionLeave Method</span></span>
<span data-ttu-id="0cf52-103">Notifica al generador de perfiles que la fase de búsqueda del control de excepciones ha terminado de buscar una función.</span><span class="sxs-lookup"><span data-stu-id="0cf52-103">Notifies the profiler that the search phase of exception handling has finished searching a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0cf52-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0cf52-104">Syntax</span></span>  
  
```  
HRESULT ExceptionSearchFunctionLeave();  
```  
  
## <a name="requirements"></a><span data-ttu-id="0cf52-105">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0cf52-105">Requirements</span></span>  
 <span data-ttu-id="0cf52-106">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0cf52-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0cf52-107">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0cf52-107">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0cf52-108">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0cf52-108">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0cf52-109">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0cf52-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0cf52-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="0cf52-110">See Also</span></span>  
 [<span data-ttu-id="0cf52-111">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0cf52-111">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="0cf52-112">ExceptionSearchFunctionEnter (método)</span><span class="sxs-lookup"><span data-stu-id="0cf52-112">ExceptionSearchFunctionEnter Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionenter-method.md)
