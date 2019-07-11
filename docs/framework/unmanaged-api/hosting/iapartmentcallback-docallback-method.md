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
ms.openlocfilehash: 7bd983a41307a4244b5426b8f6b997569cd631e9
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67770497"
---
# <a name="iapartmentcallbackdocallback-method"></a><span data-ttu-id="42a1d-102">IApartmentCallback::DoCallback (Método)</span><span class="sxs-lookup"><span data-stu-id="42a1d-102">IApartmentCallback::DoCallback Method</span></span>
<span data-ttu-id="42a1d-103">Ejecuta la función especificada dentro de un apartamento.</span><span class="sxs-lookup"><span data-stu-id="42a1d-103">Executes the specified function within an apartment.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42a1d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="42a1d-104">Syntax</span></span>  
  
```cpp  
HRESULT _stdcall DoCallback(  
    [in] SIZE_T pFunc,  
    [in] SIZE_T pData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="42a1d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="42a1d-105">Parameters</span></span>  
 `pFunc`  
 <span data-ttu-id="42a1d-106">[in] Un puntero a la función que se ejecuta en el apartamento.</span><span class="sxs-lookup"><span data-stu-id="42a1d-106">[in] A pointer to the function to be executed within the apartment.</span></span>  
  
 `pData`  
 <span data-ttu-id="42a1d-107">[in] Un puntero al argumento de la función.</span><span class="sxs-lookup"><span data-stu-id="42a1d-107">[in] A pointer to the function's argument.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42a1d-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="42a1d-108">Requirements</span></span>  
 <span data-ttu-id="42a1d-109">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="42a1d-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42a1d-110">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="42a1d-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="42a1d-111">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="42a1d-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="42a1d-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42a1d-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42a1d-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="42a1d-113">See also</span></span>

- [<span data-ttu-id="42a1d-114">IApartmentCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="42a1d-114">IApartmentCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iapartmentcallback-interface.md)
