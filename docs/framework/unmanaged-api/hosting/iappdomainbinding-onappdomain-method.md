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
ms.openlocfilehash: 5db040f6db078b211043c547eed823c9b495ac97
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33431327"
---
# <a name="iappdomainbindingonappdomain-method"></a><span data-ttu-id="de745-102">IAppDomainBinding::OnAppDomain (Método)</span><span class="sxs-lookup"><span data-stu-id="de745-102">IAppDomainBinding::OnAppDomain Method</span></span>
<span data-ttu-id="de745-103">Llamado por common language runtime (CLR) para notificar al host que se ha creado un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="de745-103">Called by the common language runtime (CLR) to notify the host that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de745-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="de745-104">Syntax</span></span>  
  
```  
HRESULT OnAppDomain (  
    [in] IUnknown* pAppdomain  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="de745-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="de745-105">Parameters</span></span>  
 `pAppdomain`  
 <span data-ttu-id="de745-106">[in] Un puntero a un [IUnknown](https://msdn.microsoft.com/library/94as6ehy(v=vs.110).aspx) objeto de interfaz que representa el nuevo dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="de745-106">[in] A pointer to an [IUnknown](https://msdn.microsoft.com/library/94as6ehy(v=vs.110).aspx) interface object that represents the new application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="de745-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="de745-107">Requirements</span></span>  
 <span data-ttu-id="de745-108">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="de745-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de745-109">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="de745-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="de745-110">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="de745-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="de745-111">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="de745-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de745-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="de745-112">See Also</span></span>  
 [<span data-ttu-id="de745-113">IAppDomainBinding (interfaz)</span><span class="sxs-lookup"><span data-stu-id="de745-113">IAppDomainBinding Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iappdomainbinding-interface.md)
