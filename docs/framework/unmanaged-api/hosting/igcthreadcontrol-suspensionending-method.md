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
ms.openlocfilehash: d0986645a8ce4076c27f39f2ae8004ef20bb4bdb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33437757"
---
# <a name="igcthreadcontrolsuspensionending-method"></a><span data-ttu-id="55b1b-102">IGCThreadControl::SuspensionEnding (Método)</span><span class="sxs-lookup"><span data-stu-id="55b1b-102">IGCThreadControl::SuspensionEnding Method</span></span>
<span data-ttu-id="55b1b-103">Notifica al host que el runtime está reanudando los subprocesos después de una colección de elementos no utilizados u otra suspensión.</span><span class="sxs-lookup"><span data-stu-id="55b1b-103">Notifies the host that the runtime is resuming threads after a garbage collection or other suspension.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55b1b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="55b1b-104">Syntax</span></span>  
  
```  
HRESULT SuspensionEnding (  
    [in] DWORD Generation  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="55b1b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="55b1b-105">Parameters</span></span>  
 `Generation`  
 <span data-ttu-id="55b1b-106">[in] La generación en la que se ha realizado una recolección de elementos.</span><span class="sxs-lookup"><span data-stu-id="55b1b-106">[in] The generation on which a garbage collection has been performed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="55b1b-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="55b1b-107">Remarks</span></span>  
 <span data-ttu-id="55b1b-108">No volver a programar todos los subprocesos durante la `SuspensionEnding` devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="55b1b-108">Do not reschedule any threads during the `SuspensionEnding` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55b1b-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="55b1b-109">Requirements</span></span>  
 <span data-ttu-id="55b1b-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="55b1b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="55b1b-111">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="55b1b-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="55b1b-112">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="55b1b-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="55b1b-113">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="55b1b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55b1b-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="55b1b-114">See Also</span></span>  
 [<span data-ttu-id="55b1b-115">IGCThreadControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="55b1b-115">IGCThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md)
