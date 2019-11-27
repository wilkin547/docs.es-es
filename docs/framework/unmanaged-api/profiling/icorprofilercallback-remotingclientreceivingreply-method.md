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
ms.openlocfilehash: e25cbfabc10da0c7b1095a956583bb5c7450dba9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445808"
---
# <a name="icorprofilercallbackremotingclientreceivingreply-method"></a><span data-ttu-id="216ec-102">ICorProfilerCallback::RemotingClientReceivingReply (Método)</span><span class="sxs-lookup"><span data-stu-id="216ec-102">ICorProfilerCallback::RemotingClientReceivingReply Method</span></span>
<span data-ttu-id="216ec-103">Notifica al generador de perfiles que se ha completado la parte del servidor de una llamada de comunicación remota y que el cliente está recibiendo y procesando la respuesta.</span><span class="sxs-lookup"><span data-stu-id="216ec-103">Notifies the profiler that the server-side portion of a remoting call has completed and the client is now receiving and about to process the reply.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="216ec-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="216ec-104">Syntax</span></span>  
  
```cpp  
HRESULT RemotingClientReceivingReply(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);   
```  
  
## <a name="parameters"></a><span data-ttu-id="216ec-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="216ec-105">Parameters</span></span>  
 `pCookie`  
 <span data-ttu-id="216ec-106">de Un valor que se corresponderá con el valor proporcionado en [ICorProfilerCallback:: RemotingServerSendingReply (](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md) en estas condiciones:</span><span class="sxs-lookup"><span data-stu-id="216ec-106">[in] A value that will correspond with the value provided in [ICorProfilerCallback::RemotingServerSendingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md) under these conditions:</span></span>  
  
- <span data-ttu-id="216ec-107">Las cookies del GUID de comunicación remota están activas.</span><span class="sxs-lookup"><span data-stu-id="216ec-107">Remoting GUID cookies are active.</span></span>  
  
- <span data-ttu-id="216ec-108">El canal realiza correctamente la transmisión del mensaje.</span><span class="sxs-lookup"><span data-stu-id="216ec-108">The channel succeeds in transmitting the message.</span></span>  
  
- <span data-ttu-id="216ec-109">Las cookies de GUID están activas en el proceso del servidor.</span><span class="sxs-lookup"><span data-stu-id="216ec-109">GUID cookies are active on the server-side process.</span></span>  
  
 <span data-ttu-id="216ec-110">Esto permite un fácil emparejamiento de llamadas remotas.</span><span class="sxs-lookup"><span data-stu-id="216ec-110">This allows easy pairing of remoting calls.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="216ec-111">de Valor que se `true` si la llamada es asincrónica; de lo contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="216ec-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="216ec-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="216ec-112">Requirements</span></span>  
 <span data-ttu-id="216ec-113">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="216ec-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="216ec-114">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="216ec-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="216ec-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="216ec-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="216ec-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="216ec-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="216ec-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="216ec-117">See also</span></span>

- [<span data-ttu-id="216ec-118">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="216ec-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
