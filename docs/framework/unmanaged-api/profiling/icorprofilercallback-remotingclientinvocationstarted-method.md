---
title: "ICorProfilerCallback::RemotingClientInvocationStarted (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.RemotingClientInvocationStarted
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::RemotingClientInvocationStarted
helpviewer_keywords:
- RemotingClientInvocationStarted method [.NET Framework profiling]
- ICorProfilerCallback::RemotingClientInvocationStarted method [.NET Framework profiling]
ms.assetid: 796b63f3-c809-47f1-89cc-b23ad8eb5e79
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ae91a35af0e4a0895fa58783521de1d3b95179a4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilercallbackremotingclientinvocationstarted-method"></a><span data-ttu-id="9d457-102">ICorProfilerCallback::RemotingClientInvocationStarted (Método)</span><span class="sxs-lookup"><span data-stu-id="9d457-102">ICorProfilerCallback::RemotingClientInvocationStarted Method</span></span>
<span data-ttu-id="9d457-103">Notifica al generador de perfiles que se ha iniciado una llamada remota.</span><span class="sxs-lookup"><span data-stu-id="9d457-103">Notifies the profiler that a remoting call has started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d457-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9d457-104">Syntax</span></span>  
  
```  
HRESULT RemotingClientInvocationStarted();  
```  
  
## <a name="remarks"></a><span data-ttu-id="9d457-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9d457-105">Remarks</span></span>  
 <span data-ttu-id="9d457-106">Este evento es el mismo para las llamadas sincrónicas y asincrónicas.</span><span class="sxs-lookup"><span data-stu-id="9d457-106">This event is the same for synchronous and asynchronous calls.</span></span>  
  
 <span data-ttu-id="9d457-107">Cada uno de los siguientes pares de devoluciones de llamada se producirá en el mismo subproceso:</span><span class="sxs-lookup"><span data-stu-id="9d457-107">Each of the following pairs of callbacks will occur on the same thread:</span></span>  
  
-   <span data-ttu-id="9d457-108">`RemotingClientInvocationStarted`y [ICorProfilerCallback:: RemotingClientSendingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md)</span><span class="sxs-lookup"><span data-stu-id="9d457-108">`RemotingClientInvocationStarted` and [ICorProfilerCallback::RemotingClientSendingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md)</span></span>  
  
-   <span data-ttu-id="9d457-109">[ICorProfilerCallback:: RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) y [ICorProfilerCallback:: RemotingClientInvocationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientinvocationfinished-method.md)</span><span class="sxs-lookup"><span data-stu-id="9d457-109">[ICorProfilerCallback::RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) and [ICorProfilerCallback::RemotingClientInvocationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientinvocationfinished-method.md)</span></span>  
  
-   <span data-ttu-id="9d457-110">[ICorProfilerCallback:: RemotingServerInvocationReturned](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverinvocationreturned-method.md) y [ICorProfilerCallback:: RemotingServerSendingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md)</span><span class="sxs-lookup"><span data-stu-id="9d457-110">[ICorProfilerCallback::RemotingServerInvocationReturned](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverinvocationreturned-method.md) and [ICorProfilerCallback::RemotingServerSendingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md)</span></span>  
  
 <span data-ttu-id="9d457-111">Debe tener en cuenta los siguientes problemas con las devoluciones de llamada de comunicación remota:</span><span class="sxs-lookup"><span data-stu-id="9d457-111">You should be aware of the following issues with the remoting callbacks:</span></span>  
  
-   <span data-ttu-id="9d457-112">Ejecución de una función de comunicación remota no se refleja en el generador de perfiles API, por lo que no se reciben correctamente las notificaciones para las funciones que se llama desde el cliente y se ejecutan en el servidor.</span><span class="sxs-lookup"><span data-stu-id="9d457-112">Execution of a remoting function is not reflected by the profiler API, so notifications for functions that are called from the client and executed on the server are not properly received.</span></span> <span data-ttu-id="9d457-113">La invocación real se produce a través de un objeto de proxy; en el generador de perfiles, parece que ciertas funciones están compiladas JIT pero nunca se utiliza.</span><span class="sxs-lookup"><span data-stu-id="9d457-113">The actual invocation happens via a proxy object; to the profiler, it appears that certain functions are JIT-compiled but never used.</span></span>  
  
-   <span data-ttu-id="9d457-114">El generador de perfiles no recibe notificaciones precisas para los eventos de interacción remota asincrónica.</span><span class="sxs-lookup"><span data-stu-id="9d457-114">The profiler does not receive accurate notifications for asynchronous remoting events.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9d457-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9d457-115">Requirements</span></span>  
 <span data-ttu-id="9d457-116">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9d457-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9d457-117">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9d457-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9d457-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9d457-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9d457-119">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9d457-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d457-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="9d457-120">See Also</span></span>  
 [<span data-ttu-id="9d457-121">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9d457-121">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
