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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 81f96216c61b59c6554e2dcd64a79a25ed87bf95
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33451862"
---
# <a name="icorprofilercallbackexceptionsearchfunctionleave-method"></a><span data-ttu-id="b11d0-102">ICorProfilerCallback::ExceptionSearchFunctionLeave (Método)</span><span class="sxs-lookup"><span data-stu-id="b11d0-102">ICorProfilerCallback::ExceptionSearchFunctionLeave Method</span></span>
<span data-ttu-id="b11d0-103">Notifica al generador de perfiles que la fase de búsqueda del control de excepciones ha terminado de buscar una función.</span><span class="sxs-lookup"><span data-stu-id="b11d0-103">Notifies the profiler that the search phase of exception handling has finished searching a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b11d0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b11d0-104">Syntax</span></span>  
  
```  
HRESULT ExceptionSearchFunctionLeave();  
```  
  
## <a name="requirements"></a><span data-ttu-id="b11d0-105">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b11d0-105">Requirements</span></span>  
 <span data-ttu-id="b11d0-106">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b11d0-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b11d0-107">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b11d0-107">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b11d0-108">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b11d0-108">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b11d0-109">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b11d0-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b11d0-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="b11d0-110">See Also</span></span>  
 [<span data-ttu-id="b11d0-111">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b11d0-111">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="b11d0-112">ExceptionSearchFunctionEnter (método)</span><span class="sxs-lookup"><span data-stu-id="b11d0-112">ExceptionSearchFunctionEnter Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionenter-method.md)
