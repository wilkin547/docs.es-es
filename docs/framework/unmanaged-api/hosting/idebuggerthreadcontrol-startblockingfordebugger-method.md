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
ms.openlocfilehash: 878dba37728734a777d2f95226b60bfbe9aae16a
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/22/2020
ms.locfileid: "83805268"
---
# <a name="idebuggerthreadcontrolstartblockingfordebugger-method"></a><span data-ttu-id="589f9-102">IDebuggerThreadControl::StartBlockingForDebugger (Método)</span><span class="sxs-lookup"><span data-stu-id="589f9-102">IDebuggerThreadControl::StartBlockingForDebugger Method</span></span>
<span data-ttu-id="589f9-103">Notifica al host que los servicios de depuración están a punto de iniciar el bloqueo de todos los subprocesos.</span><span class="sxs-lookup"><span data-stu-id="589f9-103">Notifies the host that the debugging services are about to start blocking all threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="589f9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="589f9-104">Syntax</span></span>  
  
```cpp  
HRESULT StartBlockingForDebugger (  
    [in] DWORD dwUnused  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="589f9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="589f9-105">Parameters</span></span>  
 `dwUnused`  
 <span data-ttu-id="589f9-106">[in] Reservado para uso futuro.</span><span class="sxs-lookup"><span data-stu-id="589f9-106">[in] Reserved for future use.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="589f9-107">Observaciones</span><span class="sxs-lookup"><span data-stu-id="589f9-107">Remarks</span></span>  
 <span data-ttu-id="589f9-108">`StartBlockingForDebugger`Se podría llamar al método en un subproceso en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="589f9-108">The `StartBlockingForDebugger` method could be called on a runtime thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="589f9-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="589f9-109">Requirements</span></span>  
 <span data-ttu-id="589f9-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="589f9-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="589f9-111">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="589f9-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="589f9-112">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="589f9-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="589f9-113">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="589f9-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="589f9-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="589f9-114">See also</span></span>

- [<span data-ttu-id="589f9-115">IDebuggerThreadControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="589f9-115">IDebuggerThreadControl Interface</span></span>](idebuggerthreadcontrol-interface.md)
