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
ms.openlocfilehash: 1d876644ae35d13a481b01d9e0e5ff0d0764ca18
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713956"
---
# <a name="icorprofilercallbackremotingserversendingreply-method"></a><span data-ttu-id="ca1ca-102">ICorProfilerCallback::RemotingServerSendingReply (Método)</span><span class="sxs-lookup"><span data-stu-id="ca1ca-102">ICorProfilerCallback::RemotingServerSendingReply Method</span></span>

<span data-ttu-id="ca1ca-103">Notifica al generador de perfiles que el proceso ha terminado de procesar una solicitud de invocación de método remoto y está a punto de transmitir la respuesta a través de un canal.</span><span class="sxs-lookup"><span data-stu-id="ca1ca-103">Notifies the profiler that the process has finished processing a remote method invocation request and is about to transmit the reply through a channel.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca1ca-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ca1ca-104">Syntax</span></span>  
  
```cpp  
HRESULT RemotingServerSendingReply(  
    [in] GUID *pCookie,  
    [in] BOOL fIsAsync);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ca1ca-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ca1ca-105">Parameters</span></span>  

 `pCookie`  
 <span data-ttu-id="ca1ca-106">de Un puntero a un GUID que se corresponderá con el valor proporcionado en [ICorProfilerCallback:: remotingclientreceivingreply (](icorprofilercallback-remotingclientreceivingreply-method.md) en estas condiciones:</span><span class="sxs-lookup"><span data-stu-id="ca1ca-106">[in] A pointer to a GUID that will correspond with the value provided in [ICorProfilerCallback::RemotingClientReceivingReply](icorprofilercallback-remotingclientreceivingreply-method.md) under these conditions:</span></span>  
  
- <span data-ttu-id="ca1ca-107">Las cookies del GUID de comunicación remota están activas.</span><span class="sxs-lookup"><span data-stu-id="ca1ca-107">Remoting GUID cookies are active.</span></span>  
  
- <span data-ttu-id="ca1ca-108">El canal realiza correctamente la transmisión del mensaje.</span><span class="sxs-lookup"><span data-stu-id="ca1ca-108">The channel succeeds in transmitting the message.</span></span>  
  
- <span data-ttu-id="ca1ca-109">Las cookies de GUID están activas en el proceso del lado cliente.</span><span class="sxs-lookup"><span data-stu-id="ca1ca-109">GUID cookies are active on the client-side process.</span></span>  
  
 <span data-ttu-id="ca1ca-110">Esto permite un fácil emparejamiento de llamadas remotas y la creación de una pila de llamadas lógicas.</span><span class="sxs-lookup"><span data-stu-id="ca1ca-110">This allows easy pairing of remoting calls and the creation of a logical call stack.</span></span>  
  
 `fIsAsync`  
 <span data-ttu-id="ca1ca-111">de Valor que es `true` si la llamada es asincrónica; de lo contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="ca1ca-111">[in] A value that is `true` if the call is asynchronous; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca1ca-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ca1ca-112">Requirements</span></span>  

 <span data-ttu-id="ca1ca-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ca1ca-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca1ca-114">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ca1ca-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ca1ca-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ca1ca-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ca1ca-116">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca1ca-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca1ca-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ca1ca-117">See also</span></span>

- [<span data-ttu-id="ca1ca-118">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ca1ca-118">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
