---
title: "ICLRRuntimeHost::GetCurrentAppDomainId (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeHost.GetCurrentAppDomainId
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRRuntimeHost::GetCurrentAppDomainId
helpviewer_keywords:
- ICLRRuntimeHost::GetCurrentAppDomainId method [.NET Framework hosting]
- GetCurrentAppDomainId method [.NET Framework hosting]
ms.assetid: 33800475-7815-4976-8aca-a1038761a2ef
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5e4e682ae71512e24d91ea7e4e12a8a2dd70f1de
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="iclrruntimehostgetcurrentappdomainid-method"></a><span data-ttu-id="fcb69-102">ICLRRuntimeHost::GetCurrentAppDomainId (Método)</span><span class="sxs-lookup"><span data-stu-id="fcb69-102">ICLRRuntimeHost::GetCurrentAppDomainId Method</span></span>
<span data-ttu-id="fcb69-103">Obtiene el identificador numérico de la <xref:System.AppDomain> que se está ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="fcb69-103">Gets the numeric identifier of the <xref:System.AppDomain> that is currently executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fcb69-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fcb69-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentAppDomainId(  
    [out] DWORD* pdwAppDomainId  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fcb69-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fcb69-105">Parameters</span></span>  
 `pdwAppDomainId`  
 <span data-ttu-id="fcb69-106">[out] El identificador numérico de la <xref:System.AppDomain> que se está ejecutando actualmente.</span><span class="sxs-lookup"><span data-stu-id="fcb69-106">[out] The numeric identifier of the <xref:System.AppDomain> that is currently executing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fcb69-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="fcb69-107">Return Value</span></span>  
  
|<span data-ttu-id="fcb69-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fcb69-108">HRESULT</span></span>|<span data-ttu-id="fcb69-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="fcb69-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fcb69-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="fcb69-110">S_OK</span></span>|<span data-ttu-id="fcb69-111">`GetCurrentAppDomainId`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="fcb69-111">`GetCurrentAppDomainId` returned successfully.</span></span>|  
|<span data-ttu-id="fcb69-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="fcb69-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="fcb69-113">Common language runtime (CLR) no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="fcb69-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="fcb69-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="fcb69-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="fcb69-115">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="fcb69-115">The call timed out.</span></span>|  
|<span data-ttu-id="fcb69-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="fcb69-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="fcb69-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="fcb69-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="fcb69-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="fcb69-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="fcb69-119">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="fcb69-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="fcb69-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="fcb69-120">E_FAIL</span></span>|<span data-ttu-id="fcb69-121">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="fcb69-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="fcb69-122">Si el método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="fcb69-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="fcb69-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="fcb69-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fcb69-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fcb69-124">Remarks</span></span>  
 <span data-ttu-id="fcb69-125">El `pdwAppDomainId` parámetro se establece en el valor de la <xref:System.AppDomain.Id%2A> propiedad de la <xref:System.AppDomain> en que se está ejecutando el subproceso actual.</span><span class="sxs-lookup"><span data-stu-id="fcb69-125">The `pdwAppDomainId` parameter is set to the value of the <xref:System.AppDomain.Id%2A> property of the <xref:System.AppDomain> in which the current thread is executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fcb69-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fcb69-126">Requirements</span></span>  
 <span data-ttu-id="fcb69-127">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fcb69-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fcb69-128">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="fcb69-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fcb69-129">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fcb69-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fcb69-130">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fcb69-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcb69-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="fcb69-131">See Also</span></span>  
 <xref:System.AppDomain>  
 <xref:System.AppDomainManager>  
 [<span data-ttu-id="fcb69-132">ICLRRuntimeHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="fcb69-132">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
