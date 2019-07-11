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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 468c5b28bb5a574aacf623196f0c516992473707
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67756226"
---
# <a name="icorprofilercallbackexceptionoshandlerleave-method"></a><span data-ttu-id="fbce5-102">ICorProfilerCallback::ExceptionOSHandlerLeave (Método)</span><span class="sxs-lookup"><span data-stu-id="fbce5-102">ICorProfilerCallback::ExceptionOSHandlerLeave Method</span></span>
<span data-ttu-id="fbce5-103">Sin implementar.</span><span class="sxs-lookup"><span data-stu-id="fbce5-103">Not implemented.</span></span> <span data-ttu-id="fbce5-104">Un generador de perfiles que necesita información de excepción no administrada debe obtener esta información a través de otros medios.</span><span class="sxs-lookup"><span data-stu-id="fbce5-104">A profiler that needs unmanaged exception information must obtain this information through other means.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fbce5-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fbce5-105">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionOSHandlerLeave(  
    [in] UINT_PTR __unused);  
```  
  
## <a name="requirements"></a><span data-ttu-id="fbce5-106">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fbce5-106">Requirements</span></span>  
 <span data-ttu-id="fbce5-107">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fbce5-107">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fbce5-108">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="fbce5-108">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="fbce5-109">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fbce5-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fbce5-110">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fbce5-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbce5-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="fbce5-111">See also</span></span>

- [<span data-ttu-id="fbce5-112">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="fbce5-112">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
