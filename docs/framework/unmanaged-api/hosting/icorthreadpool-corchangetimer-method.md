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
ms.openlocfilehash: b56a0cc1e6c110c1e201a365dc333e700686a4a2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33436876"
---
# <a name="icorthreadpoolcorchangetimer-method"></a><span data-ttu-id="b6d2b-102">ICorThreadpool::CorChangeTimer (Método)</span><span class="sxs-lookup"><span data-stu-id="b6d2b-102">ICorThreadpool::CorChangeTimer Method</span></span>
<span data-ttu-id="b6d2b-103">Este método es compatible con la infraestructura de .NET Framework y no está diseñado para utilizarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="b6d2b-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6d2b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b6d2b-104">Syntax</span></span>  
  
```  
HRESULT CorChangeTimer (  
    [in]  HANDLE Timer,   
    [in]  ULONG  DueTime,   
    [in]  ULONG  Period,  
    [out] BOOL*  result  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="b6d2b-105">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b6d2b-105">Requirements</span></span>  
 <span data-ttu-id="b6d2b-106">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b6d2b-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b6d2b-107">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b6d2b-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b6d2b-108">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b6d2b-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b6d2b-109">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b6d2b-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6d2b-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="b6d2b-110">See Also</span></span>  
 [<span data-ttu-id="b6d2b-111">ICorThreadpool (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b6d2b-111">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)
