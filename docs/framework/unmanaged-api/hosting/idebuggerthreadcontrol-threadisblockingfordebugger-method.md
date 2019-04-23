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
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59154237"
---
# <a name="idebuggerthreadcontrolthreadisblockingfordebugger-method"></a><span data-ttu-id="b7896-102">IDebuggerThreadControl::ThreadIsBlockingForDebugger (Método)</span><span class="sxs-lookup"><span data-stu-id="b7896-102">IDebuggerThreadControl::ThreadIsBlockingForDebugger Method</span></span>
<span data-ttu-id="b7896-103">Notifica al host que el subproceso que está enviando esta devolución de llamada se acerca al bloque dentro de los servicios de depuración.</span><span class="sxs-lookup"><span data-stu-id="b7896-103">Notifies the host that the thread that is sending this callback is about to block within the debugging services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7896-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b7896-104">Syntax</span></span>  
  
```  
HRESULT ThreadIsBlockingForDebugger ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="b7896-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b7896-105">Remarks</span></span>  
 <span data-ttu-id="b7896-106">El `ThreadIsBlockingForDebugger` siempre se llamará el método en un subproceso en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="b7896-106">The `ThreadIsBlockingForDebugger` method will always be called on a runtime thread.</span></span>  
  
 <span data-ttu-id="b7896-107">El `ThreadIsBlockingForDebugger` método proporciona al host una oportunidad para realizar otra acción mientras se bloquea el subproceso.</span><span class="sxs-lookup"><span data-stu-id="b7896-107">The `ThreadIsBlockingForDebugger` method gives the host an opportunity to perform another action while the thread blocks.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7896-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b7896-108">Requirements</span></span>  
 <span data-ttu-id="b7896-109">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b7896-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7896-110">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b7896-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b7896-111">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b7896-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b7896-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b7896-112">**NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7896-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="b7896-113">See also</span></span>

- [<span data-ttu-id="b7896-114">IDebuggerThreadControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b7896-114">IDebuggerThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md)
