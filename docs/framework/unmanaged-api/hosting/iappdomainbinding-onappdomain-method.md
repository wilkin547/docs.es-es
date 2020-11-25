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
ms.openlocfilehash: 65f6be8c12ce057422ad178c759affed170e44ba
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721721"
---
# <a name="iappdomainbindingonappdomain-method"></a><span data-ttu-id="b5b05-102">IAppDomainBinding::OnAppDomain (Método)</span><span class="sxs-lookup"><span data-stu-id="b5b05-102">IAppDomainBinding::OnAppDomain Method</span></span>

<span data-ttu-id="b5b05-103">Lo llama el Common Language Runtime (CLR) para notificar al host que se ha creado un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="b5b05-103">Called by the common language runtime (CLR) to notify the host that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5b05-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b5b05-104">Syntax</span></span>  
  
```cpp  
HRESULT OnAppDomain (  
    [in] IUnknown* pAppdomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b5b05-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b5b05-105">Parameters</span></span>  

 `pAppdomain`  
 <span data-ttu-id="b5b05-106">de Un puntero a un objeto de interfaz [IUnknown](/cpp/atl/iunknown) que representa el nuevo dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="b5b05-106">[in] A pointer to an [IUnknown](/cpp/atl/iunknown) interface object that represents the new application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b5b05-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b5b05-107">Requirements</span></span>  

 <span data-ttu-id="b5b05-108">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b5b05-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b5b05-109">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="b5b05-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b5b05-110">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b5b05-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b5b05-111">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b5b05-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5b05-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b5b05-112">See also</span></span>

- [<span data-ttu-id="b5b05-113">IAppDomainBinding (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b5b05-113">IAppDomainBinding Interface</span></span>](iappdomainbinding-interface.md)
