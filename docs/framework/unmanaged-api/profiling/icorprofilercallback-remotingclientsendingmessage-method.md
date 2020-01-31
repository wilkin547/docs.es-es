---
title: ICorProfilerCallback::RemotingClientSendingMessage (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingClientSendingMessage
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingClientSendingMessage
helpviewer_keywords:
- RemotingClientSendingMessage method [.NET Framework profiling]
- ICorProfilerCallback::RemotingClientSendingMessage method [.NET Framework profiling]
ms.assetid: 54d9a5a5-3877-49c1-a503-ce7c7943bc2a
topic_type:
- apiref
ms.openlocfilehash: 8ae58344a7a17637bf08b9b5179abdba7e7060d6
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866031"
---
# <a name="icorprofilercallbackremotingclientsendingmessage-method"></a><span data-ttu-id="67a25-102">ICorProfilerCallback::RemotingClientSendingMessage (Método)</span><span class="sxs-lookup"><span data-stu-id="67a25-102">ICorProfilerCallback::RemotingClientSendingMessage Method</span></span>
<span data-ttu-id="67a25-103">Notifica al generador de perfiles que el cliente envía una solicitud al servidor.</span><span class="sxs-lookup"><span data-stu-id="67a25-103">Notifies the profiler that the client is sending a request to the server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67a25-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="67a25-104">Syntax</span></span>  
  
```cpp  
HRESULT RemotingClientSendingMessage(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);  
```  
  
## <a name="parameters"></a><span data-ttu-id="67a25-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="67a25-105">Parameters</span></span>  
 `pCookie`  
 <span data-ttu-id="67a25-106">de Un valor que corresponde al valor proporcionado en [ICorProfilerCallback:: remotingserverreceivingmessage (](icorprofilercallback-remotingserverreceivingmessage-method.md) en estas condiciones:</span><span class="sxs-lookup"><span data-stu-id="67a25-106">[in] A value that corresponds with the value provided in [ICorProfilerCallback::RemotingServerReceivingMessage](icorprofilercallback-remotingserverreceivingmessage-method.md) under these conditions:</span></span>  
  
- <span data-ttu-id="67a25-107">Las cookies del GUID de comunicación remota están activas.</span><span class="sxs-lookup"><span data-stu-id="67a25-107">Remoting GUID cookies are active.</span></span>  
  
- <span data-ttu-id="67a25-108">El canal realiza correctamente la transmisión del mensaje.</span><span class="sxs-lookup"><span data-stu-id="67a25-108">The channel succeeds in transmitting the message.</span></span>  
  
- <span data-ttu-id="67a25-109">Las cookies de GUID están activas en el proceso del servidor.</span><span class="sxs-lookup"><span data-stu-id="67a25-109">GUID cookies are active on the server-side process.</span></span>  
  
 <span data-ttu-id="67a25-110">Esto permite un fácil emparejamiento de llamadas remotas y la creación de una pila de llamadas lógicas.</span><span class="sxs-lookup"><span data-stu-id="67a25-110">This allows easy pairing of remoting calls and the creation of a logical call stack.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="67a25-111">de Valor que se `true` si la llamada es asincrónica; de lo contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="67a25-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67a25-112">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="67a25-112">Requirements</span></span>  
 <span data-ttu-id="67a25-113">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="67a25-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67a25-114">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="67a25-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="67a25-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="67a25-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="67a25-116">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67a25-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67a25-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="67a25-117">See also</span></span>

- [<span data-ttu-id="67a25-118">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="67a25-118">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
