---
title: ICorThreadpool::CorChangeTimer (Método)
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorChangeTimer
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorChangeTimer
helpviewer_keywords:
- CorChangeTimer method [.NET Framework hosting]
- ICorThreadpool::CorChangeTimer method [.NET Framework hosting]
ms.assetid: 82b03a59-5a87-43ed-9b75-e04b256e1a46
topic_type:
- apiref
ms.openlocfilehash: 3d119c8355f5b58a05f1ea1695969b2e98682c72
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95690244"
---
# <a name="icorthreadpoolcorchangetimer-method"></a><span data-ttu-id="1c4dc-102">ICorThreadpool::CorChangeTimer (Método)</span><span class="sxs-lookup"><span data-stu-id="1c4dc-102">ICorThreadpool::CorChangeTimer Method</span></span>

<span data-ttu-id="1c4dc-103">Este método es compatible con la infraestructura de .NET Framework y no está diseñado para utilizarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="1c4dc-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c4dc-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1c4dc-104">Syntax</span></span>  
  
```cpp  
HRESULT CorChangeTimer (  
    [in]  HANDLE Timer,
    [in]  ULONG  DueTime,
    [in]  ULONG  Period,  
    [out] BOOL*  result  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="1c4dc-105">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1c4dc-105">Requirements</span></span>  

 <span data-ttu-id="1c4dc-106">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1c4dc-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c4dc-107">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="1c4dc-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1c4dc-108">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1c4dc-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1c4dc-109">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c4dc-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c4dc-110">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1c4dc-110">See also</span></span>

- [<span data-ttu-id="1c4dc-111">ICorThreadpool (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1c4dc-111">ICorThreadpool Interface</span></span>](icorthreadpool-interface.md)
