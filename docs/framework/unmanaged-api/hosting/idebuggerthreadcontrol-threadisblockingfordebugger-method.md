---
title: IDebuggerThreadControl::ThreadIsBlockingForDebugger (Método)
ms.date: 03/30/2017
api_name:
- IDebuggerThreadControl.ThreadIsBlockingForDebugger
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ThreadIsBlockingForDebugger
helpviewer_keywords:
- ThreadIsBlockingForDebugger method [.NET Framework hosting]
- IDebuggerThreadControl::ThreadIsBlockingForDebugger method [.NET Framework hosting]
ms.assetid: d4d7cb2d-69da-48b3-879a-1a8a68c9bfa8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 47ff178cc9ab798593848e56fc7bba8ac82ae295
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61699700"
---
# <a name="idebuggerthreadcontrolthreadisblockingfordebugger-method"></a><span data-ttu-id="8555a-102">IDebuggerThreadControl::ThreadIsBlockingForDebugger (Método)</span><span class="sxs-lookup"><span data-stu-id="8555a-102">IDebuggerThreadControl::ThreadIsBlockingForDebugger Method</span></span>
<span data-ttu-id="8555a-103">Notifica al host que el subproceso que está enviando esta devolución de llamada se acerca al bloque dentro de los servicios de depuración.</span><span class="sxs-lookup"><span data-stu-id="8555a-103">Notifies the host that the thread that is sending this callback is about to block within the debugging services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8555a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8555a-104">Syntax</span></span>  
  
```  
HRESULT ThreadIsBlockingForDebugger ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="8555a-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8555a-105">Remarks</span></span>  
 <span data-ttu-id="8555a-106">El `ThreadIsBlockingForDebugger` siempre se llamará el método en un subproceso en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="8555a-106">The `ThreadIsBlockingForDebugger` method will always be called on a runtime thread.</span></span>  
  
 <span data-ttu-id="8555a-107">El `ThreadIsBlockingForDebugger` método proporciona al host una oportunidad para realizar otra acción mientras se bloquea el subproceso.</span><span class="sxs-lookup"><span data-stu-id="8555a-107">The `ThreadIsBlockingForDebugger` method gives the host an opportunity to perform another action while the thread blocks.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8555a-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8555a-108">Requirements</span></span>  
 <span data-ttu-id="8555a-109">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8555a-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8555a-110">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8555a-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8555a-111">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8555a-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8555a-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8555a-112">**NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8555a-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="8555a-113">See also</span></span>

- [<span data-ttu-id="8555a-114">IDebuggerThreadControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8555a-114">IDebuggerThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md)
