---
title: IGCHost::Collect (Método)
ms.date: 03/30/2017
api_name:
- IGCHost.Collect
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- Collect
helpviewer_keywords:
- Collect method, IGCHost interface [.NET Framework hosting]
- IGCHost::Collect method [.NET Framework hosting]
ms.assetid: fc7d9448-3186-494d-9f0d-ea39717e9a82
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 973062e93e4964da0a21c14c17e0ce1960029ebd
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57489077"
---
# <a name="igchostcollect-method"></a><span data-ttu-id="2ecfe-102">IGCHost::Collect (Método)</span><span class="sxs-lookup"><span data-stu-id="2ecfe-102">IGCHost::Collect Method</span></span>
<span data-ttu-id="2ecfe-103">Fuerza una recolección que se produzca la generación determinada, independientemente del estado de la recolección de elementos actual.</span><span class="sxs-lookup"><span data-stu-id="2ecfe-103">Forces a collection to occur for the given generation, regardless of the state of the current garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ecfe-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2ecfe-104">Syntax</span></span>  
  
```  
HRESULT Collect (  
    [in] LONG Generation  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2ecfe-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2ecfe-105">Parameters</span></span>  
 `Generation`  
 <span data-ttu-id="2ecfe-106">[in] La generación en la que se va a realizar la recolección de elementos.</span><span class="sxs-lookup"><span data-stu-id="2ecfe-106">[in] The generation on which to perform the garbage collection.</span></span> <span data-ttu-id="2ecfe-107">El valor -1 indica que todas las generaciones se someterá a una colección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="2ecfe-107">A value of -1 indicates that all generations will undergo a garbage collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ecfe-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2ecfe-108">Requirements</span></span>  
 <span data-ttu-id="2ecfe-109">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2ecfe-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ecfe-110">**Encabezado**: GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="2ecfe-110">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="2ecfe-111">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2ecfe-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2ecfe-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ecfe-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ecfe-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="2ecfe-113">See also</span></span>
- [<span data-ttu-id="2ecfe-114">IGCHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2ecfe-114">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
