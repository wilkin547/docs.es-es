---
title: ICorProfilerCallback::ExceptionOSHandlerLeave (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionOSHandlerLeave
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionOSHandlerLeave
helpviewer_keywords:
- ExceptionOSHandlerLeave method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionOSHandlerLeave method [.NET Framework profiling]
ms.assetid: 4d164676-0ee9-4f67-a8ea-cb474db09053
topic_type:
- apiref
ms.openlocfilehash: dcb2af2507306b22da14c13a42e4019261c8fa8c
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866447"
---
# <a name="icorprofilercallbackexceptionoshandlerleave-method"></a><span data-ttu-id="3d9b9-102">ICorProfilerCallback::ExceptionOSHandlerLeave (Método)</span><span class="sxs-lookup"><span data-stu-id="3d9b9-102">ICorProfilerCallback::ExceptionOSHandlerLeave Method</span></span>
<span data-ttu-id="3d9b9-103">Sin implementar.</span><span class="sxs-lookup"><span data-stu-id="3d9b9-103">Not implemented.</span></span> <span data-ttu-id="3d9b9-104">Un generador de perfiles que necesita información de excepción no administrada debe obtener esta información a través de otros medios.</span><span class="sxs-lookup"><span data-stu-id="3d9b9-104">A profiler that needs unmanaged exception information must obtain this information through other means.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d9b9-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3d9b9-105">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionOSHandlerLeave(  
    [in] UINT_PTR __unused);  
```  
  
## <a name="requirements"></a><span data-ttu-id="3d9b9-106">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="3d9b9-106">Requirements</span></span>  
 <span data-ttu-id="3d9b9-107">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3d9b9-107">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3d9b9-108">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3d9b9-108">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3d9b9-109">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3d9b9-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3d9b9-110">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3d9b9-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d9b9-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="3d9b9-111">See also</span></span>

- [<span data-ttu-id="3d9b9-112">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3d9b9-112">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
