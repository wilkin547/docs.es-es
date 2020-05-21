---
title: ICorThreadpool::CorCallOrQueueUserWorkItem (Método)
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorCallOrQueueUserWorkItem
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorCallOrQueueUserWorkItem
helpviewer_keywords:
- ICorThreadpool::CorCallOrQueueUserWorkItem method [.NET Framework hosting]
- CorCallOrQueueUserWorkItem method [.NET Framework hosting]
ms.assetid: a2081223-84ca-4331-a8d3-9352f422f3e7
topic_type:
- apiref
ms.openlocfilehash: a2d2d6307136f0f8983e409d9f17fbcae1c55705
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/21/2020
ms.locfileid: "83760358"
---
# <a name="icorthreadpoolcorcallorqueueuserworkitem-method"></a><span data-ttu-id="744fd-102">ICorThreadpool::CorCallOrQueueUserWorkItem (Método)</span><span class="sxs-lookup"><span data-stu-id="744fd-102">ICorThreadpool::CorCallOrQueueUserWorkItem Method</span></span>
<span data-ttu-id="744fd-103">Este método es compatible con la infraestructura de .NET Framework y no está diseñado para utilizarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="744fd-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="744fd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="744fd-104">Syntax</span></span>  
  
```cpp  
HRESULT CorCallOrQueueUserWorkItem (  
    [in] LPTHREAD_START_ROUTINE Function,  
    [in] PVOID                  Context,  
    [out] BOOL*                 result  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="744fd-105">Requisitos</span><span class="sxs-lookup"><span data-stu-id="744fd-105">Requirements</span></span>  
 <span data-ttu-id="744fd-106">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="744fd-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="744fd-107">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="744fd-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="744fd-108">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="744fd-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="744fd-109">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="744fd-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="744fd-110">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="744fd-110">See also</span></span>

- [<span data-ttu-id="744fd-111">ICorThreadpool (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="744fd-111">ICorThreadpool Interface</span></span>](icorthreadpool-interface.md)
