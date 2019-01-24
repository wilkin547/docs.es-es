---
title: ICorProfilerCallback::RemotingClientReceivingReply (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingClientReceivingReply
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingClientReceivingReply
helpviewer_keywords:
- ICorProfilerCallback::RemotingClientReceivingReply method [.NET Framework profiling]
- RemotingClientReceivingReply method [.NET Framework profiling]
ms.assetid: 15cfc300-8231-4ecb-9a04-19851c3eb484
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 313dd7526478377ca457d165de4b95e7e81d93f8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54599795"
---
# <a name="icorprofilercallbackremotingclientreceivingreply-method"></a><span data-ttu-id="c5d1e-102">ICorProfilerCallback::RemotingClientReceivingReply (Método)</span><span class="sxs-lookup"><span data-stu-id="c5d1e-102">ICorProfilerCallback::RemotingClientReceivingReply Method</span></span>
<span data-ttu-id="c5d1e-103">Notifica al generador de perfiles que se ha completado la parte del servidor de una llamada remota y el cliente ahora recibe y a procesar la respuesta.</span><span class="sxs-lookup"><span data-stu-id="c5d1e-103">Notifies the profiler that the server-side portion of a remoting call has completed and the client is now receiving and about to process the reply.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5d1e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c5d1e-104">Syntax</span></span>  
  
```  
HRESULT RemotingClientReceivingReply(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="c5d1e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c5d1e-105">Parameters</span></span>  
 `pCookie`  
 <span data-ttu-id="c5d1e-106">[in] Un valor que se corresponde con el valor proporcionado en [RemotingServerSendingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md) en estas condiciones:</span><span class="sxs-lookup"><span data-stu-id="c5d1e-106">[in] A value that will correspond with the value provided in [ICorProfilerCallback::RemotingServerSendingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md) under these conditions:</span></span>  
  
-   <span data-ttu-id="c5d1e-107">Las cookies GUID de comunicación remota están activas.</span><span class="sxs-lookup"><span data-stu-id="c5d1e-107">Remoting GUID cookies are active.</span></span>  
  
-   <span data-ttu-id="c5d1e-108">El canal se realiza correctamente en la transmisión del mensaje.</span><span class="sxs-lookup"><span data-stu-id="c5d1e-108">The channel succeeds in transmitting the message.</span></span>  
  
-   <span data-ttu-id="c5d1e-109">Las cookies de GUID están activas en el proceso de servidor.</span><span class="sxs-lookup"><span data-stu-id="c5d1e-109">GUID cookies are active on the server-side process.</span></span>  
  
 <span data-ttu-id="c5d1e-110">Esto permite que simplifica el emparejamiento de las llamadas remotas.</span><span class="sxs-lookup"><span data-stu-id="c5d1e-110">This allows easy pairing of remoting calls.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="c5d1e-111">[in] Un valor que es `true` si la llamada es asincrónica; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="c5d1e-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c5d1e-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c5d1e-112">Requirements</span></span>  
 <span data-ttu-id="c5d1e-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c5d1e-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c5d1e-114">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c5d1e-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c5d1e-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c5d1e-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c5d1e-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c5d1e-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5d1e-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="c5d1e-117">See also</span></span>
- [<span data-ttu-id="c5d1e-118">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c5d1e-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
