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
ms.openlocfilehash: 37c02b878cd52034603ab6cafe4d8aaca594cbe9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126885"
---
# <a name="iappdomainbindingonappdomain-method"></a><span data-ttu-id="9600c-102">IAppDomainBinding::OnAppDomain (Método)</span><span class="sxs-lookup"><span data-stu-id="9600c-102">IAppDomainBinding::OnAppDomain Method</span></span>
<span data-ttu-id="9600c-103">Lo llama el Common Language Runtime (CLR) para notificar al host que se ha creado un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="9600c-103">Called by the common language runtime (CLR) to notify the host that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9600c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9600c-104">Syntax</span></span>  
  
```cpp  
HRESULT OnAppDomain (  
    [in] IUnknown* pAppdomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9600c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9600c-105">Parameters</span></span>  
 `pAppdomain`  
 <span data-ttu-id="9600c-106">de Un puntero a un objeto de interfaz [IUnknown](/cpp/atl/iunknown) que representa el nuevo dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="9600c-106">[in] A pointer to an [IUnknown](/cpp/atl/iunknown) interface object that represents the new application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9600c-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9600c-107">Requirements</span></span>  
 <span data-ttu-id="9600c-108">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9600c-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9600c-109">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="9600c-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9600c-110">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="9600c-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9600c-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9600c-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9600c-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="9600c-112">See also</span></span>

- [<span data-ttu-id="9600c-113">IAppDomainBinding (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9600c-113">IAppDomainBinding Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iappdomainbinding-interface.md)
