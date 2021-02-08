---
description: 'Más información sobre: ICorThreadpool:: CorSetMaxThreads ((método)'
title: ICorThreadpool::CorSetMaxThreads (Método)
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorSetMaxThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSetMaxThreads
helpviewer_keywords:
- ICorThreadpool::CorSetMaxThreads method [.NET Framework hosting]
- CorSetMaxThreads method [.NET Framework hosting]
ms.assetid: 4a846238-df4e-4060-ba3b-5173f6a51e85
topic_type:
- apiref
ms.openlocfilehash: 5eb55604b55da58ffb4b5b2806aa3e340274a6b2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789546"
---
# <a name="icorthreadpoolcorsetmaxthreads-method"></a><span data-ttu-id="ac624-103">ICorThreadpool::CorSetMaxThreads (Método)</span><span class="sxs-lookup"><span data-stu-id="ac624-103">ICorThreadpool::CorSetMaxThreads Method</span></span>

<span data-ttu-id="ac624-104">Este método es compatible con la infraestructura de .NET Framework y no está diseñado para utilizarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="ac624-104">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac624-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ac624-105">Syntax</span></span>  
  
```cpp  
HRESULT CorSetMaxThreads (  
    [in] DWORD MaxWorkerThreads,  
    [in] DWORD MaxIOCompletionThreads  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="ac624-106">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ac624-106">Requirements</span></span>  

 <span data-ttu-id="ac624-107">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ac624-107">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac624-108">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="ac624-108">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ac624-109">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ac624-109">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ac624-110">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ac624-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac624-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="ac624-111">See also</span></span>

- [<span data-ttu-id="ac624-112">ICorThreadpool (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ac624-112">ICorThreadpool Interface</span></span>](icorthreadpool-interface.md)
