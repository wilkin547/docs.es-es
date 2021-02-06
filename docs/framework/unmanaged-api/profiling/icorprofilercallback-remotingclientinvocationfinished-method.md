---
description: 'Más información sobre: ICorProfilerCallback:: Remotingclientinvocationfinished ((método)'
title: ICorProfilerCallback::RemotingClientInvocationFinished (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingClientInvocationFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingClientInvocationFinished
helpviewer_keywords:
- RemotingClientInvocationFinished method [.NET Framework profiling]
- ICorProfilerCallback::RemotingClientInvocationFinished method [.NET Framework profiling]
ms.assetid: ea4b283b-1210-4f41-a7a2-c398b1adde4e
topic_type:
- apiref
ms.openlocfilehash: bc15139e10b7634c50604d9a05ba290566145c21
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99648018"
---
# <a name="icorprofilercallbackremotingclientinvocationfinished-method"></a><span data-ttu-id="421a8-103">ICorProfilerCallback::RemotingClientInvocationFinished (Método)</span><span class="sxs-lookup"><span data-stu-id="421a8-103">ICorProfilerCallback::RemotingClientInvocationFinished Method</span></span>

<span data-ttu-id="421a8-104">Notifica al generador de perfiles que se ha ejecutado una llamada de comunicación remota para completarse en el cliente.</span><span class="sxs-lookup"><span data-stu-id="421a8-104">Notifies the profiler that a remoting call has run to completion on the client.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="421a8-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="421a8-105">Syntax</span></span>  
  
```cpp  
HRESULT RemotingClientInvocationFinished();  
```  
  
## <a name="remarks"></a><span data-ttu-id="421a8-106">Observaciones</span><span class="sxs-lookup"><span data-stu-id="421a8-106">Remarks</span></span>  

 <span data-ttu-id="421a8-107">Si la llamada de comunicación remota fue sincrónica, también se ha ejecutado hasta completarse en el servidor.</span><span class="sxs-lookup"><span data-stu-id="421a8-107">If the remoting call was synchronous, it has also run to completion on the server.</span></span> <span data-ttu-id="421a8-108">Si la llamada de comunicación remota es asincrónica, se podría esperar una respuesta cuando se controla la llamada.</span><span class="sxs-lookup"><span data-stu-id="421a8-108">If the remoting call was asynchronous, a reply might still be expected when the call is handled.</span></span> <span data-ttu-id="421a8-109">Si se espera una respuesta, se producirá como una llamada a [ICorProfilerCallback:: remotingclientreceivingreply (](icorprofilercallback-remotingclientreceivingreply-method.md) y una llamada adicional a `RemotingClientInvocationFinished` para indicar el procesamiento secundario necesario de una llamada asincrónica.</span><span class="sxs-lookup"><span data-stu-id="421a8-109">If a reply is expected, it will occur as a call to [ICorProfilerCallback::RemotingClientReceivingReply](icorprofilercallback-remotingclientreceivingreply-method.md) and an additional call to `RemotingClientInvocationFinished` to indicate the required secondary processing of an asynchronous call.</span></span>  
  
 <span data-ttu-id="421a8-110">Cada uno de los siguientes pares de devoluciones de llamada se producirá en el mismo subproceso:</span><span class="sxs-lookup"><span data-stu-id="421a8-110">Each of the following pairs of callbacks will occur on the same thread:</span></span>  
  
- <span data-ttu-id="421a8-111">`RemotingClientInvocationStarted` y [ICorProfilerCallback:: remotingclientsendingmessage (](icorprofilercallback-remotingclientsendingmessage-method.md)</span><span class="sxs-lookup"><span data-stu-id="421a8-111">`RemotingClientInvocationStarted` and [ICorProfilerCallback::RemotingClientSendingMessage](icorprofilercallback-remotingclientsendingmessage-method.md)</span></span>  
  
- <span data-ttu-id="421a8-112">[ICorProfilerCallback:: remotingclientreceivingreply (](icorprofilercallback-remotingclientreceivingreply-method.md) e [ICorProfilerCallback:: remotingclientinvocationfinished (](icorprofilercallback-remotingclientinvocationfinished-method.md)</span><span class="sxs-lookup"><span data-stu-id="421a8-112">[ICorProfilerCallback::RemotingClientReceivingReply](icorprofilercallback-remotingclientreceivingreply-method.md) and [ICorProfilerCallback::RemotingClientInvocationFinished](icorprofilercallback-remotingclientinvocationfinished-method.md)</span></span>  
  
- <span data-ttu-id="421a8-113">[ICorProfilerCallback:: RemotingServerInvocationReturned (](icorprofilercallback-remotingserverinvocationreturned-method.md) e [ICorProfilerCallback:: RemotingServerSendingReply (](icorprofilercallback-remotingserversendingreply-method.md)</span><span class="sxs-lookup"><span data-stu-id="421a8-113">[ICorProfilerCallback::RemotingServerInvocationReturned](icorprofilercallback-remotingserverinvocationreturned-method.md) and [ICorProfilerCallback::RemotingServerSendingReply](icorprofilercallback-remotingserversendingreply-method.md)</span></span>  
  
 <span data-ttu-id="421a8-114">Debe tener en cuenta los siguientes problemas con las devoluciones de llamada de comunicación remota:</span><span class="sxs-lookup"><span data-stu-id="421a8-114">You should be aware of the following issues with the remoting callbacks:</span></span>  
  
- <span data-ttu-id="421a8-115">La ejecución de una función de comunicación remota no se refleja en la API del generador de perfiles, por lo que las notificaciones para las funciones a las que se llama desde el cliente y que se ejecutan en el servidor no se reciben correctamente.</span><span class="sxs-lookup"><span data-stu-id="421a8-115">Execution of a remoting function is not reflected by the profiler API, so notifications for functions that are called from the client and executed on the server are not properly received.</span></span> <span data-ttu-id="421a8-116">La invocación real se produce a través de un objeto proxy. en el generador de perfiles, parece que ciertas funciones se compilan JIT pero nunca se usan.</span><span class="sxs-lookup"><span data-stu-id="421a8-116">The actual invocation happens via a proxy object; to the profiler, it appears that certain functions are JIT-compiled but never used.</span></span>  
  
- <span data-ttu-id="421a8-117">El generador de perfiles no recibe notificaciones precisas para eventos de comunicación remota asincrónica.</span><span class="sxs-lookup"><span data-stu-id="421a8-117">The profiler does not receive accurate notifications for asynchronous remoting events.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="421a8-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="421a8-118">Requirements</span></span>  

 <span data-ttu-id="421a8-119">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="421a8-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="421a8-120">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="421a8-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="421a8-121">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="421a8-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="421a8-122">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="421a8-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="421a8-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="421a8-123">See also</span></span>

- [<span data-ttu-id="421a8-124">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="421a8-124">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
