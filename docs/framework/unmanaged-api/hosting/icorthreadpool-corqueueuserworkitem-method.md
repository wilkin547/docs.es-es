---
title: "ICorThreadpool::CorQueueUserWorkItem (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorThreadpool.CorQueueUserWorkItem
api_location: mscoree.dll
api_type: COM
f1_keywords: CorQueueUserWorkItem
helpviewer_keywords:
- ICorThreadpool::CorQueueUserWorkItem method [.NET Framework hosting]
- CorQueueUserWorkItem method [.NET Framework hosting]
ms.assetid: 29ac7898-a7c7-433e-8f79-cd5237e0bab8
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ea796485a83914c32b50444e6b8479b3ec509ea9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icorthreadpoolcorqueueuserworkitem-method"></a><span data-ttu-id="97b79-102">ICorThreadpool::CorQueueUserWorkItem (Método)</span><span class="sxs-lookup"><span data-stu-id="97b79-102">ICorThreadpool::CorQueueUserWorkItem Method</span></span>
<span data-ttu-id="97b79-103">Este método es compatible con la infraestructura de .NET Framework y no está diseñado para utilizarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="97b79-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97b79-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="97b79-104">Syntax</span></span>  
  
```  
HRESULT CorQueueUserWorkItem (  
    [in] LPTHREAD_START_ROUTINE Function,  
    [in] PVOID                  Context,  
    [in] BOOL                   executeOnlyOnce,  
    [out] BOOL*                 result  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="97b79-105">Requisitos</span><span class="sxs-lookup"><span data-stu-id="97b79-105">Requirements</span></span>  
 <span data-ttu-id="97b79-106">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="97b79-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="97b79-107">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="97b79-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="97b79-108">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="97b79-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="97b79-109">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="97b79-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97b79-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="97b79-110">See Also</span></span>  
 [<span data-ttu-id="97b79-111">ICorThreadpool (interfaz)</span><span class="sxs-lookup"><span data-stu-id="97b79-111">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)
