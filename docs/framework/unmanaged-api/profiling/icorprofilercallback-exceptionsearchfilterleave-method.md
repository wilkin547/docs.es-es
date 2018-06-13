---
title: ICorProfilerCallback::ExceptionSearchFilterLeave (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionSearchFilterLeave
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionSearchFilterLeave
helpviewer_keywords:
- ICorProfilerCallback::ExceptionSearchFilterLeave method [.NET Framework profiling]
- ExceptionSearchFilterLeave method [.NET Framework profiling]
ms.assetid: c28a2a82-dd11-4385-843f-b509fb61753b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 13de3470e70635243aed78ac603cebc841c8fa59
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33451303"
---
# <a name="icorprofilercallbackexceptionsearchfilterleave-method"></a><span data-ttu-id="90352-102">ICorProfilerCallback::ExceptionSearchFilterLeave (Método)</span><span class="sxs-lookup"><span data-stu-id="90352-102">ICorProfilerCallback::ExceptionSearchFilterLeave Method</span></span>
<span data-ttu-id="90352-103">Notifica al generador de perfiles que un filtro de usuario solo ha terminado de ejecutar.</span><span class="sxs-lookup"><span data-stu-id="90352-103">Notifies the profiler that a user filter has just finished executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90352-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="90352-104">Syntax</span></span>  
  
```  
HRESULT ExceptionSearchFilterLeave();  
```  
  
## <a name="requirements"></a><span data-ttu-id="90352-105">Requisitos</span><span class="sxs-lookup"><span data-stu-id="90352-105">Requirements</span></span>  
 <span data-ttu-id="90352-106">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="90352-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="90352-107">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="90352-107">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="90352-108">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="90352-108">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="90352-109">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="90352-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90352-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="90352-110">See Also</span></span>  
 [<span data-ttu-id="90352-111">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="90352-111">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="90352-112">ExceptionSearchFilterEnter (método)</span><span class="sxs-lookup"><span data-stu-id="90352-112">ExceptionSearchFilterEnter Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterenter-method.md)
