---
title: "ICorProfilerCallback::RemotingServerReceivingMessage (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorProfilerCallback.RemotingServerReceivingMessage
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingServerReceivingMessage
helpviewer_keywords:
- ICorProfilerCallback::RemotingServerReceivingMessage method [.NET Framework profiling]
- RemotingServerReceivingMessage method [.NET Framework profiling]
ms.assetid: 5604d21f-e6b7-490e-b469-42122a7568e1
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e4542f5362d83bc5c0419b9f1ff389c9a21aad29
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackremotingserverreceivingmessage-method"></a><span data-ttu-id="b4fe2-102">ICorProfilerCallback::RemotingServerReceivingMessage (Método)</span><span class="sxs-lookup"><span data-stu-id="b4fe2-102">ICorProfilerCallback::RemotingServerReceivingMessage Method</span></span>
<span data-ttu-id="b4fe2-103">Notifica al generador de perfiles que el proceso ha recibido una solicitud de activación o la invocación de método remoto.</span><span class="sxs-lookup"><span data-stu-id="b4fe2-103">Notifies the profiler that the process has received a remote method invocation or activation request.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4fe2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b4fe2-104">Syntax</span></span>  
  
```  
HRESULT RemotingClientSendingMessage(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b4fe2-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b4fe2-105">Parameters</span></span>  
 `pCookie`  
 <span data-ttu-id="b4fe2-106">[in] Un valor que se corresponderá con el valor proporcionado en [ICorProfilerCallback:: RemotingClientSendingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md) en estas condiciones:</span><span class="sxs-lookup"><span data-stu-id="b4fe2-106">[in] A value that will correspond with the value provided in [ICorProfilerCallback::RemotingClientSendingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md) under these conditions:</span></span>  
  
-   <span data-ttu-id="b4fe2-107">Las cookies GUID de comunicación remota están activas.</span><span class="sxs-lookup"><span data-stu-id="b4fe2-107">Remoting GUID cookies are active.</span></span>  
  
-   <span data-ttu-id="b4fe2-108">El canal consigue transmitir el mensaje.</span><span class="sxs-lookup"><span data-stu-id="b4fe2-108">The channel succeeds in transmitting the message.</span></span>  
  
-   <span data-ttu-id="b4fe2-109">Las cookies de GUID están activas en el proceso de cliente.</span><span class="sxs-lookup"><span data-stu-id="b4fe2-109">GUID cookies are active on the client-side process.</span></span>  
  
 <span data-ttu-id="b4fe2-110">Esto permite la fácil emparejamiento de las llamadas remotas y la creación de una pila de llamadas lógica.</span><span class="sxs-lookup"><span data-stu-id="b4fe2-110">This allows easy pairing of remoting calls and the creation of a logical call stack.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="b4fe2-111">[in] Un valor que es `true` si la llamada es asincrónica; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="b4fe2-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b4fe2-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b4fe2-112">Remarks</span></span>  
 <span data-ttu-id="b4fe2-113">Si la solicitud de mensaje es asincrónica, la solicitud puede ser atendida por cualquier subproceso arbitrario.</span><span class="sxs-lookup"><span data-stu-id="b4fe2-113">If the message request is asynchronous, the request can be serviced by any arbitrary thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4fe2-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b4fe2-114">Requirements</span></span>  
 <span data-ttu-id="b4fe2-115">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b4fe2-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4fe2-116">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b4fe2-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b4fe2-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b4fe2-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b4fe2-118">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4fe2-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4fe2-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="b4fe2-119">See Also</span></span>  
 [<span data-ttu-id="b4fe2-120">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b4fe2-120">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
