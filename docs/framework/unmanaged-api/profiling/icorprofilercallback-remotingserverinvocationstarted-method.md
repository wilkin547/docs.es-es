---
title: ICorProfilerCallback::RemotingServerInvocationStarted (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingServerInvocationStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingServerInvocationStarted
helpviewer_keywords:
- RemotingServerInvocationStarted method [.NET Framework profiling]
- ICorProfilerCallback::RemotingServerInvocationStarted method [.NET Framework profiling]
ms.assetid: 86051a11-ad8e-4ace-9a11-ff0f982a5e11
topic_type:
- apiref
ms.openlocfilehash: 3725b73ab55f6e4dc789a1fde8d1224695a174d7
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499940"
---
# <a name="icorprofilercallbackremotingserverinvocationstarted-method"></a><span data-ttu-id="1e0b8-102">ICorProfilerCallback::RemotingServerInvocationStarted (Método)</span><span class="sxs-lookup"><span data-stu-id="1e0b8-102">ICorProfilerCallback::RemotingServerInvocationStarted Method</span></span>
<span data-ttu-id="1e0b8-103">Notifica al generador de perfiles que el proceso está invocando un método en respuesta a una solicitud de invocación de método remoto.</span><span class="sxs-lookup"><span data-stu-id="1e0b8-103">Notifies the profiler that the process is invoking a method in response to a remote method invocation request.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e0b8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1e0b8-104">Syntax</span></span>  
  
```cpp  
HRESULT RemotingServerInvocationStarted();  
```  
  
## <a name="requirements"></a><span data-ttu-id="1e0b8-105">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1e0b8-105">Requirements</span></span>  
 <span data-ttu-id="1e0b8-106">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1e0b8-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1e0b8-107">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1e0b8-107">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1e0b8-108">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1e0b8-108">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1e0b8-109">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1e0b8-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e0b8-110">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="1e0b8-110">See also</span></span>

- [<span data-ttu-id="1e0b8-111">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1e0b8-111">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
