---
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
ms.openlocfilehash: d41ccd30707eba269bbac7231e06792363615544
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719325"
---
# <a name="icorprofilercallbackremotingclientinvocationfinished-method"></a><span data-ttu-id="58613-102">ICorProfilerCallback::RemotingClientInvocationFinished (Método)</span><span class="sxs-lookup"><span data-stu-id="58613-102">ICorProfilerCallback::RemotingClientInvocationFinished Method</span></span>

<span data-ttu-id="58613-103">Notifica al generador de perfiles que se ha ejecutado una llamada de comunicación remota para completarse en el cliente.</span><span class="sxs-lookup"><span data-stu-id="58613-103">Notifies the profiler that a remoting call has run to completion on the client.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58613-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="58613-104">Syntax</span></span>  
  
```cpp  
HRESULT RemotingClientInvocationFinished();  
```  
  
## <a name="remarks"></a><span data-ttu-id="58613-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="58613-105">Remarks</span></span>  

 <span data-ttu-id="58613-106">Si la llamada de comunicación remota fue sincrónica, también se ha ejecutado hasta completarse en el servidor.</span><span class="sxs-lookup"><span data-stu-id="58613-106">If the remoting call was synchronous, it has also run to completion on the server.</span></span> <span data-ttu-id="58613-107">Si la llamada de comunicación remota es asincrónica, se podría esperar una respuesta cuando se controla la llamada.</span><span class="sxs-lookup"><span data-stu-id="58613-107">If the remoting call was asynchronous, a reply might still be expected when the call is handled.</span></span> <span data-ttu-id="58613-108">Si se espera una respuesta, se producirá como una llamada a [ICorProfilerCallback:: remotingclientreceivingreply (](icorprofilercallback-remotingclientreceivingreply-method.md) y una llamada adicional a `RemotingClientInvocationFinished` para indicar el procesamiento secundario necesario de una llamada asincrónica.</span><span class="sxs-lookup"><span data-stu-id="58613-108">If a reply is expected, it will occur as a call to [ICorProfilerCallback::RemotingClientReceivingReply](icorprofilercallback-remotingclientreceivingreply-method.md) and an additional call to `RemotingClientInvocationFinished` to indicate the required secondary processing of an asynchronous call.</span></span>  
  
 <span data-ttu-id="58613-109">Cada uno de los siguientes pares de devoluciones de llamada se producirá en el mismo subproceso:</span><span class="sxs-lookup"><span data-stu-id="58613-109">Each of the following pairs of callbacks will occur on the same thread:</span></span>  
  
- <span data-ttu-id="58613-110">`RemotingClientInvocationStarted` y [ICorProfilerCallback:: remotingclientsendingmessage (](icorprofilercallback-remotingclientsendingmessage-method.md)</span><span class="sxs-lookup"><span data-stu-id="58613-110">`RemotingClientInvocationStarted` and [ICorProfilerCallback::RemotingClientSendingMessage](icorprofilercallback-remotingclientsendingmessage-method.md)</span></span>  
  
- <span data-ttu-id="58613-111">[ICorProfilerCallback:: remotingclientreceivingreply (](icorprofilercallback-remotingclientreceivingreply-method.md) e [ICorProfilerCallback:: remotingclientinvocationfinished (](icorprofilercallback-remotingclientinvocationfinished-method.md)</span><span class="sxs-lookup"><span data-stu-id="58613-111">[ICorProfilerCallback::RemotingClientReceivingReply](icorprofilercallback-remotingclientreceivingreply-method.md) and [ICorProfilerCallback::RemotingClientInvocationFinished](icorprofilercallback-remotingclientinvocationfinished-method.md)</span></span>  
  
- <span data-ttu-id="58613-112">[ICorProfilerCallback:: RemotingServerInvocationReturned (](icorprofilercallback-remotingserverinvocationreturned-method.md) e [ICorProfilerCallback:: RemotingServerSendingReply (](icorprofilercallback-remotingserversendingreply-method.md)</span><span class="sxs-lookup"><span data-stu-id="58613-112">[ICorProfilerCallback::RemotingServerInvocationReturned](icorprofilercallback-remotingserverinvocationreturned-method.md) and [ICorProfilerCallback::RemotingServerSendingReply](icorprofilercallback-remotingserversendingreply-method.md)</span></span>  
  
 <span data-ttu-id="58613-113">Debe tener en cuenta los siguientes problemas con las devoluciones de llamada de comunicación remota:</span><span class="sxs-lookup"><span data-stu-id="58613-113">You should be aware of the following issues with the remoting callbacks:</span></span>  
  
- <span data-ttu-id="58613-114">La ejecución de una función de comunicación remota no se refleja en la API del generador de perfiles, por lo que las notificaciones para las funciones a las que se llama desde el cliente y que se ejecutan en el servidor no se reciben correctamente.</span><span class="sxs-lookup"><span data-stu-id="58613-114">Execution of a remoting function is not reflected by the profiler API, so notifications for functions that are called from the client and executed on the server are not properly received.</span></span> <span data-ttu-id="58613-115">La invocación real se produce a través de un objeto proxy. en el generador de perfiles, parece que ciertas funciones se compilan JIT pero nunca se usan.</span><span class="sxs-lookup"><span data-stu-id="58613-115">The actual invocation happens via a proxy object; to the profiler, it appears that certain functions are JIT-compiled but never used.</span></span>  
  
- <span data-ttu-id="58613-116">El generador de perfiles no recibe notificaciones precisas para eventos de comunicación remota asincrónica.</span><span class="sxs-lookup"><span data-stu-id="58613-116">The profiler does not receive accurate notifications for asynchronous remoting events.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58613-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="58613-117">Requirements</span></span>  

 <span data-ttu-id="58613-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="58613-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58613-119">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="58613-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="58613-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="58613-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="58613-121">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58613-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58613-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="58613-122">See also</span></span>

- [<span data-ttu-id="58613-123">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="58613-123">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
