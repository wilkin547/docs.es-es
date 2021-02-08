---
description: 'Más información sobre: ICorProfilerCallback:: Remotingclientsendingmessage ((método)'
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
ms.openlocfilehash: 3d075b3f3c3ffe63c9d4401bdc182037593b5b19
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99788935"
---
# <a name="icorprofilercallbackremotingclientsendingmessage-method"></a><span data-ttu-id="76abd-103">ICorProfilerCallback::RemotingClientSendingMessage (Método)</span><span class="sxs-lookup"><span data-stu-id="76abd-103">ICorProfilerCallback::RemotingClientSendingMessage Method</span></span>

<span data-ttu-id="76abd-104">Notifica al generador de perfiles que el cliente envía una solicitud al servidor.</span><span class="sxs-lookup"><span data-stu-id="76abd-104">Notifies the profiler that the client is sending a request to the server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76abd-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="76abd-105">Syntax</span></span>  
  
```cpp  
HRESULT RemotingClientSendingMessage(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);  
```  
  
## <a name="parameters"></a><span data-ttu-id="76abd-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="76abd-106">Parameters</span></span>  

 `pCookie`  
 <span data-ttu-id="76abd-107">de Un valor que corresponde al valor proporcionado en [ICorProfilerCallback:: remotingserverreceivingmessage (](icorprofilercallback-remotingserverreceivingmessage-method.md) en estas condiciones:</span><span class="sxs-lookup"><span data-stu-id="76abd-107">[in] A value that corresponds with the value provided in [ICorProfilerCallback::RemotingServerReceivingMessage](icorprofilercallback-remotingserverreceivingmessage-method.md) under these conditions:</span></span>  
  
- <span data-ttu-id="76abd-108">Las cookies del GUID de comunicación remota están activas.</span><span class="sxs-lookup"><span data-stu-id="76abd-108">Remoting GUID cookies are active.</span></span>  
  
- <span data-ttu-id="76abd-109">El canal realiza correctamente la transmisión del mensaje.</span><span class="sxs-lookup"><span data-stu-id="76abd-109">The channel succeeds in transmitting the message.</span></span>  
  
- <span data-ttu-id="76abd-110">Las cookies de GUID están activas en el proceso del servidor.</span><span class="sxs-lookup"><span data-stu-id="76abd-110">GUID cookies are active on the server-side process.</span></span>  
  
 <span data-ttu-id="76abd-111">Esto permite un fácil emparejamiento de llamadas remotas y la creación de una pila de llamadas lógicas.</span><span class="sxs-lookup"><span data-stu-id="76abd-111">This allows easy pairing of remoting calls and the creation of a logical call stack.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="76abd-112">de Valor que es `true` si la llamada es asincrónica; de lo contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="76abd-112">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="76abd-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="76abd-113">Requirements</span></span>  

 <span data-ttu-id="76abd-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="76abd-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="76abd-115">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="76abd-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="76abd-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="76abd-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="76abd-117">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="76abd-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76abd-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="76abd-118">See also</span></span>

- [<span data-ttu-id="76abd-119">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="76abd-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
