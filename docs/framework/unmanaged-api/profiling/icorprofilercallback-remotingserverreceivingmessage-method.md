---
description: 'Más información sobre: ICorProfilerCallback:: Remotingserverreceivingmessage ((método)'
title: ICorProfilerCallback::RemotingServerReceivingMessage (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingServerReceivingMessage
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingServerReceivingMessage
helpviewer_keywords:
- ICorProfilerCallback::RemotingServerReceivingMessage method [.NET Framework profiling]
- RemotingServerReceivingMessage method [.NET Framework profiling]
ms.assetid: 5604d21f-e6b7-490e-b469-42122a7568e1
topic_type:
- apiref
ms.openlocfilehash: 5efa706d934158d09796dfab40b132a334c10ffd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99788896"
---
# <a name="icorprofilercallbackremotingserverreceivingmessage-method"></a><span data-ttu-id="5abea-103">ICorProfilerCallback::RemotingServerReceivingMessage (Método)</span><span class="sxs-lookup"><span data-stu-id="5abea-103">ICorProfilerCallback::RemotingServerReceivingMessage Method</span></span>

<span data-ttu-id="5abea-104">Notifica al generador de perfiles que el proceso ha recibido una invocación de método remoto o una solicitud de activación.</span><span class="sxs-lookup"><span data-stu-id="5abea-104">Notifies the profiler that the process has received a remote method invocation or activation request.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5abea-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5abea-105">Syntax</span></span>  
  
```cpp  
HRESULT RemotingClientSendingMessage(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5abea-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5abea-106">Parameters</span></span>  

 `pCookie`  
 <span data-ttu-id="5abea-107">de Un valor que se corresponderá con el valor proporcionado en [ICorProfilerCallback:: remotingclientsendingmessage (](icorprofilercallback-remotingclientsendingmessage-method.md) en estas condiciones:</span><span class="sxs-lookup"><span data-stu-id="5abea-107">[in] A value that will correspond with the value provided in [ICorProfilerCallback::RemotingClientSendingMessage](icorprofilercallback-remotingclientsendingmessage-method.md) under these conditions:</span></span>  
  
- <span data-ttu-id="5abea-108">Las cookies del GUID de comunicación remota están activas.</span><span class="sxs-lookup"><span data-stu-id="5abea-108">Remoting GUID cookies are active.</span></span>  
  
- <span data-ttu-id="5abea-109">El canal realiza correctamente la transmisión del mensaje.</span><span class="sxs-lookup"><span data-stu-id="5abea-109">The channel succeeds in transmitting the message.</span></span>  
  
- <span data-ttu-id="5abea-110">Las cookies de GUID están activas en el proceso del lado cliente.</span><span class="sxs-lookup"><span data-stu-id="5abea-110">GUID cookies are active on the client-side process.</span></span>  
  
 <span data-ttu-id="5abea-111">Esto permite un fácil emparejamiento de llamadas remotas y la creación de una pila de llamadas lógicas.</span><span class="sxs-lookup"><span data-stu-id="5abea-111">This allows easy pairing of remoting calls and the creation of a logical call stack.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="5abea-112">de Valor que es `true` si la llamada es asincrónica; de lo contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="5abea-112">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5abea-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5abea-113">Remarks</span></span>  

 <span data-ttu-id="5abea-114">Si la solicitud de mensaje es asincrónica, cualquier subproceso arbitrario puede atender la solicitud.</span><span class="sxs-lookup"><span data-stu-id="5abea-114">If the message request is asynchronous, the request can be serviced by any arbitrary thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5abea-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5abea-115">Requirements</span></span>  

 <span data-ttu-id="5abea-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5abea-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5abea-117">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5abea-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5abea-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5abea-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5abea-119">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5abea-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5abea-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="5abea-120">See also</span></span>

- [<span data-ttu-id="5abea-121">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5abea-121">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
