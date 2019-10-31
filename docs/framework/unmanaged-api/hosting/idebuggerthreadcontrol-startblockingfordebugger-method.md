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
ms.openlocfilehash: 72f7bee79e74c69acff90861ceada8a91afe2157
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134911"
---
# <a name="idebuggerthreadcontrolstartblockingfordebugger-method"></a><span data-ttu-id="cf73a-102">IDebuggerThreadControl::StartBlockingForDebugger (Método)</span><span class="sxs-lookup"><span data-stu-id="cf73a-102">IDebuggerThreadControl::StartBlockingForDebugger Method</span></span>
<span data-ttu-id="cf73a-103">Notifica al host que los servicios de depuración están a punto de iniciar el bloqueo de todos los subprocesos.</span><span class="sxs-lookup"><span data-stu-id="cf73a-103">Notifies the host that the debugging services are about to start blocking all threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf73a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cf73a-104">Syntax</span></span>  
  
```cpp  
HRESULT StartBlockingForDebugger (  
    [in] DWORD dwUnused  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cf73a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cf73a-105">Parameters</span></span>  
 `dwUnused`  
 <span data-ttu-id="cf73a-106">de Reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="cf73a-106">[in] Reserved for future use.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cf73a-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cf73a-107">Remarks</span></span>  
 <span data-ttu-id="cf73a-108">Se puede llamar al método `StartBlockingForDebugger` en un subproceso en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="cf73a-108">The `StartBlockingForDebugger` method could be called on a runtime thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cf73a-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cf73a-109">Requirements</span></span>  
 <span data-ttu-id="cf73a-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cf73a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf73a-111">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="cf73a-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cf73a-112">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="cf73a-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cf73a-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf73a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf73a-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="cf73a-114">See also</span></span>

- [<span data-ttu-id="cf73a-115">IDebuggerThreadControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="cf73a-115">IDebuggerThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md)
