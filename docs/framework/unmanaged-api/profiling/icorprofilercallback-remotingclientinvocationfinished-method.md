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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ec45b73b496efdbe6328985b5f77f731d8a78cc7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33453410"
---
# <a name="icorprofilercallbackremotingclientinvocationfinished-method"></a><span data-ttu-id="451aa-102">ICorProfilerCallback::RemotingClientInvocationFinished (Método)</span><span class="sxs-lookup"><span data-stu-id="451aa-102">ICorProfilerCallback::RemotingClientInvocationFinished Method</span></span>
<span data-ttu-id="451aa-103">Notifica al generador de perfiles que una llamada de comunicación remota se ejecute hasta completarse en el cliente.</span><span class="sxs-lookup"><span data-stu-id="451aa-103">Notifies the profiler that a remoting call has run to completion on the client.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="451aa-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="451aa-104">Syntax</span></span>  
  
```  
HRESULT RemotingClientInvocationFinished();  
```  
  
## <a name="remarks"></a><span data-ttu-id="451aa-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="451aa-105">Remarks</span></span>  
 <span data-ttu-id="451aa-106">Si la llamada remota fue sincrónica, también se ejecutan hasta completarse en el servidor.</span><span class="sxs-lookup"><span data-stu-id="451aa-106">If the remoting call was synchronous, it has also run to completion on the server.</span></span> <span data-ttu-id="451aa-107">Si la llamada remota fue asincrónica, una respuesta todavía se podría esperar cuando se controla la llamada.</span><span class="sxs-lookup"><span data-stu-id="451aa-107">If the remoting call was asynchronous, a reply might still be expected when the call is handled.</span></span> <span data-ttu-id="451aa-108">Si se espera una respuesta, se producirá como una llamada a [ICorProfilerCallback:: RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) y una llamada adicional al `RemotingClientInvocationFinished` para indicar el procesamiento secundario necesario de una llamada asincrónica.</span><span class="sxs-lookup"><span data-stu-id="451aa-108">If a reply is expected, it will occur as a call to [ICorProfilerCallback::RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) and an additional call to `RemotingClientInvocationFinished` to indicate the required secondary processing of an asynchronous call.</span></span>  
  
 <span data-ttu-id="451aa-109">Cada uno de los siguientes pares de devoluciones de llamada se producirá en el mismo subproceso:</span><span class="sxs-lookup"><span data-stu-id="451aa-109">Each of the following pairs of callbacks will occur on the same thread:</span></span>  
  
-   <span data-ttu-id="451aa-110">`RemotingClientInvocationStarted` y [ICorProfilerCallback:: RemotingClientSendingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md)</span><span class="sxs-lookup"><span data-stu-id="451aa-110">`RemotingClientInvocationStarted` and [ICorProfilerCallback::RemotingClientSendingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md)</span></span>  
  
-   <span data-ttu-id="451aa-111">[ICorProfilerCallback:: RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) y [ICorProfilerCallback:: RemotingClientInvocationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientinvocationfinished-method.md)</span><span class="sxs-lookup"><span data-stu-id="451aa-111">[ICorProfilerCallback::RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) and [ICorProfilerCallback::RemotingClientInvocationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientinvocationfinished-method.md)</span></span>  
  
-   <span data-ttu-id="451aa-112">[ICorProfilerCallback:: RemotingServerInvocationReturned](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverinvocationreturned-method.md) y [ICorProfilerCallback:: RemotingServerSendingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md)</span><span class="sxs-lookup"><span data-stu-id="451aa-112">[ICorProfilerCallback::RemotingServerInvocationReturned](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverinvocationreturned-method.md) and [ICorProfilerCallback::RemotingServerSendingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md)</span></span>  
  
 <span data-ttu-id="451aa-113">Debe tener en cuenta los siguientes problemas con las devoluciones de llamada de comunicación remota:</span><span class="sxs-lookup"><span data-stu-id="451aa-113">You should be aware of the following issues with the remoting callbacks:</span></span>  
  
-   <span data-ttu-id="451aa-114">Ejecución de una función de comunicación remota no se refleja en el generador de perfiles API, por lo que no se reciben correctamente las notificaciones para las funciones que se llama desde el cliente y se ejecutan en el servidor.</span><span class="sxs-lookup"><span data-stu-id="451aa-114">Execution of a remoting function is not reflected by the profiler API, so notifications for functions that are called from the client and executed on the server are not properly received.</span></span> <span data-ttu-id="451aa-115">La invocación real se produce a través de un objeto de proxy; en el generador de perfiles, parece que ciertas funciones están compiladas JIT pero nunca se utiliza.</span><span class="sxs-lookup"><span data-stu-id="451aa-115">The actual invocation happens via a proxy object; to the profiler, it appears that certain functions are JIT-compiled but never used.</span></span>  
  
-   <span data-ttu-id="451aa-116">El generador de perfiles no recibe notificaciones precisas para los eventos de interacción remota asincrónica.</span><span class="sxs-lookup"><span data-stu-id="451aa-116">The profiler does not receive accurate notifications for asynchronous remoting events.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="451aa-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="451aa-117">Requirements</span></span>  
 <span data-ttu-id="451aa-118">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="451aa-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="451aa-119">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="451aa-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="451aa-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="451aa-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="451aa-121">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="451aa-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="451aa-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="451aa-122">See Also</span></span>  
 [<span data-ttu-id="451aa-123">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="451aa-123">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
