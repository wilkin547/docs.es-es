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
ms.openlocfilehash: 2ef8f066831df1437bd0b6a6f155dd459cae1eb2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95676847"
---
# <a name="icorprofilercallbackremotingclientsendingmessage-method"></a><span data-ttu-id="ec4e2-102">ICorProfilerCallback::RemotingClientSendingMessage (Método)</span><span class="sxs-lookup"><span data-stu-id="ec4e2-102">ICorProfilerCallback::RemotingClientSendingMessage Method</span></span>

<span data-ttu-id="ec4e2-103">Notifica al generador de perfiles que el cliente envía una solicitud al servidor.</span><span class="sxs-lookup"><span data-stu-id="ec4e2-103">Notifies the profiler that the client is sending a request to the server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec4e2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ec4e2-104">Syntax</span></span>  
  
```cpp  
HRESULT RemotingClientSendingMessage(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ec4e2-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ec4e2-105">Parameters</span></span>  

 `pCookie`  
 <span data-ttu-id="ec4e2-106">de Un valor que corresponde al valor proporcionado en [ICorProfilerCallback:: remotingserverreceivingmessage (](icorprofilercallback-remotingserverreceivingmessage-method.md) en estas condiciones:</span><span class="sxs-lookup"><span data-stu-id="ec4e2-106">[in] A value that corresponds with the value provided in [ICorProfilerCallback::RemotingServerReceivingMessage](icorprofilercallback-remotingserverreceivingmessage-method.md) under these conditions:</span></span>  
  
- <span data-ttu-id="ec4e2-107">Las cookies del GUID de comunicación remota están activas.</span><span class="sxs-lookup"><span data-stu-id="ec4e2-107">Remoting GUID cookies are active.</span></span>  
  
- <span data-ttu-id="ec4e2-108">El canal realiza correctamente la transmisión del mensaje.</span><span class="sxs-lookup"><span data-stu-id="ec4e2-108">The channel succeeds in transmitting the message.</span></span>  
  
- <span data-ttu-id="ec4e2-109">Las cookies de GUID están activas en el proceso del servidor.</span><span class="sxs-lookup"><span data-stu-id="ec4e2-109">GUID cookies are active on the server-side process.</span></span>  
  
 <span data-ttu-id="ec4e2-110">Esto permite un fácil emparejamiento de llamadas remotas y la creación de una pila de llamadas lógicas.</span><span class="sxs-lookup"><span data-stu-id="ec4e2-110">This allows easy pairing of remoting calls and the creation of a logical call stack.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="ec4e2-111">de Valor que es `true` si la llamada es asincrónica; de lo contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="ec4e2-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ec4e2-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ec4e2-112">Requirements</span></span>  

 <span data-ttu-id="ec4e2-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ec4e2-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec4e2-114">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ec4e2-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ec4e2-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ec4e2-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ec4e2-116">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ec4e2-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec4e2-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ec4e2-117">See also</span></span>

- [<span data-ttu-id="ec4e2-118">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ec4e2-118">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
