---
title: IAppDomainBinding::OnAppDomain (Método)
ms.date: 03/30/2017
api_name:
- IAppDomainBinding.OnAppDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- OnAppDomain
helpviewer_keywords:
- IAppDomainBinding::OnAppDomain method [.NET Framework hosting]
- OnAppDomain method [.NET Framework hosting]
ms.assetid: b419dcc9-e8aa-484b-af0d-0f40358edb99
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 798ef6a9b058d9d49019554feba63627360e6a0e
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57480044"
---
# <a name="iappdomainbindingonappdomain-method"></a><span data-ttu-id="e9e0b-102">IAppDomainBinding::OnAppDomain (Método)</span><span class="sxs-lookup"><span data-stu-id="e9e0b-102">IAppDomainBinding::OnAppDomain Method</span></span>
<span data-ttu-id="e9e0b-103">Lo llama common language runtime (CLR) para notificar al host que se ha creado un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="e9e0b-103">Called by the common language runtime (CLR) to notify the host that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9e0b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e9e0b-104">Syntax</span></span>  
  
```  
HRESULT OnAppDomain (  
    [in] IUnknown* pAppdomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e9e0b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e9e0b-105">Parameters</span></span>  
 `pAppdomain`  
 <span data-ttu-id="e9e0b-106">[in] Un puntero a un [IUnknown](/cpp/atl/iunknown) objeto de interfaz que representa el nuevo dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="e9e0b-106">[in] A pointer to an [IUnknown](/cpp/atl/iunknown) interface object that represents the new application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9e0b-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e9e0b-107">Requirements</span></span>  
 <span data-ttu-id="e9e0b-108">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e9e0b-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9e0b-109">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e9e0b-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e9e0b-110">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e9e0b-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e9e0b-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9e0b-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9e0b-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="e9e0b-112">See also</span></span>
- [<span data-ttu-id="e9e0b-113">IAppDomainBinding (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e9e0b-113">IAppDomainBinding Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iappdomainbinding-interface.md)
