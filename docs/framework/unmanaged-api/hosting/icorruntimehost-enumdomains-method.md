---
title: "ICorRuntimeHost::EnumDomains (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorRuntimeHost.EnumDomains
api_location: mscoree.dll
api_type: COM
f1_keywords: ICorRuntimeHost::EnumDomains
helpviewer_keywords:
- ICorRuntimeHost::EnumDomains method [.NET Framework hosting]
- EnumDomains method [.NET Framework hosting]
ms.assetid: 96b74995-0cde-4876-b6df-7fc164e6a5d1
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f12135134e38b3f52c66aa951d61a3da7cf5fa50
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icorruntimehostenumdomains-method"></a><span data-ttu-id="2c261-102">ICorRuntimeHost::EnumDomains (Método)</span><span class="sxs-lookup"><span data-stu-id="2c261-102">ICorRuntimeHost::EnumDomains Method</span></span>
<span data-ttu-id="2c261-103">Obtiene un enumerador para los dominios en el proceso actual.</span><span class="sxs-lookup"><span data-stu-id="2c261-103">Gets an enumerator for the domains in the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c261-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2c261-104">Syntax</span></span>  
  
```  
HRESULT EnumDomains (  
    [out] HCORENUM *hEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2c261-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2c261-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="2c261-106">[out] Un enumerador para los dominios.</span><span class="sxs-lookup"><span data-stu-id="2c261-106">[out] An enumerator for the domains.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2c261-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="2c261-107">Return Value</span></span>  
  
|<span data-ttu-id="2c261-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2c261-108">HRESULT</span></span>|<span data-ttu-id="2c261-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="2c261-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2c261-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="2c261-110">S_OK</span></span>|<span data-ttu-id="2c261-111">La operación fue correcta.</span><span class="sxs-lookup"><span data-stu-id="2c261-111">The operation was successful.</span></span>|  
|<span data-ttu-id="2c261-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="2c261-112">S_FALSE</span></span>|<span data-ttu-id="2c261-113">No se pudo completar la operación.</span><span class="sxs-lookup"><span data-stu-id="2c261-113">The operation failed to complete.</span></span>|  
|<span data-ttu-id="2c261-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2c261-114">E_FAIL</span></span>|<span data-ttu-id="2c261-115">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="2c261-115">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="2c261-116">Si el método devuelve E_FAIL, common language runtime (CLR) ya no es utilizable en el proceso.</span><span class="sxs-lookup"><span data-stu-id="2c261-116">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="2c261-117">Las llamadas subsiguientes a cualquier API de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="2c261-117">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="2c261-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2c261-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2c261-119">El CLR no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="2c261-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2c261-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2c261-120">Requirements</span></span>  
 <span data-ttu-id="2c261-121">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2c261-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c261-122">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2c261-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2c261-123">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2c261-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2c261-124">**Versión de .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="2c261-124">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c261-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="2c261-125">See Also</span></span>  
 [<span data-ttu-id="2c261-126">ICorRuntimeHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2c261-126">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
