---
title: "ICorRuntimeHost::NextDomain (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorRuntimeHost.NextDomain
api_location: mscoree.dll
api_type: COM
f1_keywords: ICorRuntimeHost::NextDomain
helpviewer_keywords:
- ICorRuntimeHost::NextDomain method [.NET Framework hosting]
- NextDomain method [.NET Framework hosting]
ms.assetid: fe07a05b-f6d6-44b5-ab01-b9a6eb15c350
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0e539cd4071fe9713ed53f66c2f67b24b787d259
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icorruntimehostnextdomain-method"></a><span data-ttu-id="c6cb6-102">ICorRuntimeHost::NextDomain (Método)</span><span class="sxs-lookup"><span data-stu-id="c6cb6-102">ICorRuntimeHost::NextDomain Method</span></span>
<span data-ttu-id="c6cb6-103">Obtiene un puntero de interfaz al dominio siguiente de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="c6cb6-103">Gets an interface pointer to the next domain in the enumeration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6cb6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c6cb6-104">Syntax</span></span>  
  
```  
HRESULT NextDomain (  
    [in] HCORENUM hEnum,  
    [out] void** pAppDomain  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c6cb6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c6cb6-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="c6cb6-106">[in] El enumerador que se obtuvo a través de una llamada a [EnumDomains](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-enumdomains-method.md).</span><span class="sxs-lookup"><span data-stu-id="c6cb6-106">[in] The enumerator that was obtained through a call to [EnumDomains](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-enumdomains-method.md).</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="c6cb6-107">[out] Un puntero de interfaz a la <xref:System._AppDomain?displayProperty=nameWithType> tipo que representa el dominio siguiente de la enumeración, o null, si no hay más dominios.</span><span class="sxs-lookup"><span data-stu-id="c6cb6-107">[out] An interface pointer to the <xref:System._AppDomain?displayProperty=nameWithType> type that represents the next domain in the enumeration, or null, if no more domains exist.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c6cb6-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c6cb6-108">Return Value</span></span>  
  
|<span data-ttu-id="c6cb6-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c6cb6-109">HRESULT</span></span>|<span data-ttu-id="c6cb6-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="c6cb6-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c6cb6-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="c6cb6-111">S_OK</span></span>|<span data-ttu-id="c6cb6-112">La operación fue correcta.</span><span class="sxs-lookup"><span data-stu-id="c6cb6-112">The operation was successful.</span></span>|  
|<span data-ttu-id="c6cb6-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="c6cb6-113">S_FALSE</span></span>|<span data-ttu-id="c6cb6-114">No se pudo completar la operación o no hay ningún dominio más en la enumeración.</span><span class="sxs-lookup"><span data-stu-id="c6cb6-114">The operation failed to complete, or there are no more domains in the enumeration.</span></span>|  
|<span data-ttu-id="c6cb6-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c6cb6-115">E_FAIL</span></span>|<span data-ttu-id="c6cb6-116">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="c6cb6-116">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="c6cb6-117">Si el método devuelve E_FAIL, common language runtime (CLR) ya no es utilizable en el proceso.</span><span class="sxs-lookup"><span data-stu-id="c6cb6-117">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="c6cb6-118">Las llamadas subsiguientes a cualquier API de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="c6cb6-118">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="c6cb6-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c6cb6-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c6cb6-120">El CLR no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="c6cb6-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c6cb6-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c6cb6-121">Requirements</span></span>  
 <span data-ttu-id="c6cb6-122">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c6cb6-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6cb6-123">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c6cb6-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c6cb6-124">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c6cb6-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c6cb6-125">**Versiones de .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="c6cb6-125">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6cb6-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="c6cb6-126">See Also</span></span>  
 <xref:System._AppDomain>  
 <xref:System.AppDomain>  
 [<span data-ttu-id="c6cb6-127">ICorRuntimeHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c6cb6-127">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
