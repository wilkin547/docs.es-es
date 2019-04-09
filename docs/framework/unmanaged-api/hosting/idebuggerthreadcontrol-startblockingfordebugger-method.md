---
title: IDebuggerThreadControl::StartBlockingForDebugger (Método)
ms.date: 03/30/2017
api_name:
- IDebuggerThreadControl.StartBlockingForDebugger
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- StartBlockingForDebugger
helpviewer_keywords:
- IDebuggerThreadControl::StartBlockingForDebugger method [.NET Framework hosting]
- StartBlockingForDebugger method [.NET Framework hosting]
ms.assetid: 5c8f11b4-35d3-4c39-9bbd-58b896ba5ba6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dfc94c2de1a14842cc017e5c4ef6023154c20f2a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59194037"
---
# <a name="idebuggerthreadcontrolstartblockingfordebugger-method"></a><span data-ttu-id="f2cc0-102">IDebuggerThreadControl::StartBlockingForDebugger (Método)</span><span class="sxs-lookup"><span data-stu-id="f2cc0-102">IDebuggerThreadControl::StartBlockingForDebugger Method</span></span>
<span data-ttu-id="f2cc0-103">Notifica al host que los servicios de depuración están a punto de comenzar a bloquear todos los subprocesos.</span><span class="sxs-lookup"><span data-stu-id="f2cc0-103">Notifies the host that the debugging services are about to start blocking all threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2cc0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f2cc0-104">Syntax</span></span>  
  
```  
HRESULT StartBlockingForDebugger (  
    [in] DWORD dwUnused  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f2cc0-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f2cc0-105">Parameters</span></span>  
 `dwUnused`  
 <span data-ttu-id="f2cc0-106">[in] Reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="f2cc0-106">[in] Reserved for future use.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f2cc0-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f2cc0-107">Remarks</span></span>  
 <span data-ttu-id="f2cc0-108">El `StartBlockingForDebugger` podría se llama al método en un subproceso en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="f2cc0-108">The `StartBlockingForDebugger` method could be called on a runtime thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2cc0-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f2cc0-109">Requirements</span></span>  
 <span data-ttu-id="f2cc0-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f2cc0-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2cc0-111">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f2cc0-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f2cc0-112">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f2cc0-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="f2cc0-113">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="f2cc0-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f2cc0-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="f2cc0-114">See also</span></span>

- [<span data-ttu-id="f2cc0-115">IDebuggerThreadControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f2cc0-115">IDebuggerThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md)
