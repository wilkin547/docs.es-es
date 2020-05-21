---
title: ICorThreadpool::CorGetMaxThreads (Método)
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorGetMaxThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorGetMaxThreads
helpviewer_keywords:
- CorGetMaxThreads method [.NET Framework hosting]
- ICorThreadpool::CorGetMaxThreads method [.NET Framework hosting]
ms.assetid: 2861533a-cda0-47b3-b716-0d363505289b
topic_type:
- apiref
ms.openlocfilehash: 46ffdb21c1f3b501cc28afffc224349887af5644
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762757"
---
# <a name="icorthreadpoolcorgetmaxthreads-method"></a><span data-ttu-id="9206b-102">ICorThreadpool::CorGetMaxThreads (Método)</span><span class="sxs-lookup"><span data-stu-id="9206b-102">ICorThreadpool::CorGetMaxThreads Method</span></span>
<span data-ttu-id="9206b-103">Este método es compatible con la infraestructura de .NET Framework y no está diseñado para utilizarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="9206b-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9206b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9206b-104">Syntax</span></span>  
  
```cpp  
HRESULT CorGetMaxThreads (  
    [out] DWORD *MaxWorkerThreads,  
    [out] DWORD *MaxIOCompletionThreads  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="9206b-105">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9206b-105">Requirements</span></span>  
 <span data-ttu-id="9206b-106">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9206b-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9206b-107">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="9206b-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9206b-108">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="9206b-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9206b-109">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9206b-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9206b-110">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="9206b-110">See also</span></span>

- [<span data-ttu-id="9206b-111">ICorThreadpool (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9206b-111">ICorThreadpool Interface</span></span>](icorthreadpool-interface.md)
