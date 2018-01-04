---
title: "ICLRRuntimeHost::UnloadAppDomain (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeHost.UnloadAppDomain
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRRuntimeHost::UnloadAppDomain
helpviewer_keywords:
- ICLRRuntimeHost::UnloadAppDomain method [.NET Framework hosting]
- UnloadAppDomain method [.NET Framework hosting]
ms.assetid: 571912bc-3429-4ff8-8eb2-ea993ffbd901
topic_type: apiref
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 481f701ae4db15b66596c3af89c2e7aff7a28f88
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="iclrruntimehostunloadappdomain-method"></a><span data-ttu-id="10c58-102">ICLRRuntimeHost::UnloadAppDomain (Método)</span><span class="sxs-lookup"><span data-stu-id="10c58-102">ICLRRuntimeHost::UnloadAppDomain Method</span></span>
<span data-ttu-id="10c58-103">Descarga los recursos administrados <xref:System.AppDomain> que se corresponde con el identificador numérico especificado.</span><span class="sxs-lookup"><span data-stu-id="10c58-103">Unloads the managed <xref:System.AppDomain> that corresponds to the specified numeric identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10c58-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="10c58-104">Syntax</span></span>  
  
```  
HRESULT UnloadAppDomain(  
    [in] DWORD dwAppDomainId  
    [in] BOOL  fWaitUntilDone  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="10c58-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="10c58-105">Parameters</span></span>  
 `dwAppDomainId`  
 <span data-ttu-id="10c58-106">[in] El identificador numérico del dominio de aplicación a punto de descargarse.</span><span class="sxs-lookup"><span data-stu-id="10c58-106">[in] The numeric identifier of the application domain to unload.</span></span>  
  
 `fWaitUntilDone`  
 <span data-ttu-id="10c58-107">[in] `true` para indicar que common language runtime (CLR) debe esperar hasta que ha terminado de ejecutar el subproceso actual de la aplicación antes de intentar descargar el dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="10c58-107">[in] `true` to indicate that the common language runtime( CLR) must wait until it has finished executing the application's current thread before attempting to unload the application domain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="10c58-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="10c58-108">Return Value</span></span>  
  
|<span data-ttu-id="10c58-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="10c58-109">HRESULT</span></span>|<span data-ttu-id="10c58-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="10c58-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="10c58-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="10c58-111">S_OK</span></span>|<span data-ttu-id="10c58-112">`UnloadAppDomain`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="10c58-112">`UnloadAppDomain` returned successfully.</span></span>|  
|<span data-ttu-id="10c58-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="10c58-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="10c58-114">El CLR no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="10c58-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="10c58-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="10c58-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="10c58-116">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="10c58-116">The call timed out.</span></span>|  
|<span data-ttu-id="10c58-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="10c58-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="10c58-118">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="10c58-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="10c58-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="10c58-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="10c58-120">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="10c58-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="10c58-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="10c58-121">E_FAIL</span></span>|<span data-ttu-id="10c58-122">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="10c58-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="10c58-123">Si el método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="10c58-123">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="10c58-124">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="10c58-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="10c58-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="10c58-125">Remarks</span></span>  
 <span data-ttu-id="10c58-126">Puede obtener el identificador numérico del dominio de aplicación en el que está ejecutando el subproceso actual mediante una llamada a [GetCurrentAppDomainId](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md).</span><span class="sxs-lookup"><span data-stu-id="10c58-126">You can get the numeric identifier of the application domain in which the current thread is executing by calling [GetCurrentAppDomainId](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md).</span></span> <span data-ttu-id="10c58-127">Este identificador corresponde a la <xref:System.AppDomain.Id%2A> propiedad de los recursos administrados <xref:System.AppDomain> tipo.</span><span class="sxs-lookup"><span data-stu-id="10c58-127">This identifier corresponds to the <xref:System.AppDomain.Id%2A> property of the managed <xref:System.AppDomain> type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="10c58-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="10c58-128">Requirements</span></span>  
 <span data-ttu-id="10c58-129">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="10c58-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="10c58-130">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="10c58-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="10c58-131">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="10c58-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="10c58-132">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="10c58-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10c58-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="10c58-133">See Also</span></span>  
 [<span data-ttu-id="10c58-134">ICLRRuntimeHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="10c58-134">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
