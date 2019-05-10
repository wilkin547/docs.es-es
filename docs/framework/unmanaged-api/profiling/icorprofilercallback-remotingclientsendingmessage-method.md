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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 62c2774701b0bb4bc322d689fec43e312bc776a3
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64662914"
---
# <a name="icorprofilercallbackremotingclientsendingmessage-method"></a><span data-ttu-id="2f3ed-102">ICorProfilerCallback::RemotingClientSendingMessage (Método)</span><span class="sxs-lookup"><span data-stu-id="2f3ed-102">ICorProfilerCallback::RemotingClientSendingMessage Method</span></span>
<span data-ttu-id="2f3ed-103">Notifica al generador de perfiles que el cliente envía una solicitud al servidor.</span><span class="sxs-lookup"><span data-stu-id="2f3ed-103">Notifies the profiler that the client is sending a request to the server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f3ed-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2f3ed-104">Syntax</span></span>  
  
```  
HRESULT RemotingClientSendingMessage(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2f3ed-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2f3ed-105">Parameters</span></span>  
 `pCookie`  
 <span data-ttu-id="2f3ed-106">[in] Un valor que se corresponde con el valor proporcionado en [RemotingServerReceivingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverreceivingmessage-method.md) en estas condiciones:</span><span class="sxs-lookup"><span data-stu-id="2f3ed-106">[in] A value that corresponds with the value provided in [ICorProfilerCallback::RemotingServerReceivingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverreceivingmessage-method.md) under these conditions:</span></span>  
  
- <span data-ttu-id="2f3ed-107">Las cookies GUID de comunicación remota están activas.</span><span class="sxs-lookup"><span data-stu-id="2f3ed-107">Remoting GUID cookies are active.</span></span>  
  
- <span data-ttu-id="2f3ed-108">El canal se realiza correctamente en la transmisión del mensaje.</span><span class="sxs-lookup"><span data-stu-id="2f3ed-108">The channel succeeds in transmitting the message.</span></span>  
  
- <span data-ttu-id="2f3ed-109">Las cookies de GUID están activas en el proceso de servidor.</span><span class="sxs-lookup"><span data-stu-id="2f3ed-109">GUID cookies are active on the server-side process.</span></span>  
  
 <span data-ttu-id="2f3ed-110">Esto permite que simplifica el emparejamiento de las llamadas remotas y la creación de una pila de llamadas lógicas.</span><span class="sxs-lookup"><span data-stu-id="2f3ed-110">This allows easy pairing of remoting calls and the creation of a logical call stack.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="2f3ed-111">[in] Un valor que es `true` si la llamada es asincrónica; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="2f3ed-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2f3ed-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2f3ed-112">Requirements</span></span>  
 <span data-ttu-id="2f3ed-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2f3ed-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2f3ed-114">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2f3ed-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2f3ed-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2f3ed-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2f3ed-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2f3ed-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f3ed-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="2f3ed-117">See also</span></span>

- [<span data-ttu-id="2f3ed-118">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2f3ed-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
