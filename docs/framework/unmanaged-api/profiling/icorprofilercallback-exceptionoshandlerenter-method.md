---
description: 'Más información sobre: ICorProfilerCallback:: Exceptionoshandlerenter ((método)'
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
ms.openlocfilehash: 88dfd062451c63265716e7cf4c04292aa15f91ed
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99657624"
---
# <a name="icorprofilercallbackexceptionoshandlerenter-method"></a><span data-ttu-id="44abe-103">ICorProfilerCallback::ExceptionOSHandlerEnter (Método)</span><span class="sxs-lookup"><span data-stu-id="44abe-103">ICorProfilerCallback::ExceptionOSHandlerEnter Method</span></span>

<span data-ttu-id="44abe-104">Sin implementar.</span><span class="sxs-lookup"><span data-stu-id="44abe-104">Not implemented.</span></span> <span data-ttu-id="44abe-105">Un generador de perfiles que necesita información de excepción no administrada debe obtener esta información a través de otros medios.</span><span class="sxs-lookup"><span data-stu-id="44abe-105">A profiler that needs unmanaged exception information must obtain this information through other means.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44abe-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="44abe-106">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionOSHandlerEnter(  
    [in] UINT_PTR __unused);  
```  
  
## <a name="requirements"></a><span data-ttu-id="44abe-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="44abe-107">Requirements</span></span>  

 <span data-ttu-id="44abe-108">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="44abe-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="44abe-109">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="44abe-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="44abe-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="44abe-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="44abe-111">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44abe-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44abe-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="44abe-112">See also</span></span>

- [<span data-ttu-id="44abe-113">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="44abe-113">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
