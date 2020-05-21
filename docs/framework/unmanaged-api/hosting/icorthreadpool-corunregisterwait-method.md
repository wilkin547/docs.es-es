---
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
ms.openlocfilehash: e3655f77a94da25f65bada2cd4067ef53550e778
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762024"
---
# <a name="icorthreadpoolcorunregisterwait-method"></a><span data-ttu-id="40aca-102">ICorThreadpool::CorUnregisterWait (Método)</span><span class="sxs-lookup"><span data-stu-id="40aca-102">ICorThreadpool::CorUnregisterWait Method</span></span>
<span data-ttu-id="40aca-103">Este método es compatible con la infraestructura de .NET Framework y no está diseñado para utilizarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="40aca-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40aca-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="40aca-104">Syntax</span></span>  
  
```cpp  
HRESULT CorUnregisterWait (  
    [in] HANDLE hWaitObject,  
    [in] HANDLE CompletionEvent,  
    [out] BOOL* result  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="40aca-105">Requisitos</span><span class="sxs-lookup"><span data-stu-id="40aca-105">Requirements</span></span>  
 <span data-ttu-id="40aca-106">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="40aca-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40aca-107">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="40aca-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="40aca-108">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="40aca-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="40aca-109">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40aca-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40aca-110">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="40aca-110">See also</span></span>

- [<span data-ttu-id="40aca-111">ICorThreadpool (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="40aca-111">ICorThreadpool Interface</span></span>](icorthreadpool-interface.md)
