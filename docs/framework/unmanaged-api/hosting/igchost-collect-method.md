---
title: "IGCHost::Collect (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IGCHost.Collect
api_location: mscoree.dll
api_type: COM
f1_keywords: Collect
helpviewer_keywords:
- Collect method, IGCHost interface [.NET Framework hosting]
- IGCHost::Collect method [.NET Framework hosting]
ms.assetid: fc7d9448-3186-494d-9f0d-ea39717e9a82
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d97a988db48cc9bfdf8cf1e260c28e0169eb73f9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="igchostcollect-method"></a><span data-ttu-id="2e669-102">IGCHost::Collect (Método)</span><span class="sxs-lookup"><span data-stu-id="2e669-102">IGCHost::Collect Method</span></span>
<span data-ttu-id="2e669-103">Fuerza una recolección que se produzca la generación determinada, con independencia del estado de la colección de elementos no utilizados actual.</span><span class="sxs-lookup"><span data-stu-id="2e669-103">Forces a collection to occur for the given generation, regardless of the state of the current garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e669-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2e669-104">Syntax</span></span>  
  
```  
HRESULT Collect (  
    [in] LONG Generation  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2e669-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2e669-105">Parameters</span></span>  
 `Generation`  
 <span data-ttu-id="2e669-106">[in] La generación en la que se va a realizar la recolección de elementos.</span><span class="sxs-lookup"><span data-stu-id="2e669-106">[in] The generation on which to perform the garbage collection.</span></span> <span data-ttu-id="2e669-107">Un valor de -1 indica que todas las generaciones se someterán a una colección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="2e669-107">A value of -1 indicates that all generations will undergo a garbage collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2e669-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2e669-108">Requirements</span></span>  
 <span data-ttu-id="2e669-109">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2e669-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2e669-110">**Encabezado:** GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="2e669-110">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="2e669-111">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2e669-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2e669-112">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2e669-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e669-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="2e669-113">See Also</span></span>  
 [<span data-ttu-id="2e669-114">IGCHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2e669-114">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
