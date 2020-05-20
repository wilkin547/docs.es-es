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
ms.openlocfilehash: 2d5dbd003d0ea5decae0025d47e6bd5c1fb1ed4a
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83617079"
---
# <a name="iappdomainbindingonappdomain-method"></a><span data-ttu-id="2b64b-102">IAppDomainBinding::OnAppDomain (Método)</span><span class="sxs-lookup"><span data-stu-id="2b64b-102">IAppDomainBinding::OnAppDomain Method</span></span>
<span data-ttu-id="2b64b-103">Lo llama el Common Language Runtime (CLR) para notificar al host que se ha creado un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="2b64b-103">Called by the common language runtime (CLR) to notify the host that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b64b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2b64b-104">Syntax</span></span>  
  
```cpp  
HRESULT OnAppDomain (  
    [in] IUnknown* pAppdomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2b64b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2b64b-105">Parameters</span></span>  
 `pAppdomain`  
 <span data-ttu-id="2b64b-106">de Un puntero a un objeto de interfaz [IUnknown](/cpp/atl/iunknown) que representa el nuevo dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="2b64b-106">[in] A pointer to an [IUnknown](/cpp/atl/iunknown) interface object that represents the new application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2b64b-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2b64b-107">Requirements</span></span>  
 <span data-ttu-id="2b64b-108">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2b64b-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2b64b-109">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="2b64b-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2b64b-110">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="2b64b-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2b64b-111">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2b64b-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b64b-112">Consulta también</span><span class="sxs-lookup"><span data-stu-id="2b64b-112">See also</span></span>

- [<span data-ttu-id="2b64b-113">IAppDomainBinding (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="2b64b-113">IAppDomainBinding Interface</span></span>](iappdomainbinding-interface.md)
