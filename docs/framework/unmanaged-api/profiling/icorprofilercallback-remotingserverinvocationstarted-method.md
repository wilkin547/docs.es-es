---
description: 'Más información sobre: ICorProfilerCallback:: Remotingserverinvocationstarted ((método)'
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
ms.openlocfilehash: 8a27e3e545b9ff2812561f5faa7ebfe70d41f015
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99788909"
---
# <a name="icorprofilercallbackremotingserverinvocationstarted-method"></a><span data-ttu-id="f198d-103">ICorProfilerCallback::RemotingServerInvocationStarted (Método)</span><span class="sxs-lookup"><span data-stu-id="f198d-103">ICorProfilerCallback::RemotingServerInvocationStarted Method</span></span>

<span data-ttu-id="f198d-104">Notifica al generador de perfiles que el proceso está invocando un método en respuesta a una solicitud de invocación de método remoto.</span><span class="sxs-lookup"><span data-stu-id="f198d-104">Notifies the profiler that the process is invoking a method in response to a remote method invocation request.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f198d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f198d-105">Syntax</span></span>  
  
```cpp  
HRESULT RemotingServerInvocationStarted();  
```  
  
## <a name="requirements"></a><span data-ttu-id="f198d-106">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f198d-106">Requirements</span></span>  

 <span data-ttu-id="f198d-107">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f198d-107">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f198d-108">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f198d-108">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f198d-109">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f198d-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f198d-110">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f198d-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f198d-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="f198d-111">See also</span></span>

- [<span data-ttu-id="f198d-112">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f198d-112">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
