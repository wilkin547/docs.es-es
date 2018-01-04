---
title: "IDebuggerThreadControl::ThreadIsBlockingForDebugger (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IDebuggerThreadControl.ThreadIsBlockingForDebugger
api_location: mscoree.dll
api_type: COM
f1_keywords: ThreadIsBlockingForDebugger
helpviewer_keywords:
- ThreadIsBlockingForDebugger method [.NET Framework hosting]
- IDebuggerThreadControl::ThreadIsBlockingForDebugger method [.NET Framework hosting]
ms.assetid: d4d7cb2d-69da-48b3-879a-1a8a68c9bfa8
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 59a4c13e84414dcd10b217134334777a745431c7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="idebuggerthreadcontrolthreadisblockingfordebugger-method"></a><span data-ttu-id="6ce16-102">IDebuggerThreadControl::ThreadIsBlockingForDebugger (Método)</span><span class="sxs-lookup"><span data-stu-id="6ce16-102">IDebuggerThreadControl::ThreadIsBlockingForDebugger Method</span></span>
<span data-ttu-id="6ce16-103">Notifica al host que hace referencia el subproceso que está enviando esta devolución de llamada al bloque dentro de los servicios de depuración.</span><span class="sxs-lookup"><span data-stu-id="6ce16-103">Notifies the host that the thread that is sending this callback is about to block within the debugging services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ce16-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6ce16-104">Syntax</span></span>  
  
```  
HRESULT ThreadIsBlockingForDebugger ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="6ce16-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6ce16-105">Remarks</span></span>  
 <span data-ttu-id="6ce16-106">El `ThreadIsBlockingForDebugger` siempre se llamará el método en un subproceso en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="6ce16-106">The `ThreadIsBlockingForDebugger` method will always be called on a runtime thread.</span></span>  
  
 <span data-ttu-id="6ce16-107">El `ThreadIsBlockingForDebugger` método proporciona al host una oportunidad de realizar otra acción mientras el subproceso se bloquea.</span><span class="sxs-lookup"><span data-stu-id="6ce16-107">The `ThreadIsBlockingForDebugger` method gives the host an opportunity to perform another action while the thread blocks.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6ce16-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6ce16-108">Requirements</span></span>  
 <span data-ttu-id="6ce16-109">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6ce16-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6ce16-110">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6ce16-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6ce16-111">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6ce16-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6ce16-112">**Versiones de .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6ce16-112">**NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ce16-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="6ce16-113">See Also</span></span>  
 [<span data-ttu-id="6ce16-114">IDebuggerThreadControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6ce16-114">IDebuggerThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md)
