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
ms.openlocfilehash: 1aa5a0d20ee87fe4362016ed0d7fa29ef786460e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74430716"
---
# <a name="icorprofilercallbackremotingserversendingreply-method"></a><span data-ttu-id="2a3ff-102">ICorProfilerCallback::RemotingServerSendingReply (Método)</span><span class="sxs-lookup"><span data-stu-id="2a3ff-102">ICorProfilerCallback::RemotingServerSendingReply Method</span></span>
<span data-ttu-id="2a3ff-103">Notifica al generador de perfiles que el proceso ha terminado de procesar una solicitud de invocación de método remoto y está a punto de transmitir la respuesta a través de un canal.</span><span class="sxs-lookup"><span data-stu-id="2a3ff-103">Notifies the profiler that the process has finished processing a remote method invocation request and is about to transmit the reply through a channel.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a3ff-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2a3ff-104">Syntax</span></span>  
  
```cpp  
HRESULT RemotingServerSendingReply(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2a3ff-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2a3ff-105">Parameters</span></span>  
 `pCookie`  
 <span data-ttu-id="2a3ff-106">de Un puntero a un GUID que se corresponderá con el valor proporcionado en [ICorProfilerCallback:: remotingclientreceivingreply (](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) en estas condiciones:</span><span class="sxs-lookup"><span data-stu-id="2a3ff-106">[in] A pointer to a GUID that will correspond with the value provided in [ICorProfilerCallback::RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) under these conditions:</span></span>  
  
- <span data-ttu-id="2a3ff-107">Las cookies del GUID de comunicación remota están activas.</span><span class="sxs-lookup"><span data-stu-id="2a3ff-107">Remoting GUID cookies are active.</span></span>  
  
- <span data-ttu-id="2a3ff-108">El canal realiza correctamente la transmisión del mensaje.</span><span class="sxs-lookup"><span data-stu-id="2a3ff-108">The channel succeeds in transmitting the message.</span></span>  
  
- <span data-ttu-id="2a3ff-109">Las cookies de GUID están activas en el proceso del lado cliente.</span><span class="sxs-lookup"><span data-stu-id="2a3ff-109">GUID cookies are active on the client-side process.</span></span>  
  
 <span data-ttu-id="2a3ff-110">Esto permite un fácil emparejamiento de llamadas remotas y la creación de una pila de llamadas lógicas.</span><span class="sxs-lookup"><span data-stu-id="2a3ff-110">This allows easy pairing of remoting calls and the creation of a logical call stack.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="2a3ff-111">de Valor que se `true` si la llamada es asincrónica; de lo contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="2a3ff-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2a3ff-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2a3ff-112">Requirements</span></span>  
 <span data-ttu-id="2a3ff-113">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2a3ff-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a3ff-114">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2a3ff-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2a3ff-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2a3ff-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2a3ff-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a3ff-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a3ff-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="2a3ff-117">See also</span></span>

- [<span data-ttu-id="2a3ff-118">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2a3ff-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
