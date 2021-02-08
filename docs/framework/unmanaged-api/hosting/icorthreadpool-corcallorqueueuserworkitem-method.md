---
description: 'Más información sobre: ICorThreadpool:: CorCallOrQueueUserWorkItem ((método)'
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
ms.openlocfilehash: 630afab4eac94d0361b0c83c962ff6e7d59be42d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789585"
---
# <a name="icorthreadpoolcorcallorqueueuserworkitem-method"></a><span data-ttu-id="b43b5-103">ICorThreadpool::CorCallOrQueueUserWorkItem (Método)</span><span class="sxs-lookup"><span data-stu-id="b43b5-103">ICorThreadpool::CorCallOrQueueUserWorkItem Method</span></span>

<span data-ttu-id="b43b5-104">Este método es compatible con la infraestructura de .NET Framework y no está diseñado para utilizarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="b43b5-104">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b43b5-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b43b5-105">Syntax</span></span>  
  
```cpp  
HRESULT CorCallOrQueueUserWorkItem (  
    [in] LPTHREAD_START_ROUTINE Function,  
    [in] PVOID                  Context,  
    [out] BOOL*                 result  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="b43b5-106">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b43b5-106">Requirements</span></span>  

 <span data-ttu-id="b43b5-107">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b43b5-107">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b43b5-108">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="b43b5-108">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b43b5-109">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b43b5-109">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b43b5-110">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b43b5-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b43b5-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="b43b5-111">See also</span></span>

- [<span data-ttu-id="b43b5-112">ICorThreadpool (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b43b5-112">ICorThreadpool Interface</span></span>](icorthreadpool-interface.md)
