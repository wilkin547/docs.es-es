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
ms.openlocfilehash: 62973a36e899b1a8c618888e5245bfc00d8ad777
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866077"
---
# <a name="icorprofilercallbackremotingclientreceivingreply-method"></a><span data-ttu-id="182e5-102">ICorProfilerCallback::RemotingClientReceivingReply (Método)</span><span class="sxs-lookup"><span data-stu-id="182e5-102">ICorProfilerCallback::RemotingClientReceivingReply Method</span></span>
<span data-ttu-id="182e5-103">Notifica al generador de perfiles que se ha completado la parte del servidor de una llamada de comunicación remota y que el cliente está recibiendo y procesando la respuesta.</span><span class="sxs-lookup"><span data-stu-id="182e5-103">Notifies the profiler that the server-side portion of a remoting call has completed and the client is now receiving and about to process the reply.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="182e5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="182e5-104">Syntax</span></span>  
  
```cpp  
HRESULT RemotingClientReceivingReply(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);   
```  
  
## <a name="parameters"></a><span data-ttu-id="182e5-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="182e5-105">Parameters</span></span>  
 `pCookie`  
 <span data-ttu-id="182e5-106">de Un valor que se corresponderá con el valor proporcionado en [ICorProfilerCallback:: RemotingServerSendingReply (](icorprofilercallback-remotingserversendingreply-method.md) en estas condiciones:</span><span class="sxs-lookup"><span data-stu-id="182e5-106">[in] A value that will correspond with the value provided in [ICorProfilerCallback::RemotingServerSendingReply](icorprofilercallback-remotingserversendingreply-method.md) under these conditions:</span></span>  
  
- <span data-ttu-id="182e5-107">Las cookies del GUID de comunicación remota están activas.</span><span class="sxs-lookup"><span data-stu-id="182e5-107">Remoting GUID cookies are active.</span></span>  
  
- <span data-ttu-id="182e5-108">El canal realiza correctamente la transmisión del mensaje.</span><span class="sxs-lookup"><span data-stu-id="182e5-108">The channel succeeds in transmitting the message.</span></span>  
  
- <span data-ttu-id="182e5-109">Las cookies de GUID están activas en el proceso del servidor.</span><span class="sxs-lookup"><span data-stu-id="182e5-109">GUID cookies are active on the server-side process.</span></span>  
  
 <span data-ttu-id="182e5-110">Esto permite un fácil emparejamiento de llamadas remotas.</span><span class="sxs-lookup"><span data-stu-id="182e5-110">This allows easy pairing of remoting calls.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="182e5-111">de Valor que se `true` si la llamada es asincrónica; de lo contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="182e5-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="182e5-112">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="182e5-112">Requirements</span></span>  
 <span data-ttu-id="182e5-113">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="182e5-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="182e5-114">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="182e5-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="182e5-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="182e5-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="182e5-116">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="182e5-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="182e5-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="182e5-117">See also</span></span>

- [<span data-ttu-id="182e5-118">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="182e5-118">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
