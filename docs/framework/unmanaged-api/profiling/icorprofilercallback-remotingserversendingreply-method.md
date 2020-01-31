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
ms.openlocfilehash: f77901623ef4df7b43276c18a910cf62fcc4451d
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865979"
---
# <a name="icorprofilercallbackremotingserversendingreply-method"></a><span data-ttu-id="8eab7-102">ICorProfilerCallback::RemotingServerSendingReply (Método)</span><span class="sxs-lookup"><span data-stu-id="8eab7-102">ICorProfilerCallback::RemotingServerSendingReply Method</span></span>
<span data-ttu-id="8eab7-103">Notifica al generador de perfiles que el proceso ha terminado de procesar una solicitud de invocación de método remoto y está a punto de transmitir la respuesta a través de un canal.</span><span class="sxs-lookup"><span data-stu-id="8eab7-103">Notifies the profiler that the process has finished processing a remote method invocation request and is about to transmit the reply through a channel.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8eab7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8eab7-104">Syntax</span></span>  
  
```cpp  
HRESULT RemotingServerSendingReply(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8eab7-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="8eab7-105">Parameters</span></span>  
 `pCookie`  
 <span data-ttu-id="8eab7-106">de Un puntero a un GUID que se corresponderá con el valor proporcionado en [ICorProfilerCallback:: remotingclientreceivingreply (](icorprofilercallback-remotingclientreceivingreply-method.md) en estas condiciones:</span><span class="sxs-lookup"><span data-stu-id="8eab7-106">[in] A pointer to a GUID that will correspond with the value provided in [ICorProfilerCallback::RemotingClientReceivingReply](icorprofilercallback-remotingclientreceivingreply-method.md) under these conditions:</span></span>  
  
- <span data-ttu-id="8eab7-107">Las cookies del GUID de comunicación remota están activas.</span><span class="sxs-lookup"><span data-stu-id="8eab7-107">Remoting GUID cookies are active.</span></span>  
  
- <span data-ttu-id="8eab7-108">El canal realiza correctamente la transmisión del mensaje.</span><span class="sxs-lookup"><span data-stu-id="8eab7-108">The channel succeeds in transmitting the message.</span></span>  
  
- <span data-ttu-id="8eab7-109">Las cookies de GUID están activas en el proceso del lado cliente.</span><span class="sxs-lookup"><span data-stu-id="8eab7-109">GUID cookies are active on the client-side process.</span></span>  
  
 <span data-ttu-id="8eab7-110">Esto permite un fácil emparejamiento de llamadas remotas y la creación de una pila de llamadas lógicas.</span><span class="sxs-lookup"><span data-stu-id="8eab7-110">This allows easy pairing of remoting calls and the creation of a logical call stack.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="8eab7-111">de Valor que se `true` si la llamada es asincrónica; de lo contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="8eab7-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8eab7-112">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="8eab7-112">Requirements</span></span>  
 <span data-ttu-id="8eab7-113">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8eab7-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8eab7-114">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8eab7-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8eab7-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8eab7-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8eab7-116">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8eab7-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8eab7-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="8eab7-117">See also</span></span>

- [<span data-ttu-id="8eab7-118">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8eab7-118">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
