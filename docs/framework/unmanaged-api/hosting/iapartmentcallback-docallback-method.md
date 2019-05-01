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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61970058"
---
# <a name="iapartmentcallbackdocallback-method"></a><span data-ttu-id="d9292-102">IApartmentCallback::DoCallback (Método)</span><span class="sxs-lookup"><span data-stu-id="d9292-102">IApartmentCallback::DoCallback Method</span></span>
<span data-ttu-id="d9292-103">Ejecuta la función especificada dentro de un apartamento.</span><span class="sxs-lookup"><span data-stu-id="d9292-103">Executes the specified function within an apartment.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9292-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d9292-104">Syntax</span></span>  
  
```  
HRESULT _stdcall DoCallback(  
    [in] SIZE_T pFunc,  
    [in] SIZE_T pData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d9292-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d9292-105">Parameters</span></span>  
 `pFunc`  
 <span data-ttu-id="d9292-106">[in] Un puntero a la función que se ejecuta en el apartamento.</span><span class="sxs-lookup"><span data-stu-id="d9292-106">[in] A pointer to the function to be executed within the apartment.</span></span>  
  
 `pData`  
 <span data-ttu-id="d9292-107">[in] Un puntero al argumento de la función.</span><span class="sxs-lookup"><span data-stu-id="d9292-107">[in] A pointer to the function's argument.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d9292-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d9292-108">Requirements</span></span>  
 <span data-ttu-id="d9292-109">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d9292-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d9292-110">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d9292-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d9292-111">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d9292-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d9292-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d9292-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9292-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="d9292-113">See also</span></span>

- [<span data-ttu-id="d9292-114">IApartmentCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d9292-114">IApartmentCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iapartmentcallback-interface.md)
