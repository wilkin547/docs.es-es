---
description: 'Más información sobre: ICorThreadpool:: Corgetmaxthreads ((método)'
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
ms.openlocfilehash: 44de36a7ff3e086ab9389049137c66697af11af3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99636486"
---
# <a name="icorthreadpoolcorgetmaxthreads-method"></a><span data-ttu-id="2259b-103">ICorThreadpool::CorGetMaxThreads (Método)</span><span class="sxs-lookup"><span data-stu-id="2259b-103">ICorThreadpool::CorGetMaxThreads Method</span></span>

<span data-ttu-id="2259b-104">Este método es compatible con la infraestructura de .NET Framework y no está diseñado para utilizarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="2259b-104">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2259b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2259b-105">Syntax</span></span>  
  
```cpp  
HRESULT CorGetMaxThreads (  
    [out] DWORD *MaxWorkerThreads,  
    [out] DWORD *MaxIOCompletionThreads  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="2259b-106">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2259b-106">Requirements</span></span>  

 <span data-ttu-id="2259b-107">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2259b-107">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2259b-108">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="2259b-108">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2259b-109">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2259b-109">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2259b-110">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2259b-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2259b-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="2259b-111">See also</span></span>

- [<span data-ttu-id="2259b-112">ICorThreadpool (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="2259b-112">ICorThreadpool Interface</span></span>](icorthreadpool-interface.md)
