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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: de2a831e310ac7f770200a70cb793bc19645e31d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33451603"
---
# <a name="icorprofilercallbackremotingserverinvocationstarted-method"></a><span data-ttu-id="337ff-102">ICorProfilerCallback::RemotingServerInvocationStarted (Método)</span><span class="sxs-lookup"><span data-stu-id="337ff-102">ICorProfilerCallback::RemotingServerInvocationStarted Method</span></span>
<span data-ttu-id="337ff-103">Notifica al generador de perfiles que el proceso está invocando un método en respuesta a una solicitud de invocación de método remoto.</span><span class="sxs-lookup"><span data-stu-id="337ff-103">Notifies the profiler that the process is invoking a method in response to a remote method invocation request.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="337ff-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="337ff-104">Syntax</span></span>  
  
```  
HRESULT RemotingServerInvocationStarted();  
```  
  
## <a name="requirements"></a><span data-ttu-id="337ff-105">Requisitos</span><span class="sxs-lookup"><span data-stu-id="337ff-105">Requirements</span></span>  
 <span data-ttu-id="337ff-106">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="337ff-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="337ff-107">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="337ff-107">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="337ff-108">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="337ff-108">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="337ff-109">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="337ff-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="337ff-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="337ff-110">See Also</span></span>  
 [<span data-ttu-id="337ff-111">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="337ff-111">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
