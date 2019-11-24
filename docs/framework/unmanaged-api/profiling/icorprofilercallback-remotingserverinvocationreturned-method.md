---
title: ICorProfilerCallback::RemotingServerInvocationReturned (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingServerInvocationReturned
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingServerInvocationReturned
helpviewer_keywords:
- ICorProfilerCallback::RemotingServerInvocationReturned method [.NET Framework profiling]
- RemotingServerInvocationReturned method [.NET Framework profiling]
ms.assetid: a4de6805-e159-4280-99e5-3390c86166d0
topic_type:
- apiref
ms.openlocfilehash: c121e403d116581ce3fa823d5d8cadbb2a58e296
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445785"
---
# <a name="icorprofilercallbackremotingserverinvocationreturned-method"></a><span data-ttu-id="b90e9-102">ICorProfilerCallback::RemotingServerInvocationReturned (Método)</span><span class="sxs-lookup"><span data-stu-id="b90e9-102">ICorProfilerCallback::RemotingServerInvocationReturned Method</span></span>
<span data-ttu-id="b90e9-103">Notifies the profiler that the process has finished invoking a method in response to a remote method invocation request.</span><span class="sxs-lookup"><span data-stu-id="b90e9-103">Notifies the profiler that the process has finished invoking a method in response to a remote method invocation request.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b90e9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b90e9-104">Syntax</span></span>  
  
```cpp  
HRESULT RemotingServerInvocationReturned();  
```  
  
## <a name="requirements"></a><span data-ttu-id="b90e9-105">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b90e9-105">Requirements</span></span>  
 <span data-ttu-id="b90e9-106">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b90e9-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b90e9-107">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b90e9-107">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b90e9-108">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b90e9-108">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b90e9-109">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b90e9-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b90e9-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="b90e9-110">See also</span></span>

- [<span data-ttu-id="b90e9-111">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b90e9-111">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
