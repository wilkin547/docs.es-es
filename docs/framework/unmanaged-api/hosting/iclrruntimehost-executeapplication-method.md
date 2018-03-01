---
title: "ICLRRuntimeHost::ExecuteApplication (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICLRRuntimeHost.ExecuteApplication
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::ExecuteApplication
helpviewer_keywords:
- ICLRRuntimeHost::ExecuteApplication method [.NET Framework hosting]
- ExecuteApplication method [.NET Framework hosting]
ms.assetid: 5f28cc4e-7176-4e00-aa1f-58ae6ee52fe4
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 7b765f020bd15fa94fb18a6fd7d81cf66c534639
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="iclrruntimehostexecuteapplication-method"></a><span data-ttu-id="3fedb-102">ICLRRuntimeHost::ExecuteApplication (Método)</span><span class="sxs-lookup"><span data-stu-id="3fedb-102">ICLRRuntimeHost::ExecuteApplication Method</span></span>
<span data-ttu-id="3fedb-103">Se utiliza en escenarios de implementación de ClickOnce basada en manifiestos para especificar la aplicación que se debe activar en un nuevo dominio.</span><span class="sxs-lookup"><span data-stu-id="3fedb-103">Used in manifest-based ClickOnce deployment scenarios to specify the application to be activated in a new domain.</span></span> <span data-ttu-id="3fedb-104">Para obtener más información acerca de estos escenarios, vea [seguridad e implementación ClickOnce](/visualstudio/deployment/clickonce-security-and-deployment).</span><span class="sxs-lookup"><span data-stu-id="3fedb-104">For more information about these scenarios, see [ClickOnce Security and Deployment](/visualstudio/deployment/clickonce-security-and-deployment).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3fedb-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3fedb-105">Syntax</span></span>  
  
```  
HRESULT ExecuteApplication(  
    [in] LPCWSTR   pwzAppFullName,  
    [in] DWORD     dwManifestPaths,  
    [in] LPCWSTR   *ppwzManifestPaths,  
    [in] DWORD     dwActivationData,  
    [in] LPCWSTR   *ppwzActivationData,  
    [out] int      *pReturnValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3fedb-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3fedb-106">Parameters</span></span>  
 `pwzAppFullName`  
 <span data-ttu-id="3fedb-107">[in] El nombre completo de la aplicación, tal como se define para <xref:System.ApplicationIdentity>.</span><span class="sxs-lookup"><span data-stu-id="3fedb-107">[in] The full name of the application, as defined for <xref:System.ApplicationIdentity>.</span></span>  
  
 `dwManifestPaths`  
 <span data-ttu-id="3fedb-108">[in] El número de cadenas incluidas en el `ppwzManifestPaths` matriz.</span><span class="sxs-lookup"><span data-stu-id="3fedb-108">[in] The number of strings contained in the `ppwzManifestPaths` array.</span></span>  
  
 `ppwzManifestPaths`  
 <span data-ttu-id="3fedb-109">[in] Opcional.</span><span class="sxs-lookup"><span data-stu-id="3fedb-109">[in] Optional.</span></span> <span data-ttu-id="3fedb-110">Matriz de cadenas que contiene las rutas de acceso de manifiestos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="3fedb-110">A string array that contains manifest paths for the application.</span></span>  
  
 `dwActivationData`  
 <span data-ttu-id="3fedb-111">[in] El número de cadenas incluidas en el `ppwzActivationData` matriz.</span><span class="sxs-lookup"><span data-stu-id="3fedb-111">[in] The number of strings contained in the `ppwzActivationData` array.</span></span>  
  
 `ppwzActivationData`  
 <span data-ttu-id="3fedb-112">[in] Opcional.</span><span class="sxs-lookup"><span data-stu-id="3fedb-112">[in] Optional.</span></span> <span data-ttu-id="3fedb-113">Matriz de cadenas que contiene los datos de activación de la aplicación, como la parte de la cadena de consulta de la dirección URL para las aplicaciones implementadas a través de Internet.</span><span class="sxs-lookup"><span data-stu-id="3fedb-113">A string array that contains the application's activation data, such as the query string portion of the URL for applications deployed over the Web.</span></span>  
  
 `pReturnValue`  
 <span data-ttu-id="3fedb-114">[out] El valor devuelto desde el punto de entrada de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="3fedb-114">[out] The value returned from the entry point of the application.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3fedb-115">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="3fedb-115">Return Value</span></span>  
  
|<span data-ttu-id="3fedb-116">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3fedb-116">HRESULT</span></span>|<span data-ttu-id="3fedb-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="3fedb-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3fedb-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="3fedb-118">S_OK</span></span>|<span data-ttu-id="3fedb-119">`ExecuteApplication`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="3fedb-119">`ExecuteApplication` returned successfully.</span></span>|  
|<span data-ttu-id="3fedb-120">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3fedb-120">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3fedb-121">Common language runtime (CLR) no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="3fedb-121">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3fedb-122">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3fedb-122">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3fedb-123">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="3fedb-123">The call timed out.</span></span>|  
|<span data-ttu-id="3fedb-124">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3fedb-124">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3fedb-125">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="3fedb-125">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3fedb-126">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3fedb-126">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3fedb-127">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="3fedb-127">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3fedb-128">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3fedb-128">E_FAIL</span></span>|<span data-ttu-id="3fedb-129">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="3fedb-129">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3fedb-130">Si el método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="3fedb-130">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3fedb-131">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="3fedb-131">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3fedb-132">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3fedb-132">Remarks</span></span>  
 <span data-ttu-id="3fedb-133">`ExecuteApplication`se usa para activar aplicaciones ClickOnce en un dominio de aplicación recién creado.</span><span class="sxs-lookup"><span data-stu-id="3fedb-133">`ExecuteApplication` is used to activate ClickOnce applications in a newly created application domain.</span></span>  
  
 <span data-ttu-id="3fedb-134">El `pReturnValue` parámetro de salida se establece en el valor devuelto por la aplicación.</span><span class="sxs-lookup"><span data-stu-id="3fedb-134">The `pReturnValue` output parameter is set to the value returned by the application.</span></span> <span data-ttu-id="3fedb-135">Si proporciona un valor null para `pReturnValue`, `ExecuteApplication` no se producen errores, pero no devuelve un valor.</span><span class="sxs-lookup"><span data-stu-id="3fedb-135">If you supply a value of null for `pReturnValue`, `ExecuteApplication` does not fail, but it does not return a value.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="3fedb-136">No llame a la [método Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) método antes de llamar a la `ExecuteApplication` método para activar una aplicación basada en manifiestos.</span><span class="sxs-lookup"><span data-stu-id="3fedb-136">Do not call the [Start Method](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) method before calling the `ExecuteApplication` method to activate a manifest-based application.</span></span> <span data-ttu-id="3fedb-137">Si el `Start` método se llama en primer lugar, el `ExecuteApplication` se producirá un error en la llamada al método.</span><span class="sxs-lookup"><span data-stu-id="3fedb-137">If the `Start` method is called first, the `ExecuteApplication` method call will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3fedb-138">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3fedb-138">Requirements</span></span>  
 <span data-ttu-id="3fedb-139">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3fedb-139">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3fedb-140">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3fedb-140">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3fedb-141">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3fedb-141">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3fedb-142">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3fedb-142">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fedb-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="3fedb-143">See Also</span></span>  
 <xref:System.ActivationContext>  
 <xref:System.AppDomainManager>  
 <xref:System.ApplicationIdentity>  
 [<span data-ttu-id="3fedb-144">ICLRRuntimeHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3fedb-144">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)  
 [<span data-ttu-id="3fedb-145">SetAppDomainManager (método)</span><span class="sxs-lookup"><span data-stu-id="3fedb-145">SetAppDomainManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-setappdomainmanager-method.md)  
 [<span data-ttu-id="3fedb-146">Tutorial: Descargar ensamblados a petición con la API de implementación ClickOnce mediante el diseñador</span><span class="sxs-lookup"><span data-stu-id="3fedb-146">Walkthrough: Downloading Assemblies on Demand with the ClickOnce Deployment API Using the Designer</span></span>](/visualstudio/deployment/walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api-using-the-designer)
