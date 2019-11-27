---
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
ms.openlocfilehash: 2c2eb7d0dc04d813b1ce91fb1acf4b171f244592
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445764"
---
# <a name="icorprofilercallbackremotingserverreceivingmessage-method"></a><span data-ttu-id="809be-102">ICorProfilerCallback::RemotingServerReceivingMessage (Método)</span><span class="sxs-lookup"><span data-stu-id="809be-102">ICorProfilerCallback::RemotingServerReceivingMessage Method</span></span>
<span data-ttu-id="809be-103">Notifica al generador de perfiles que el proceso ha recibido una invocación de método remoto o una solicitud de activación.</span><span class="sxs-lookup"><span data-stu-id="809be-103">Notifies the profiler that the process has received a remote method invocation or activation request.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="809be-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="809be-104">Syntax</span></span>  
  
```cpp  
HRESULT RemotingClientSendingMessage(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);  
```  
  
## <a name="parameters"></a><span data-ttu-id="809be-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="809be-105">Parameters</span></span>  
 `pCookie`  
 <span data-ttu-id="809be-106">de Un valor que se corresponderá con el valor proporcionado en [ICorProfilerCallback:: remotingclientsendingmessage (](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md) en estas condiciones:</span><span class="sxs-lookup"><span data-stu-id="809be-106">[in] A value that will correspond with the value provided in [ICorProfilerCallback::RemotingClientSendingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md) under these conditions:</span></span>  
  
- <span data-ttu-id="809be-107">Las cookies del GUID de comunicación remota están activas.</span><span class="sxs-lookup"><span data-stu-id="809be-107">Remoting GUID cookies are active.</span></span>  
  
- <span data-ttu-id="809be-108">El canal realiza correctamente la transmisión del mensaje.</span><span class="sxs-lookup"><span data-stu-id="809be-108">The channel succeeds in transmitting the message.</span></span>  
  
- <span data-ttu-id="809be-109">Las cookies de GUID están activas en el proceso del lado cliente.</span><span class="sxs-lookup"><span data-stu-id="809be-109">GUID cookies are active on the client-side process.</span></span>  
  
 <span data-ttu-id="809be-110">Esto permite un fácil emparejamiento de llamadas remotas y la creación de una pila de llamadas lógicas.</span><span class="sxs-lookup"><span data-stu-id="809be-110">This allows easy pairing of remoting calls and the creation of a logical call stack.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="809be-111">de Valor que se `true` si la llamada es asincrónica; de lo contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="809be-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="809be-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="809be-112">Remarks</span></span>  
 <span data-ttu-id="809be-113">Si la solicitud de mensaje es asincrónica, cualquier subproceso arbitrario puede atender la solicitud.</span><span class="sxs-lookup"><span data-stu-id="809be-113">If the message request is asynchronous, the request can be serviced by any arbitrary thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="809be-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="809be-114">Requirements</span></span>  
 <span data-ttu-id="809be-115">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="809be-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="809be-116">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="809be-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="809be-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="809be-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="809be-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="809be-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="809be-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="809be-119">See also</span></span>

- [<span data-ttu-id="809be-120">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="809be-120">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
