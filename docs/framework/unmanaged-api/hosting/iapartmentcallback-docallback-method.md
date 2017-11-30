---
title: "IApartmentCallback::DoCallback (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IApartmentCallback.DoCallback
api_location: mscoree.dll
api_type: COM
f1_keywords: DoCallback
helpviewer_keywords:
- IApartmentCallback::DoCallback method [.NET Framework hosting]
- DoCallback method [.NET Framework hosting]
ms.assetid: 8edad30c-30ff-4bee-813c-75525a82fc93
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 03c72af5fba0871433e46c2b8045c55bbf0a5ff6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="iapartmentcallbackdocallback-method"></a><span data-ttu-id="a2af6-102">IApartmentCallback::DoCallback (Método)</span><span class="sxs-lookup"><span data-stu-id="a2af6-102">IApartmentCallback::DoCallback Method</span></span>
<span data-ttu-id="a2af6-103">Ejecuta la función especificada dentro de un apartamento.</span><span class="sxs-lookup"><span data-stu-id="a2af6-103">Executes the specified function within an apartment.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2af6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a2af6-104">Syntax</span></span>  
  
```  
HRESULT _stdcall DoCallback(  
    [in] SIZE_T pFunc,  
    [in] SIZE_T pData  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a2af6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a2af6-105">Parameters</span></span>  
 `pFunc`  
 <span data-ttu-id="a2af6-106">[in] Un puntero a la función que se ejecuta en el apartamento.</span><span class="sxs-lookup"><span data-stu-id="a2af6-106">[in] A pointer to the function to be executed within the apartment.</span></span>  
  
 `pData`  
 <span data-ttu-id="a2af6-107">[in] Un puntero al argumento de la función.</span><span class="sxs-lookup"><span data-stu-id="a2af6-107">[in] A pointer to the function's argument.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a2af6-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a2af6-108">Requirements</span></span>  
 <span data-ttu-id="a2af6-109">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a2af6-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a2af6-110">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a2af6-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a2af6-111">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a2af6-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a2af6-112">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a2af6-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2af6-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="a2af6-113">See Also</span></span>  
 [<span data-ttu-id="a2af6-114">IApartmentCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a2af6-114">IApartmentCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iapartmentcallback-interface.md)
