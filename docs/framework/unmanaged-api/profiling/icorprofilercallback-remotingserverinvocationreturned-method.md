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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 00f5fd44d340a76200537871a9860f67601b66d9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59208714"
---
# <a name="icorprofilercallbackremotingserverinvocationreturned-method"></a><span data-ttu-id="f7cbe-102">ICorProfilerCallback::RemotingServerInvocationReturned (Método)</span><span class="sxs-lookup"><span data-stu-id="f7cbe-102">ICorProfilerCallback::RemotingServerInvocationReturned Method</span></span>
<span data-ttu-id="f7cbe-103">Notifica al generador de perfiles que ha finalizado el proceso para invocar un método en respuesta a una solicitud de invocación de método remoto.</span><span class="sxs-lookup"><span data-stu-id="f7cbe-103">Notifies the profiler that the process has finished invoking a method in response to a remote method invocation request.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7cbe-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f7cbe-104">Syntax</span></span>  
  
```  
HRESULT RemotingServerInvocationReturned();  
```  
  
## <a name="requirements"></a><span data-ttu-id="f7cbe-105">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f7cbe-105">Requirements</span></span>  
 <span data-ttu-id="f7cbe-106">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f7cbe-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f7cbe-107">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f7cbe-107">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f7cbe-108">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f7cbe-108">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="f7cbe-109">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="f7cbe-109">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f7cbe-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="f7cbe-110">See also</span></span>

- [<span data-ttu-id="f7cbe-111">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f7cbe-111">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
