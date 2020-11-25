---
title: ICorProfilerCallback::RemotingClientInvocationStarted (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingClientInvocationStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingClientInvocationStarted
helpviewer_keywords:
- RemotingClientInvocationStarted method [.NET Framework profiling]
- ICorProfilerCallback::RemotingClientInvocationStarted method [.NET Framework profiling]
ms.assetid: 796b63f3-c809-47f1-89cc-b23ad8eb5e79
topic_type:
- apiref
ms.openlocfilehash: 22b9970556dd9d8b5070f38a7712462aa5a4aae2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720170"
---
# <a name="icorprofilercallbackremotingclientinvocationstarted-method"></a><span data-ttu-id="8372a-102">ICorProfilerCallback::RemotingClientInvocationStarted (Método)</span><span class="sxs-lookup"><span data-stu-id="8372a-102">ICorProfilerCallback::RemotingClientInvocationStarted Method</span></span>

<span data-ttu-id="8372a-103">Notifica al generador de perfiles que se ha iniciado una llamada de comunicación remota.</span><span class="sxs-lookup"><span data-stu-id="8372a-103">Notifies the profiler that a remoting call has started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8372a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8372a-104">Syntax</span></span>  
  
```cpp  
HRESULT RemotingClientInvocationStarted();  
```  
  
## <a name="remarks"></a><span data-ttu-id="8372a-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8372a-105">Remarks</span></span>  

 <span data-ttu-id="8372a-106">Este evento es el mismo para las llamadas sincrónicas y asincrónicas.</span><span class="sxs-lookup"><span data-stu-id="8372a-106">This event is the same for synchronous and asynchronous calls.</span></span>  
  
 <span data-ttu-id="8372a-107">Cada uno de los siguientes pares de devoluciones de llamada se producirá en el mismo subproceso:</span><span class="sxs-lookup"><span data-stu-id="8372a-107">Each of the following pairs of callbacks will occur on the same thread:</span></span>  
  
- <span data-ttu-id="8372a-108">`RemotingClientInvocationStarted` y [ICorProfilerCallback:: remotingclientsendingmessage (](icorprofilercallback-remotingclientsendingmessage-method.md)</span><span class="sxs-lookup"><span data-stu-id="8372a-108">`RemotingClientInvocationStarted` and [ICorProfilerCallback::RemotingClientSendingMessage](icorprofilercallback-remotingclientsendingmessage-method.md)</span></span>  
  
- <span data-ttu-id="8372a-109">[ICorProfilerCallback:: remotingclientreceivingreply (](icorprofilercallback-remotingclientreceivingreply-method.md) e [ICorProfilerCallback:: remotingclientinvocationfinished (](icorprofilercallback-remotingclientinvocationfinished-method.md)</span><span class="sxs-lookup"><span data-stu-id="8372a-109">[ICorProfilerCallback::RemotingClientReceivingReply](icorprofilercallback-remotingclientreceivingreply-method.md) and [ICorProfilerCallback::RemotingClientInvocationFinished](icorprofilercallback-remotingclientinvocationfinished-method.md)</span></span>  
  
- <span data-ttu-id="8372a-110">[ICorProfilerCallback:: RemotingServerInvocationReturned (](icorprofilercallback-remotingserverinvocationreturned-method.md) e [ICorProfilerCallback:: RemotingServerSendingReply (](icorprofilercallback-remotingserversendingreply-method.md)</span><span class="sxs-lookup"><span data-stu-id="8372a-110">[ICorProfilerCallback::RemotingServerInvocationReturned](icorprofilercallback-remotingserverinvocationreturned-method.md) and [ICorProfilerCallback::RemotingServerSendingReply](icorprofilercallback-remotingserversendingreply-method.md)</span></span>  
  
 <span data-ttu-id="8372a-111">Debe tener en cuenta los siguientes problemas con las devoluciones de llamada de comunicación remota:</span><span class="sxs-lookup"><span data-stu-id="8372a-111">You should be aware of the following issues with the remoting callbacks:</span></span>  
  
- <span data-ttu-id="8372a-112">La ejecución de una función de comunicación remota no se refleja en la API del generador de perfiles, por lo que las notificaciones para las funciones a las que se llama desde el cliente y que se ejecutan en el servidor no se reciben correctamente.</span><span class="sxs-lookup"><span data-stu-id="8372a-112">Execution of a remoting function is not reflected by the profiler API, so notifications for functions that are called from the client and executed on the server are not properly received.</span></span> <span data-ttu-id="8372a-113">La invocación real se produce a través de un objeto proxy. en el generador de perfiles, parece que ciertas funciones se compilan JIT pero nunca se usan.</span><span class="sxs-lookup"><span data-stu-id="8372a-113">The actual invocation happens via a proxy object; to the profiler, it appears that certain functions are JIT-compiled but never used.</span></span>  
  
- <span data-ttu-id="8372a-114">El generador de perfiles no recibe notificaciones precisas para eventos de comunicación remota asincrónica.</span><span class="sxs-lookup"><span data-stu-id="8372a-114">The profiler does not receive accurate notifications for asynchronous remoting events.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8372a-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8372a-115">Requirements</span></span>  

 <span data-ttu-id="8372a-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8372a-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8372a-117">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8372a-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8372a-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8372a-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8372a-119">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8372a-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8372a-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8372a-120">See also</span></span>

- [<span data-ttu-id="8372a-121">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8372a-121">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
