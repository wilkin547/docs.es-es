---
description: 'Más información sobre: ICorProfilerCallback:: Exceptionoshandlerleave ((método)'
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
ms.openlocfilehash: 809f9440510bc0b55c9cae9827757eb61e61b257
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99657578"
---
# <a name="icorprofilercallbackexceptionoshandlerleave-method"></a><span data-ttu-id="52e10-103">ICorProfilerCallback::ExceptionOSHandlerLeave (Método)</span><span class="sxs-lookup"><span data-stu-id="52e10-103">ICorProfilerCallback::ExceptionOSHandlerLeave Method</span></span>

<span data-ttu-id="52e10-104">Sin implementar.</span><span class="sxs-lookup"><span data-stu-id="52e10-104">Not implemented.</span></span> <span data-ttu-id="52e10-105">Un generador de perfiles que necesita información de excepción no administrada debe obtener esta información a través de otros medios.</span><span class="sxs-lookup"><span data-stu-id="52e10-105">A profiler that needs unmanaged exception information must obtain this information through other means.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52e10-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="52e10-106">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionOSHandlerLeave(  
    [in] UINT_PTR __unused);  
```  
  
## <a name="requirements"></a><span data-ttu-id="52e10-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="52e10-107">Requirements</span></span>  

 <span data-ttu-id="52e10-108">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="52e10-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="52e10-109">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="52e10-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="52e10-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="52e10-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="52e10-111">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="52e10-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52e10-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="52e10-112">See also</span></span>

- [<span data-ttu-id="52e10-113">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="52e10-113">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
