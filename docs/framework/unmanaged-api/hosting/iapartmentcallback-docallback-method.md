---
title: IApartmentCallback::DoCallback (Método)
ms.date: 03/30/2017
api_name:
- IApartmentCallback.DoCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- DoCallback
helpviewer_keywords:
- IApartmentCallback::DoCallback method [.NET Framework hosting]
- DoCallback method [.NET Framework hosting]
ms.assetid: 8edad30c-30ff-4bee-813c-75525a82fc93
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 77a2ccaf6f972fadd8396378dc7777ec4c85120d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59110232"
---
# <a name="iapartmentcallbackdocallback-method"></a><span data-ttu-id="3e0df-102">IApartmentCallback::DoCallback (Método)</span><span class="sxs-lookup"><span data-stu-id="3e0df-102">IApartmentCallback::DoCallback Method</span></span>
<span data-ttu-id="3e0df-103">Ejecuta la función especificada dentro de un apartamento.</span><span class="sxs-lookup"><span data-stu-id="3e0df-103">Executes the specified function within an apartment.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e0df-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3e0df-104">Syntax</span></span>  
  
```  
HRESULT _stdcall DoCallback(  
    [in] SIZE_T pFunc,  
    [in] SIZE_T pData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3e0df-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3e0df-105">Parameters</span></span>  
 `pFunc`  
 <span data-ttu-id="3e0df-106">[in] Un puntero a la función que se ejecuta en el apartamento.</span><span class="sxs-lookup"><span data-stu-id="3e0df-106">[in] A pointer to the function to be executed within the apartment.</span></span>  
  
 `pData`  
 <span data-ttu-id="3e0df-107">[in] Un puntero al argumento de la función.</span><span class="sxs-lookup"><span data-stu-id="3e0df-107">[in] A pointer to the function's argument.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3e0df-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3e0df-108">Requirements</span></span>  
 <span data-ttu-id="3e0df-109">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3e0df-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3e0df-110">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3e0df-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3e0df-111">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3e0df-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="3e0df-112">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="3e0df-112">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3e0df-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="3e0df-113">See also</span></span>

- [<span data-ttu-id="3e0df-114">IApartmentCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3e0df-114">IApartmentCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iapartmentcallback-interface.md)
