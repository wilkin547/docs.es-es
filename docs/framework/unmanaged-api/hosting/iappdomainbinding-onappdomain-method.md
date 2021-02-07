---
description: 'Más información sobre: Iappdomainbinding (:: Onappdomain ((método)'
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
ms.openlocfilehash: de7f37152261a6fe829026607cf135f3ea0b4a84
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99760607"
---
# <a name="iappdomainbindingonappdomain-method"></a><span data-ttu-id="e2e8d-103">IAppDomainBinding::OnAppDomain (Método)</span><span class="sxs-lookup"><span data-stu-id="e2e8d-103">IAppDomainBinding::OnAppDomain Method</span></span>

<span data-ttu-id="e2e8d-104">Lo llama el Common Language Runtime (CLR) para notificar al host que se ha creado un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="e2e8d-104">Called by the common language runtime (CLR) to notify the host that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2e8d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e2e8d-105">Syntax</span></span>  
  
```cpp  
HRESULT OnAppDomain (  
    [in] IUnknown* pAppdomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e2e8d-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e2e8d-106">Parameters</span></span>  

 `pAppdomain`  
 <span data-ttu-id="e2e8d-107">de Un puntero a un objeto de interfaz [IUnknown](/cpp/atl/iunknown) que representa el nuevo dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="e2e8d-107">[in] A pointer to an [IUnknown](/cpp/atl/iunknown) interface object that represents the new application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2e8d-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e2e8d-108">Requirements</span></span>  

 <span data-ttu-id="e2e8d-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e2e8d-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2e8d-110">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="e2e8d-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e2e8d-111">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e2e8d-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e2e8d-112">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e2e8d-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2e8d-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="e2e8d-113">See also</span></span>

- [<span data-ttu-id="e2e8d-114">IAppDomainBinding (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e2e8d-114">IAppDomainBinding Interface</span></span>](iappdomainbinding-interface.md)
