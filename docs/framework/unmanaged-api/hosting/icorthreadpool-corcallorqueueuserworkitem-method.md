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
ms.openlocfilehash: 6046ff8486b356ca781a42a34a5a18bdae8c4c73
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95690023"
---
# <a name="icorthreadpoolcorcallorqueueuserworkitem-method"></a><span data-ttu-id="24edb-102">ICorThreadpool::CorCallOrQueueUserWorkItem (Método)</span><span class="sxs-lookup"><span data-stu-id="24edb-102">ICorThreadpool::CorCallOrQueueUserWorkItem Method</span></span>

<span data-ttu-id="24edb-103">Este método es compatible con la infraestructura de .NET Framework y no está diseñado para utilizarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="24edb-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24edb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="24edb-104">Syntax</span></span>  
  
```cpp  
HRESULT CorCallOrQueueUserWorkItem (  
    [in] LPTHREAD_START_ROUTINE Function,  
    [in] PVOID                  Context,  
    [out] BOOL*                 result  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="24edb-105">Requisitos</span><span class="sxs-lookup"><span data-stu-id="24edb-105">Requirements</span></span>  

 <span data-ttu-id="24edb-106">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="24edb-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="24edb-107">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="24edb-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="24edb-108">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="24edb-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="24edb-109">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="24edb-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24edb-110">Consulte también</span><span class="sxs-lookup"><span data-stu-id="24edb-110">See also</span></span>

- [<span data-ttu-id="24edb-111">ICorThreadpool (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="24edb-111">ICorThreadpool Interface</span></span>](icorthreadpool-interface.md)
