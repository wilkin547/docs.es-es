---
description: 'Más información sobre: IGCThreadControl:: Suspensionending ((método)'
title: IGCThreadControl::SuspensionEnding (Método)
ms.date: 03/30/2017
api_name:
- IGCThreadControl.SuspensionEnding
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SuspensionEnding
helpviewer_keywords:
- IGCThreadControl::SuspensionEnding method [.NET Framework hosting]
- SuspensionEnding method, IGCThreadControl interface [.NET Framework hosting]
ms.assetid: 70814265-c734-4ddc-9502-fe8b28d2b414
topic_type:
- apiref
ms.openlocfilehash: 5ff889f45ea3664312060f373907e65c367276f1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99709274"
---
# <a name="igcthreadcontrolsuspensionending-method"></a><span data-ttu-id="14361-103">IGCThreadControl::SuspensionEnding (Método)</span><span class="sxs-lookup"><span data-stu-id="14361-103">IGCThreadControl::SuspensionEnding Method</span></span>

<span data-ttu-id="14361-104">Notifica al host que el Runtime está reanudando los subprocesos después de una recolección de elementos no utilizados u otra suspensión.</span><span class="sxs-lookup"><span data-stu-id="14361-104">Notifies the host that the runtime is resuming threads after a garbage collection or other suspension.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14361-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="14361-105">Syntax</span></span>  
  
```cpp  
HRESULT SuspensionEnding (  
    [in] DWORD Generation  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="14361-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="14361-106">Parameters</span></span>  

 `Generation`  
 <span data-ttu-id="14361-107">de La generación en la que se ha realizado la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="14361-107">[in] The generation on which a garbage collection has been performed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="14361-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="14361-108">Remarks</span></span>  

 <span data-ttu-id="14361-109">No vuelva a programar los subprocesos durante la `SuspensionEnding` devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="14361-109">Do not reschedule any threads during the `SuspensionEnding` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="14361-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="14361-110">Requirements</span></span>  

 <span data-ttu-id="14361-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="14361-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="14361-112">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="14361-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="14361-113">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="14361-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="14361-114">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="14361-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14361-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="14361-115">See also</span></span>

- [<span data-ttu-id="14361-116">IGCThreadControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="14361-116">IGCThreadControl Interface</span></span>](igcthreadcontrol-interface.md)
