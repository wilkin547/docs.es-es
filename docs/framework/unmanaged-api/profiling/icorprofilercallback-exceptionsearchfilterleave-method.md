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
ms.openlocfilehash: 70573164baf6839b5ae701c645526e8b1507ad35
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445358"
---
# <a name="icorprofilercallbackexceptionsearchfilterleave-method"></a><span data-ttu-id="1e3ab-102">ICorProfilerCallback::ExceptionSearchFilterLeave (Método)</span><span class="sxs-lookup"><span data-stu-id="1e3ab-102">ICorProfilerCallback::ExceptionSearchFilterLeave Method</span></span>
<span data-ttu-id="1e3ab-103">Notifica al generador de perfiles que un filtro de usuario ha terminado de ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="1e3ab-103">Notifies the profiler that a user filter has just finished executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e3ab-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1e3ab-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionSearchFilterLeave();  
```  
  
## <a name="requirements"></a><span data-ttu-id="1e3ab-105">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1e3ab-105">Requirements</span></span>  
 <span data-ttu-id="1e3ab-106">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1e3ab-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1e3ab-107">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1e3ab-107">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1e3ab-108">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1e3ab-108">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1e3ab-109">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1e3ab-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e3ab-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="1e3ab-110">See also</span></span>

- [<span data-ttu-id="1e3ab-111">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1e3ab-111">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="1e3ab-112">ExceptionSearchFilterEnter (método)</span><span class="sxs-lookup"><span data-stu-id="1e3ab-112">ExceptionSearchFilterEnter Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterenter-method.md)
