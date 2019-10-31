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
ms.openlocfilehash: e20ea6addc1ae3f99b4b3d65f532e0128ac160b3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134971"
---
# <a name="igchostcollect-method"></a><span data-ttu-id="8e5a2-102">IGCHost::Collect (Método)</span><span class="sxs-lookup"><span data-stu-id="8e5a2-102">IGCHost::Collect Method</span></span>
<span data-ttu-id="8e5a2-103">Obliga a que se produzca una colección para la generación dada, independientemente del estado de la recolección de elementos no utilizados actual.</span><span class="sxs-lookup"><span data-stu-id="8e5a2-103">Forces a collection to occur for the given generation, regardless of the state of the current garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e5a2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8e5a2-104">Syntax</span></span>  
  
```cpp  
HRESULT Collect (  
    [in] LONG Generation  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8e5a2-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8e5a2-105">Parameters</span></span>  
 `Generation`  
 <span data-ttu-id="8e5a2-106">de Generación en la que se va a realizar la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="8e5a2-106">[in] The generation on which to perform the garbage collection.</span></span> <span data-ttu-id="8e5a2-107">Un valor de-1 indica que todas las generaciones se someterán a una recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="8e5a2-107">A value of -1 indicates that all generations will undergo a garbage collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8e5a2-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8e5a2-108">Requirements</span></span>  
 <span data-ttu-id="8e5a2-109">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8e5a2-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8e5a2-110">**Encabezado:** GCHost. idl, GCHost. h</span><span class="sxs-lookup"><span data-stu-id="8e5a2-110">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="8e5a2-111">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="8e5a2-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8e5a2-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8e5a2-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e5a2-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="8e5a2-113">See also</span></span>

- [<span data-ttu-id="8e5a2-114">IGCHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8e5a2-114">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
