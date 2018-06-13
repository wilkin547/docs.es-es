---
title: ICorProfilerCallback::ExceptionOSHandlerEnter (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionOSHandlerEnter
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionOSHandlerEnter
helpviewer_keywords:
- ExceptionOSHandlerEnter method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionOSHandlerEnter method [.NET Framework profiling]
ms.assetid: 09238b9b-9359-4780-89dc-2f5e4f57920e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f2dc7c22ee075f347604864d8bee1a4e871da616
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33451771"
---
# <a name="icorprofilercallbackexceptionoshandlerenter-method"></a><span data-ttu-id="55089-102">ICorProfilerCallback::ExceptionOSHandlerEnter (Método)</span><span class="sxs-lookup"><span data-stu-id="55089-102">ICorProfilerCallback::ExceptionOSHandlerEnter Method</span></span>
<span data-ttu-id="55089-103">Sin implementar.</span><span class="sxs-lookup"><span data-stu-id="55089-103">Not implemented.</span></span> <span data-ttu-id="55089-104">Un generador de perfiles que necesita información de excepción no administrada debe obtener esta información a través de otros medios.</span><span class="sxs-lookup"><span data-stu-id="55089-104">A profiler that needs unmanaged exception information must obtain this information through other means.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55089-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="55089-105">Syntax</span></span>  
  
```  
HRESULT ExceptionOSHandlerEnter(  
    [in] UINT_PTR __unused);  
```  
  
## <a name="requirements"></a><span data-ttu-id="55089-106">Requisitos</span><span class="sxs-lookup"><span data-stu-id="55089-106">Requirements</span></span>  
 <span data-ttu-id="55089-107">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="55089-107">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="55089-108">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="55089-108">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="55089-109">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="55089-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="55089-110">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="55089-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55089-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="55089-111">See Also</span></span>  
 [<span data-ttu-id="55089-112">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="55089-112">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
