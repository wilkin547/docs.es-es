---
title: ICorProfilerCallback::RemotingServerSendingReply (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingServerSendingReply
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingServerSendingReply
helpviewer_keywords:
- RemotingServerSendingReply method [.NET Framework profiling]
- ICorProfilerCallback::RemotingServerSendingReply method [.NET Framework profiling]
ms.assetid: dfe84a19-2e03-4be2-8b25-f02bad38e4a9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 024b1f3f7e08dc21582789de7f3899e8e44d5e39
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59162690"
---
# <a name="icorprofilercallbackremotingserversendingreply-method"></a><span data-ttu-id="f4a74-102">ICorProfilerCallback::RemotingServerSendingReply (Método)</span><span class="sxs-lookup"><span data-stu-id="f4a74-102">ICorProfilerCallback::RemotingServerSendingReply Method</span></span>
<span data-ttu-id="f4a74-103">Notifica al generador de perfiles que el proceso ha terminado de procesar una solicitud de invocación de método remota y está a punto de transmitir la respuesta a través de un canal.</span><span class="sxs-lookup"><span data-stu-id="f4a74-103">Notifies the profiler that the process has finished processing a remote method invocation request and is about to transmit the reply through a channel.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4a74-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f4a74-104">Syntax</span></span>  
  
```  
HRESULT RemotingServerSendingReply(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f4a74-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f4a74-105">Parameters</span></span>  
 `pCookie`  
 <span data-ttu-id="f4a74-106">[in] Un puntero a un GUID que se corresponde con el valor proporcionado en [RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) en estas condiciones:</span><span class="sxs-lookup"><span data-stu-id="f4a74-106">[in] A pointer to a GUID that will correspond with the value provided in [ICorProfilerCallback::RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) under these conditions:</span></span>  
  
-   <span data-ttu-id="f4a74-107">Las cookies GUID de comunicación remota están activas.</span><span class="sxs-lookup"><span data-stu-id="f4a74-107">Remoting GUID cookies are active.</span></span>  
  
-   <span data-ttu-id="f4a74-108">El canal se realiza correctamente en la transmisión del mensaje.</span><span class="sxs-lookup"><span data-stu-id="f4a74-108">The channel succeeds in transmitting the message.</span></span>  
  
-   <span data-ttu-id="f4a74-109">Las cookies de GUID están activas en el proceso de cliente.</span><span class="sxs-lookup"><span data-stu-id="f4a74-109">GUID cookies are active on the client-side process.</span></span>  
  
 <span data-ttu-id="f4a74-110">Esto permite que simplifica el emparejamiento de las llamadas remotas y la creación de una pila de llamadas lógicas.</span><span class="sxs-lookup"><span data-stu-id="f4a74-110">This allows easy pairing of remoting calls and the creation of a logical call stack.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="f4a74-111">[in] Un valor que es `true` si la llamada es asincrónica; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="f4a74-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f4a74-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f4a74-112">Requirements</span></span>  
 <span data-ttu-id="f4a74-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f4a74-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f4a74-114">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f4a74-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f4a74-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f4a74-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f4a74-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f4a74-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4a74-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="f4a74-117">See also</span></span>

- [<span data-ttu-id="f4a74-118">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f4a74-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
