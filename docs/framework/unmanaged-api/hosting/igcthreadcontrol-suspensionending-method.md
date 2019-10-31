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
ms.openlocfilehash: 8d8efccde56d8d37a75b1d9bbec706411c6b1f45
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134783"
---
# <a name="igcthreadcontrolsuspensionending-method"></a><span data-ttu-id="25116-102">IGCThreadControl::SuspensionEnding (Método)</span><span class="sxs-lookup"><span data-stu-id="25116-102">IGCThreadControl::SuspensionEnding Method</span></span>
<span data-ttu-id="25116-103">Notifica al host que el Runtime está reanudando los subprocesos después de una recolección de elementos no utilizados u otra suspensión.</span><span class="sxs-lookup"><span data-stu-id="25116-103">Notifies the host that the runtime is resuming threads after a garbage collection or other suspension.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25116-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="25116-104">Syntax</span></span>  
  
```cpp  
HRESULT SuspensionEnding (  
    [in] DWORD Generation  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="25116-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="25116-105">Parameters</span></span>  
 `Generation`  
 <span data-ttu-id="25116-106">de La generación en la que se ha realizado la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="25116-106">[in] The generation on which a garbage collection has been performed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="25116-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="25116-107">Remarks</span></span>  
 <span data-ttu-id="25116-108">No vuelva a programar ningún subproceso durante la devolución de llamada de `SuspensionEnding`.</span><span class="sxs-lookup"><span data-stu-id="25116-108">Do not reschedule any threads during the `SuspensionEnding` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="25116-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="25116-109">Requirements</span></span>  
 <span data-ttu-id="25116-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="25116-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="25116-111">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="25116-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="25116-112">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="25116-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="25116-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="25116-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25116-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="25116-114">See also</span></span>

- [<span data-ttu-id="25116-115">IGCThreadControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="25116-115">IGCThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md)
