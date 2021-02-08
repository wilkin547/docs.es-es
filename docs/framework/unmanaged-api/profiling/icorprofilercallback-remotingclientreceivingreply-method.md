---
description: 'Más información sobre: ICorProfilerCallback:: Remotingclientreceivingreply ((método)'
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
ms.openlocfilehash: 4c1d42baa9f4381b66c9be75afa239899ae81b81
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99788948"
---
# <a name="icorprofilercallbackremotingclientreceivingreply-method"></a><span data-ttu-id="28476-103">ICorProfilerCallback::RemotingClientReceivingReply (Método)</span><span class="sxs-lookup"><span data-stu-id="28476-103">ICorProfilerCallback::RemotingClientReceivingReply Method</span></span>

<span data-ttu-id="28476-104">Notifica al generador de perfiles que se ha completado la parte del servidor de una llamada de comunicación remota y que el cliente está recibiendo y procesando la respuesta.</span><span class="sxs-lookup"><span data-stu-id="28476-104">Notifies the profiler that the server-side portion of a remoting call has completed and the client is now receiving and about to process the reply.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28476-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="28476-105">Syntax</span></span>  
  
```cpp  
HRESULT RemotingClientReceivingReply(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);
```  
  
## <a name="parameters"></a><span data-ttu-id="28476-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="28476-106">Parameters</span></span>  

 `pCookie`  
 <span data-ttu-id="28476-107">de Un valor que se corresponderá con el valor proporcionado en [ICorProfilerCallback:: RemotingServerSendingReply (](icorprofilercallback-remotingserversendingreply-method.md) en estas condiciones:</span><span class="sxs-lookup"><span data-stu-id="28476-107">[in] A value that will correspond with the value provided in [ICorProfilerCallback::RemotingServerSendingReply](icorprofilercallback-remotingserversendingreply-method.md) under these conditions:</span></span>  
  
- <span data-ttu-id="28476-108">Las cookies del GUID de comunicación remota están activas.</span><span class="sxs-lookup"><span data-stu-id="28476-108">Remoting GUID cookies are active.</span></span>  
  
- <span data-ttu-id="28476-109">El canal realiza correctamente la transmisión del mensaje.</span><span class="sxs-lookup"><span data-stu-id="28476-109">The channel succeeds in transmitting the message.</span></span>  
  
- <span data-ttu-id="28476-110">Las cookies de GUID están activas en el proceso del servidor.</span><span class="sxs-lookup"><span data-stu-id="28476-110">GUID cookies are active on the server-side process.</span></span>  
  
 <span data-ttu-id="28476-111">Esto permite un fácil emparejamiento de llamadas remotas.</span><span class="sxs-lookup"><span data-stu-id="28476-111">This allows easy pairing of remoting calls.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="28476-112">de Valor que es `true` si la llamada es asincrónica; de lo contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="28476-112">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="28476-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="28476-113">Requirements</span></span>  

 <span data-ttu-id="28476-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="28476-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="28476-115">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="28476-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="28476-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="28476-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="28476-117">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="28476-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28476-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="28476-118">See also</span></span>

- [<span data-ttu-id="28476-119">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="28476-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
