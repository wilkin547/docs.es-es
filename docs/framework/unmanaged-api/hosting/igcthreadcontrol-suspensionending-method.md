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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d77380e35d8f5eee1e50b1030493e0b17cbadfba
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54713293"
---
# <a name="igcthreadcontrolsuspensionending-method"></a><span data-ttu-id="e9baf-102">IGCThreadControl::SuspensionEnding (Método)</span><span class="sxs-lookup"><span data-stu-id="e9baf-102">IGCThreadControl::SuspensionEnding Method</span></span>
<span data-ttu-id="e9baf-103">Notifica al host que el tiempo de ejecución es reanudar subprocesos después de una recolección de elementos u otra suspensión.</span><span class="sxs-lookup"><span data-stu-id="e9baf-103">Notifies the host that the runtime is resuming threads after a garbage collection or other suspension.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9baf-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e9baf-104">Syntax</span></span>  
  
```  
HRESULT SuspensionEnding (  
    [in] DWORD Generation  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e9baf-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e9baf-105">Parameters</span></span>  
 `Generation`  
 <span data-ttu-id="e9baf-106">[in] La generación en el que se ha realizado una recolección de elementos.</span><span class="sxs-lookup"><span data-stu-id="e9baf-106">[in] The generation on which a garbage collection has been performed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e9baf-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e9baf-107">Remarks</span></span>  
 <span data-ttu-id="e9baf-108">No volver a programar los subprocesos durante la `SuspensionEnding` devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="e9baf-108">Do not reschedule any threads during the `SuspensionEnding` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9baf-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e9baf-109">Requirements</span></span>  
 <span data-ttu-id="e9baf-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e9baf-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9baf-111">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e9baf-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e9baf-112">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e9baf-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e9baf-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9baf-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9baf-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="e9baf-114">See also</span></span>
- [<span data-ttu-id="e9baf-115">IGCThreadControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e9baf-115">IGCThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md)
