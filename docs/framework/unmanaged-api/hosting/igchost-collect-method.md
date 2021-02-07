---
description: 'Más información sobre: IGCHost:: collect (método)'
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
ms.openlocfilehash: b4c249e07709dc443ae7dd6c6a5bfd206b7f1caa
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99709703"
---
# <a name="igchostcollect-method"></a><span data-ttu-id="a9fc8-103">IGCHost::Collect (Método)</span><span class="sxs-lookup"><span data-stu-id="a9fc8-103">IGCHost::Collect Method</span></span>

<span data-ttu-id="a9fc8-104">Obliga a que se produzca una colección para la generación dada, independientemente del estado de la recolección de elementos no utilizados actual.</span><span class="sxs-lookup"><span data-stu-id="a9fc8-104">Forces a collection to occur for the given generation, regardless of the state of the current garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9fc8-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a9fc8-105">Syntax</span></span>  
  
```cpp  
HRESULT Collect (  
    [in] LONG Generation  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a9fc8-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a9fc8-106">Parameters</span></span>  

 `Generation`  
 <span data-ttu-id="a9fc8-107">de Generación en la que se va a realizar la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="a9fc8-107">[in] The generation on which to perform the garbage collection.</span></span> <span data-ttu-id="a9fc8-108">Un valor de-1 indica que todas las generaciones se someterán a una recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="a9fc8-108">A value of -1 indicates that all generations will undergo a garbage collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a9fc8-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a9fc8-109">Requirements</span></span>  

 <span data-ttu-id="a9fc8-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a9fc8-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a9fc8-111">**Encabezado:** GCHost. idl, GCHost. h</span><span class="sxs-lookup"><span data-stu-id="a9fc8-111">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="a9fc8-112">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a9fc8-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a9fc8-113">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a9fc8-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9fc8-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="a9fc8-114">See also</span></span>

- [<span data-ttu-id="a9fc8-115">IGCHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a9fc8-115">IGCHost Interface</span></span>](igchost-interface.md)
