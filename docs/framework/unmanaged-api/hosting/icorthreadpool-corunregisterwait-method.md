---
description: 'Más información sobre: ICorThreadpool:: Corunregisterwait ((método)'
title: ICorThreadpool::CorUnregisterWait (Método)
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorUnregisterWait
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorUnregisterWait
helpviewer_keywords:
- CorUnregisterWait method [.NET Framework hosting]
- ICorThreadpool::CorUnregisterWait method [.NET Framework hosting]
ms.assetid: 42c933f1-30a8-4011-bdea-e117f3c3265e
topic_type:
- apiref
ms.openlocfilehash: 61b6c7a1fa8459ddd173d2857cff982f353afc31
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789533"
---
# <a name="icorthreadpoolcorunregisterwait-method"></a><span data-ttu-id="de0ab-103">ICorThreadpool::CorUnregisterWait (Método)</span><span class="sxs-lookup"><span data-stu-id="de0ab-103">ICorThreadpool::CorUnregisterWait Method</span></span>

<span data-ttu-id="de0ab-104">Este método es compatible con la infraestructura de .NET Framework y no está diseñado para utilizarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="de0ab-104">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de0ab-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="de0ab-105">Syntax</span></span>  
  
```cpp  
HRESULT CorUnregisterWait (  
    [in] HANDLE hWaitObject,  
    [in] HANDLE CompletionEvent,  
    [out] BOOL* result  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="de0ab-106">Requisitos</span><span class="sxs-lookup"><span data-stu-id="de0ab-106">Requirements</span></span>  

 <span data-ttu-id="de0ab-107">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="de0ab-107">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de0ab-108">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="de0ab-108">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="de0ab-109">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="de0ab-109">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="de0ab-110">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="de0ab-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de0ab-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="de0ab-111">See also</span></span>

- [<span data-ttu-id="de0ab-112">ICorThreadpool (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="de0ab-112">ICorThreadpool Interface</span></span>](icorthreadpool-interface.md)
