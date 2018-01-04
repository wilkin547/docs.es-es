---
title: "ICLRRuntimeHost::ExecuteInAppDomain (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeHost.ExecuteInAppDomain
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRRuntimeHost::ExecuteInAppDomain
helpviewer_keywords:
- ICLRRuntimeHost::ExecuteInAppDomain method [.NET Framework hosting]
- ExecuteInAppDomain method [.NET Framework hosting]
ms.assetid: e2b0e2db-3fae-4b56-844e-d30a125a660c
topic_type: apiref
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a8c540c9618655e6df30ad253e0c4cccdf6624e3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="iclrruntimehostexecuteinappdomain-method"></a><span data-ttu-id="64eea-102">ICLRRuntimeHost::ExecuteInAppDomain (Método)</span><span class="sxs-lookup"><span data-stu-id="64eea-102">ICLRRuntimeHost::ExecuteInAppDomain Method</span></span>
<span data-ttu-id="64eea-103">Especifica el <xref:System.AppDomain> en el que se va a ejecutar el código administrado especificado.</span><span class="sxs-lookup"><span data-stu-id="64eea-103">Specifies the <xref:System.AppDomain> in which to execute the specified managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64eea-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="64eea-104">Syntax</span></span>  
  
```  
HRESULT ExecuteInAppDomain(  
    [in] DWORD AppDomainId,   
    [in] FExecuteInDomainCallback pCallback,   
    [in] void* cookie  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="64eea-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="64eea-105">Parameters</span></span>  
 `AppDomainId`  
 <span data-ttu-id="64eea-106">[in] El identificador numérico de la <xref:System.AppDomain> en el que se va a ejecutar el método especificado.</span><span class="sxs-lookup"><span data-stu-id="64eea-106">[in] The numeric ID of the <xref:System.AppDomain> in which to execute the specified method.</span></span>  
  
 `pCallback`  
 <span data-ttu-id="64eea-107">[in] Un puntero a función que se ejecuta dentro de lo especificado <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="64eea-107">[in] A pointer to the function to execute within the specified <xref:System.AppDomain>.</span></span>  
  
 `cookie`  
 <span data-ttu-id="64eea-108">[in] Un puntero a la memoria asignada por el llamador opaco.</span><span class="sxs-lookup"><span data-stu-id="64eea-108">[in] A pointer to opaque caller-allocated memory.</span></span> <span data-ttu-id="64eea-109">Este parámetro se pasa por common language runtime (CLR) para la devolución de llamada de dominio.</span><span class="sxs-lookup"><span data-stu-id="64eea-109">This parameter is passed by the common language runtime (CLR) to the domain callback.</span></span> <span data-ttu-id="64eea-110">No tiene memoria de montón administrado en tiempo de ejecución; la asignación y la duración de esta memoria se controlan por el llamador.</span><span class="sxs-lookup"><span data-stu-id="64eea-110">It is not runtime-managed heap memory; both the allocation and lifetime of this memory are controlled by the caller.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="64eea-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="64eea-111">Return Value</span></span>  
  
|<span data-ttu-id="64eea-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="64eea-112">HRESULT</span></span>|<span data-ttu-id="64eea-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="64eea-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="64eea-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="64eea-114">S_OK</span></span>|<span data-ttu-id="64eea-115">`ExecuteInAppDomain`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="64eea-115">`ExecuteInAppDomain` returned successfully.</span></span>|  
|<span data-ttu-id="64eea-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="64eea-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="64eea-117">El CLR no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="64eea-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="64eea-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="64eea-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="64eea-119">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="64eea-119">The call timed out.</span></span>|  
|<span data-ttu-id="64eea-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="64eea-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="64eea-121">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="64eea-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="64eea-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="64eea-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="64eea-123">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="64eea-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="64eea-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="64eea-124">E_FAIL</span></span>|<span data-ttu-id="64eea-125">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="64eea-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="64eea-126">Si el método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="64eea-126">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="64eea-127">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="64eea-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="64eea-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="64eea-128">Remarks</span></span>  
 <span data-ttu-id="64eea-129">`ExecuteInAppDomain`permite al host controlar over que administran <xref:System.AppDomain> debe ejecutarse en el método administrado especificado.</span><span class="sxs-lookup"><span data-stu-id="64eea-129">`ExecuteInAppDomain` allows the host to exercise control over which managed <xref:System.AppDomain> the specified managed method should be executed in.</span></span> <span data-ttu-id="64eea-130">Puede obtener el valor de identificador de un dominio de aplicación, que se corresponde con el valor de la <xref:System.AppDomain.Id%2A> propiedad, mediante una llamada a [GetCurrentAppDomainId (método)](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md).</span><span class="sxs-lookup"><span data-stu-id="64eea-130">You can get the value of an application domain's identifier, which corresponds to the value of the <xref:System.AppDomain.Id%2A> property, by calling [GetCurrentAppDomainId Method](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-getcurrentappdomainid-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="64eea-131">Requisitos</span><span class="sxs-lookup"><span data-stu-id="64eea-131">Requirements</span></span>  
 <span data-ttu-id="64eea-132">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="64eea-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="64eea-133">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="64eea-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="64eea-134">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="64eea-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="64eea-135">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="64eea-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64eea-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="64eea-136">See Also</span></span>  
 [<span data-ttu-id="64eea-137">ICLRRuntimeHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="64eea-137">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
