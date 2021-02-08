---
description: 'Más información sobre: ICorProfilerCallback:: RemotingServerSendingReply ((método)'
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
ms.openlocfilehash: 236a707fcbc051a3d00c408f71f3b4f9f452c220
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99788883"
---
# <a name="icorprofilercallbackremotingserversendingreply-method"></a><span data-ttu-id="bc7c4-103">ICorProfilerCallback::RemotingServerSendingReply (Método)</span><span class="sxs-lookup"><span data-stu-id="bc7c4-103">ICorProfilerCallback::RemotingServerSendingReply Method</span></span>

<span data-ttu-id="bc7c4-104">Notifica al generador de perfiles que el proceso ha terminado de procesar una solicitud de invocación de método remoto y está a punto de transmitir la respuesta a través de un canal.</span><span class="sxs-lookup"><span data-stu-id="bc7c4-104">Notifies the profiler that the process has finished processing a remote method invocation request and is about to transmit the reply through a channel.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc7c4-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bc7c4-105">Syntax</span></span>  
  
```cpp  
HRESULT RemotingServerSendingReply(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bc7c4-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bc7c4-106">Parameters</span></span>  

 `pCookie`  
 <span data-ttu-id="bc7c4-107">de Un puntero a un GUID que se corresponderá con el valor proporcionado en [ICorProfilerCallback:: remotingclientreceivingreply (](icorprofilercallback-remotingclientreceivingreply-method.md) en estas condiciones:</span><span class="sxs-lookup"><span data-stu-id="bc7c4-107">[in] A pointer to a GUID that will correspond with the value provided in [ICorProfilerCallback::RemotingClientReceivingReply](icorprofilercallback-remotingclientreceivingreply-method.md) under these conditions:</span></span>  
  
- <span data-ttu-id="bc7c4-108">Las cookies del GUID de comunicación remota están activas.</span><span class="sxs-lookup"><span data-stu-id="bc7c4-108">Remoting GUID cookies are active.</span></span>  
  
- <span data-ttu-id="bc7c4-109">El canal realiza correctamente la transmisión del mensaje.</span><span class="sxs-lookup"><span data-stu-id="bc7c4-109">The channel succeeds in transmitting the message.</span></span>  
  
- <span data-ttu-id="bc7c4-110">Las cookies de GUID están activas en el proceso del lado cliente.</span><span class="sxs-lookup"><span data-stu-id="bc7c4-110">GUID cookies are active on the client-side process.</span></span>  
  
 <span data-ttu-id="bc7c4-111">Esto permite un fácil emparejamiento de llamadas remotas y la creación de una pila de llamadas lógicas.</span><span class="sxs-lookup"><span data-stu-id="bc7c4-111">This allows easy pairing of remoting calls and the creation of a logical call stack.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="bc7c4-112">de Valor que es `true` si la llamada es asincrónica; de lo contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="bc7c4-112">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bc7c4-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bc7c4-113">Requirements</span></span>  

 <span data-ttu-id="bc7c4-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bc7c4-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bc7c4-115">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bc7c4-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="bc7c4-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bc7c4-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bc7c4-117">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bc7c4-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc7c4-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="bc7c4-118">See also</span></span>

- [<span data-ttu-id="bc7c4-119">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="bc7c4-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
