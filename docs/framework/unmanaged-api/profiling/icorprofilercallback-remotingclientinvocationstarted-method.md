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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b452cbfc5564d98b3770c2ed97f8453296f0fc13
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59157695"
---
# <a name="icorprofilercallbackremotingclientinvocationstarted-method"></a><span data-ttu-id="89f66-102">ICorProfilerCallback::RemotingClientInvocationStarted (Método)</span><span class="sxs-lookup"><span data-stu-id="89f66-102">ICorProfilerCallback::RemotingClientInvocationStarted Method</span></span>
<span data-ttu-id="89f66-103">Notifica al generador de perfiles que se ha iniciado una llamada remota.</span><span class="sxs-lookup"><span data-stu-id="89f66-103">Notifies the profiler that a remoting call has started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89f66-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="89f66-104">Syntax</span></span>  
  
```  
HRESULT RemotingClientInvocationStarted();  
```  
  
## <a name="remarks"></a><span data-ttu-id="89f66-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="89f66-105">Remarks</span></span>  
 <span data-ttu-id="89f66-106">Este evento es el mismo para las llamadas sincrónicas y asincrónicas.</span><span class="sxs-lookup"><span data-stu-id="89f66-106">This event is the same for synchronous and asynchronous calls.</span></span>  
  
 <span data-ttu-id="89f66-107">Cada uno de los siguientes pares de devoluciones de llamada se producirá en el mismo subproceso:</span><span class="sxs-lookup"><span data-stu-id="89f66-107">Each of the following pairs of callbacks will occur on the same thread:</span></span>  
  
-   `RemotingClientInvocationStarted` <span data-ttu-id="89f66-108">and [ICorProfilerCallback::RemotingClientSendingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md)</span><span class="sxs-lookup"><span data-stu-id="89f66-108">and [ICorProfilerCallback::RemotingClientSendingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md)</span></span>  
  
-   <span data-ttu-id="89f66-109">[ICorProfilerCallback::RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) and [ICorProfilerCallback::RemotingClientInvocationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientinvocationfinished-method.md)</span><span class="sxs-lookup"><span data-stu-id="89f66-109">[ICorProfilerCallback::RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) and [ICorProfilerCallback::RemotingClientInvocationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientinvocationfinished-method.md)</span></span>  
  
-   <span data-ttu-id="89f66-110">[RemotingServerInvocationReturned](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverinvocationreturned-method.md) y [RemotingServerSendingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md)</span><span class="sxs-lookup"><span data-stu-id="89f66-110">[ICorProfilerCallback::RemotingServerInvocationReturned](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverinvocationreturned-method.md) and [ICorProfilerCallback::RemotingServerSendingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md)</span></span>  
  
 <span data-ttu-id="89f66-111">Debe tener en cuenta los siguientes problemas con las devoluciones de llamada de comunicación remota:</span><span class="sxs-lookup"><span data-stu-id="89f66-111">You should be aware of the following issues with the remoting callbacks:</span></span>  
  
-   <span data-ttu-id="89f66-112">Ejecución de una función de comunicación remota no se refleja en el generador de perfiles de API, por lo que no se han recibido correctamente las notificaciones para las funciones que se llama desde el cliente y se ejecuta en el servidor.</span><span class="sxs-lookup"><span data-stu-id="89f66-112">Execution of a remoting function is not reflected by the profiler API, so notifications for functions that are called from the client and executed on the server are not properly received.</span></span> <span data-ttu-id="89f66-113">La invocación real se produce a través de un objeto proxy; para el generador de perfiles, parece que algunas funciones estarán compiladas con JIT pero nunca se utiliza.</span><span class="sxs-lookup"><span data-stu-id="89f66-113">The actual invocation happens via a proxy object; to the profiler, it appears that certain functions are JIT-compiled but never used.</span></span>  
  
-   <span data-ttu-id="89f66-114">El generador de perfiles no recibe notificaciones precisas para los eventos de comunicación remota asincrónica.</span><span class="sxs-lookup"><span data-stu-id="89f66-114">The profiler does not receive accurate notifications for asynchronous remoting events.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89f66-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="89f66-115">Requirements</span></span>  
 <span data-ttu-id="89f66-116">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="89f66-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89f66-117">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="89f66-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="89f66-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="89f66-118">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="89f66-119">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="89f66-119">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="89f66-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="89f66-120">See also</span></span>

- [<span data-ttu-id="89f66-121">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="89f66-121">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
