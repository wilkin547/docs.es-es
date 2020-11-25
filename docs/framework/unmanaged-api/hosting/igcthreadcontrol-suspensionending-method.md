---
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
ms.openlocfilehash: 4638672b1d64a9ea07618212cc514d00996470eb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721678"
---
# <a name="igcthreadcontrolsuspensionending-method"></a><span data-ttu-id="07cc2-102">IGCThreadControl::SuspensionEnding (Método)</span><span class="sxs-lookup"><span data-stu-id="07cc2-102">IGCThreadControl::SuspensionEnding Method</span></span>

<span data-ttu-id="07cc2-103">Notifica al host que el Runtime está reanudando los subprocesos después de una recolección de elementos no utilizados u otra suspensión.</span><span class="sxs-lookup"><span data-stu-id="07cc2-103">Notifies the host that the runtime is resuming threads after a garbage collection or other suspension.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07cc2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="07cc2-104">Syntax</span></span>  
  
```cpp  
HRESULT SuspensionEnding (  
    [in] DWORD Generation  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="07cc2-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="07cc2-105">Parameters</span></span>  

 `Generation`  
 <span data-ttu-id="07cc2-106">de La generación en la que se ha realizado la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="07cc2-106">[in] The generation on which a garbage collection has been performed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="07cc2-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="07cc2-107">Remarks</span></span>  

 <span data-ttu-id="07cc2-108">No vuelva a programar los subprocesos durante la `SuspensionEnding` devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="07cc2-108">Do not reschedule any threads during the `SuspensionEnding` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="07cc2-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="07cc2-109">Requirements</span></span>  

 <span data-ttu-id="07cc2-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="07cc2-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="07cc2-111">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="07cc2-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="07cc2-112">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="07cc2-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="07cc2-113">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="07cc2-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07cc2-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="07cc2-114">See also</span></span>

- [<span data-ttu-id="07cc2-115">IGCThreadControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="07cc2-115">IGCThreadControl Interface</span></span>](igcthreadcontrol-interface.md)
