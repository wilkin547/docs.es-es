---
title: ITypeName::GetTypeArguments (Método)
ms.date: 03/30/2017
api_name:
- ITypeName.GetTypeArguments
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetTypeArguments
helpviewer_keywords:
- ITypeName::GetTypeArguments method [.NET Framework hosting]
- GetTypeArguments method [.NET Framework hosting]
ms.assetid: 638d77df-ff9c-40d9-88ee-930f5f87ada1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 77b3a898dd929a6eeadc466a04a0fdb10571ed7b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33440166"
---
# <a name="itypenamegettypearguments-method"></a><span data-ttu-id="a30ef-102">ITypeName::GetTypeArguments (Método)</span><span class="sxs-lookup"><span data-stu-id="a30ef-102">ITypeName::GetTypeArguments Method</span></span>
<span data-ttu-id="a30ef-103">Este método es compatible con la infraestructura de .NET Framework y no está diseñado para utilizarse directamente desde el código.</span><span class="sxs-lookup"><span data-stu-id="a30ef-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a30ef-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a30ef-104">Syntax</span></span>  
  
```  
HRESULT GetTypeArguments (  
    [in] DWORD           count,  
    [out] ITypeName**    rgpArguments,  
    [out, retval] DWORD* pCount  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="a30ef-105">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a30ef-105">Requirements</span></span>  
 <span data-ttu-id="a30ef-106">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a30ef-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a30ef-107">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a30ef-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a30ef-108">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a30ef-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a30ef-109">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a30ef-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a30ef-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="a30ef-110">See Also</span></span>  
 [<span data-ttu-id="a30ef-111">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="a30ef-111">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
