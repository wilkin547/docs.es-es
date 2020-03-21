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
ms.openlocfilehash: f7a943627e2087e6b8c78ced9fc32824843d44fc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175140"
---
# <a name="icorprofilercallbackremotingclientreceivingreply-method"></a><span data-ttu-id="6c81b-102">ICorProfilerCallback::RemotingClientReceivingReply (Método)</span><span class="sxs-lookup"><span data-stu-id="6c81b-102">ICorProfilerCallback::RemotingClientReceivingReply Method</span></span>
<span data-ttu-id="6c81b-103">Notifica al generador de perfiles que la parte del lado del servidor de una llamada remota se ha completado y que el cliente ahora está recibiendo y a punto de procesar la respuesta.</span><span class="sxs-lookup"><span data-stu-id="6c81b-103">Notifies the profiler that the server-side portion of a remoting call has completed and the client is now receiving and about to process the reply.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c81b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6c81b-104">Syntax</span></span>  
  
```cpp  
HRESULT RemotingClientReceivingReply(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);
```  
  
## <a name="parameters"></a><span data-ttu-id="6c81b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6c81b-105">Parameters</span></span>  
 `pCookie`  
 <span data-ttu-id="6c81b-106">[en] Valor que se corresponderá con el valor proporcionado en [ICorProfilerCallback::RemotingServerSendingReply](icorprofilercallback-remotingserversendingreply-method.md) en estas condiciones:</span><span class="sxs-lookup"><span data-stu-id="6c81b-106">[in] A value that will correspond with the value provided in [ICorProfilerCallback::RemotingServerSendingReply](icorprofilercallback-remotingserversendingreply-method.md) under these conditions:</span></span>  
  
- <span data-ttu-id="6c81b-107">Las cookies GUID remotas están activas.</span><span class="sxs-lookup"><span data-stu-id="6c81b-107">Remoting GUID cookies are active.</span></span>  
  
- <span data-ttu-id="6c81b-108">El canal tiene éxito en la transmisión del mensaje.</span><span class="sxs-lookup"><span data-stu-id="6c81b-108">The channel succeeds in transmitting the message.</span></span>  
  
- <span data-ttu-id="6c81b-109">Las cookies GUID están activas en el proceso del lado del servidor.</span><span class="sxs-lookup"><span data-stu-id="6c81b-109">GUID cookies are active on the server-side process.</span></span>  
  
 <span data-ttu-id="6c81b-110">Esto permite un fácil emparejamiento de llamadas remotas.</span><span class="sxs-lookup"><span data-stu-id="6c81b-110">This allows easy pairing of remoting calls.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="6c81b-111">[en] Un valor `true` que es si la llamada es asincrónica; de `false`lo contrario, .</span><span class="sxs-lookup"><span data-stu-id="6c81b-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6c81b-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6c81b-112">Requirements</span></span>  
 <span data-ttu-id="6c81b-113">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6c81b-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6c81b-114">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6c81b-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6c81b-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6c81b-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6c81b-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6c81b-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c81b-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6c81b-117">See also</span></span>

- [<span data-ttu-id="6c81b-118">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="6c81b-118">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
