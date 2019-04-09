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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: de4a61f188bc6419b52f168c8bbbf43ad91fa19e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59159606"
---
# <a name="icorthreadpoolcorchangetimer-method"></a><span data-ttu-id="91720-102">ICorThreadpool::CorChangeTimer (Método)</span><span class="sxs-lookup"><span data-stu-id="91720-102">ICorThreadpool::CorChangeTimer Method</span></span>
<span data-ttu-id="91720-103">Este método es compatible con la infraestructura de .NET Framework y no está diseñado para utilizarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="91720-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91720-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="91720-104">Syntax</span></span>  
  
```  
HRESULT CorChangeTimer (  
    [in]  HANDLE Timer,   
    [in]  ULONG  DueTime,   
    [in]  ULONG  Period,  
    [out] BOOL*  result  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="91720-105">Requisitos</span><span class="sxs-lookup"><span data-stu-id="91720-105">Requirements</span></span>  
 <span data-ttu-id="91720-106">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="91720-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="91720-107">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="91720-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="91720-108">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="91720-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="91720-109">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="91720-109">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="91720-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="91720-110">See also</span></span>

- [<span data-ttu-id="91720-111">ICorThreadpool (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="91720-111">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)
