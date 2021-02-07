---
description: 'Más información sobre: ICorThreadpool:: Corgetavailablethreads ((método)'
title: ICorThreadpool::CorGetAvailableThreads (Método)
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorGetAvailableThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorGetAvailableThreads
helpviewer_keywords:
- CorGetAvailableThreads method [.NET Framework hosting]
- ICorThreadpool::CorGetAvailableThreads method [.NET Framework hosting]
ms.assetid: 0b09b750-0b86-4ba4-9621-041857cfe8ba
topic_type:
- apiref
ms.openlocfilehash: ca6b476a00ce781e10c0708f5132b398b4c85398
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99760594"
---
# <a name="icorthreadpoolcorgetavailablethreads-method"></a><span data-ttu-id="a1978-103">ICorThreadpool::CorGetAvailableThreads (Método)</span><span class="sxs-lookup"><span data-stu-id="a1978-103">ICorThreadpool::CorGetAvailableThreads Method</span></span>

<span data-ttu-id="a1978-104">Este método es compatible con la infraestructura de .NET Framework y no está diseñado para utilizarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="a1978-104">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1978-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a1978-105">Syntax</span></span>  
  
```cpp  
HRESULT CorGetAvailableThreads (  
    [out] DWORD *AvailableWorkerThreads,  
    [out] DWORD *AvailableIOCompletionThreads  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="a1978-106">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a1978-106">Requirements</span></span>  

 <span data-ttu-id="a1978-107">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a1978-107">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1978-108">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="a1978-108">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a1978-109">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a1978-109">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a1978-110">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a1978-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1978-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="a1978-111">See also</span></span>

- [<span data-ttu-id="a1978-112">ICorThreadpool (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a1978-112">ICorThreadpool Interface</span></span>](icorthreadpool-interface.md)
