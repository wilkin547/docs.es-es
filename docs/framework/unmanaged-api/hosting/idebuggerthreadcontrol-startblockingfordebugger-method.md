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
ms.openlocfilehash: 1e0cb52a6b9f03209256e5398415b4ec632fb5e5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95705514"
---
# <a name="idebuggerthreadcontrolstartblockingfordebugger-method"></a><span data-ttu-id="f68e4-102">IDebuggerThreadControl::StartBlockingForDebugger (Método)</span><span class="sxs-lookup"><span data-stu-id="f68e4-102">IDebuggerThreadControl::StartBlockingForDebugger Method</span></span>

<span data-ttu-id="f68e4-103">Notifica al host que los servicios de depuración están a punto de iniciar el bloqueo de todos los subprocesos.</span><span class="sxs-lookup"><span data-stu-id="f68e4-103">Notifies the host that the debugging services are about to start blocking all threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f68e4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f68e4-104">Syntax</span></span>  
  
```cpp  
HRESULT StartBlockingForDebugger (  
    [in] DWORD dwUnused  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f68e4-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f68e4-105">Parameters</span></span>  

 `dwUnused`  
 <span data-ttu-id="f68e4-106">[in] Reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="f68e4-106">[in] Reserved for future use.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f68e4-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f68e4-107">Remarks</span></span>  

 <span data-ttu-id="f68e4-108">`StartBlockingForDebugger`Se podría llamar al método en un subproceso en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="f68e4-108">The `StartBlockingForDebugger` method could be called on a runtime thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f68e4-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f68e4-109">Requirements</span></span>  

 <span data-ttu-id="f68e4-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f68e4-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f68e4-111">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="f68e4-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f68e4-112">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f68e4-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f68e4-113">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f68e4-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f68e4-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f68e4-114">See also</span></span>

- [<span data-ttu-id="f68e4-115">IDebuggerThreadControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f68e4-115">IDebuggerThreadControl Interface</span></span>](idebuggerthreadcontrol-interface.md)
