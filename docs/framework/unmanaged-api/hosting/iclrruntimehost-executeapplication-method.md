---
title: ICLRRuntimeHost::ExecuteApplication (Método)
ms.date: 03/30/2017
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
ms.openlocfilehash: 4b56ffab8fb6a9ef70b51421f9cdc5535111e527
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120479"
---
# <a name="iclrruntimehostexecuteapplication-method"></a><span data-ttu-id="314c0-102">ICLRRuntimeHost::ExecuteApplication (Método)</span><span class="sxs-lookup"><span data-stu-id="314c0-102">ICLRRuntimeHost::ExecuteApplication Method</span></span>
<span data-ttu-id="314c0-103">Se usa en escenarios de implementación ClickOnce basados en manifiesto para especificar la aplicación que se va a activar en un dominio nuevo.</span><span class="sxs-lookup"><span data-stu-id="314c0-103">Used in manifest-based ClickOnce deployment scenarios to specify the application to be activated in a new domain.</span></span> <span data-ttu-id="314c0-104">Para obtener más información acerca de estos escenarios, consulte [seguridad e implementación de ClickOnce](/visualstudio/deployment/clickonce-security-and-deployment).</span><span class="sxs-lookup"><span data-stu-id="314c0-104">For more information about these scenarios, see [ClickOnce Security and Deployment](/visualstudio/deployment/clickonce-security-and-deployment).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="314c0-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="314c0-105">Syntax</span></span>  
  
```cpp  
HRESULT ExecuteApplication(  
    [in] LPCWSTR   pwzAppFullName,  
    [in] DWORD     dwManifestPaths,  
    [in] LPCWSTR   *ppwzManifestPaths,  
    [in] DWORD     dwActivationData,  
    [in] LPCWSTR   *ppwzActivationData,  
    [out] int      *pReturnValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="314c0-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="314c0-106">Parameters</span></span>  
 `pwzAppFullName`  
 <span data-ttu-id="314c0-107">de Nombre completo de la aplicación, tal y como se define para <xref:System.ApplicationIdentity>.</span><span class="sxs-lookup"><span data-stu-id="314c0-107">[in] The full name of the application, as defined for <xref:System.ApplicationIdentity>.</span></span>  
  
 `dwManifestPaths`  
 <span data-ttu-id="314c0-108">de Número de cadenas contenidas en la matriz de `ppwzManifestPaths`.</span><span class="sxs-lookup"><span data-stu-id="314c0-108">[in] The number of strings contained in the `ppwzManifestPaths` array.</span></span>  
  
 `ppwzManifestPaths`  
 <span data-ttu-id="314c0-109">[in] Opcional.</span><span class="sxs-lookup"><span data-stu-id="314c0-109">[in] Optional.</span></span> <span data-ttu-id="314c0-110">Matriz de cadenas que contiene las rutas de acceso de manifiesto para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="314c0-110">A string array that contains manifest paths for the application.</span></span>  
  
 `dwActivationData`  
 <span data-ttu-id="314c0-111">de Número de cadenas contenidas en la matriz de `ppwzActivationData`.</span><span class="sxs-lookup"><span data-stu-id="314c0-111">[in] The number of strings contained in the `ppwzActivationData` array.</span></span>  
  
 `ppwzActivationData`  
 <span data-ttu-id="314c0-112">[in] Opcional.</span><span class="sxs-lookup"><span data-stu-id="314c0-112">[in] Optional.</span></span> <span data-ttu-id="314c0-113">Una matriz de cadenas que contiene los datos de activación de la aplicación, como la parte de la cadena de consulta de la dirección URL de las aplicaciones implementadas a través de la Web.</span><span class="sxs-lookup"><span data-stu-id="314c0-113">A string array that contains the application's activation data, such as the query string portion of the URL for applications deployed over the Web.</span></span>  
  
 `pReturnValue`  
 <span data-ttu-id="314c0-114">enuncia El valor devuelto desde el punto de entrada de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="314c0-114">[out] The value returned from the entry point of the application.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="314c0-115">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="314c0-115">Return Value</span></span>  
  
|<span data-ttu-id="314c0-116">HRESULT</span><span class="sxs-lookup"><span data-stu-id="314c0-116">HRESULT</span></span>|<span data-ttu-id="314c0-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="314c0-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="314c0-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="314c0-118">S_OK</span></span>|<span data-ttu-id="314c0-119">`ExecuteApplication` devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="314c0-119">`ExecuteApplication` returned successfully.</span></span>|  
|<span data-ttu-id="314c0-120">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="314c0-120">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="314c0-121">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="314c0-121">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="314c0-122">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="314c0-122">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="314c0-123">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="314c0-123">The call timed out.</span></span>|  
|<span data-ttu-id="314c0-124">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="314c0-124">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="314c0-125">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="314c0-125">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="314c0-126">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="314c0-126">HOST_E_ABANDONED</span></span>|<span data-ttu-id="314c0-127">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="314c0-127">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="314c0-128">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="314c0-128">E_FAIL</span></span>|<span data-ttu-id="314c0-129">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="314c0-129">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="314c0-130">Si un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="314c0-130">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="314c0-131">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="314c0-131">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="314c0-132">Comentarios</span><span class="sxs-lookup"><span data-stu-id="314c0-132">Remarks</span></span>  
 <span data-ttu-id="314c0-133">`ExecuteApplication` se utiliza para activar las aplicaciones ClickOnce en un dominio de aplicación recién creado.</span><span class="sxs-lookup"><span data-stu-id="314c0-133">`ExecuteApplication` is used to activate ClickOnce applications in a newly created application domain.</span></span>  
  
 <span data-ttu-id="314c0-134">El parámetro de salida `pReturnValue` se establece en el valor devuelto por la aplicación.</span><span class="sxs-lookup"><span data-stu-id="314c0-134">The `pReturnValue` output parameter is set to the value returned by the application.</span></span> <span data-ttu-id="314c0-135">Si proporciona un valor null para `pReturnValue`, `ExecuteApplication` no producirá un error, pero no devolverá ningún valor.</span><span class="sxs-lookup"><span data-stu-id="314c0-135">If you supply a value of null for `pReturnValue`, `ExecuteApplication` does not fail, but it does not return a value.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="314c0-136">No llame al método [Start Method](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) antes de llamar al método `ExecuteApplication` para activar una aplicación basada en manifiesto.</span><span class="sxs-lookup"><span data-stu-id="314c0-136">Do not call the [Start Method](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) method before calling the `ExecuteApplication` method to activate a manifest-based application.</span></span> <span data-ttu-id="314c0-137">Si se llama primero al método `Start`, se producirá un error en la llamada al método `ExecuteApplication`.</span><span class="sxs-lookup"><span data-stu-id="314c0-137">If the `Start` method is called first, the `ExecuteApplication` method call will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="314c0-138">Requisitos</span><span class="sxs-lookup"><span data-stu-id="314c0-138">Requirements</span></span>  
 <span data-ttu-id="314c0-139">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="314c0-139">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="314c0-140">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="314c0-140">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="314c0-141">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="314c0-141">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="314c0-142">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="314c0-142">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="314c0-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="314c0-143">See also</span></span>

- <xref:System.ActivationContext>
- <xref:System.AppDomainManager>
- <xref:System.ApplicationIdentity>
- [<span data-ttu-id="314c0-144">ICLRRuntimeHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="314c0-144">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
- [<span data-ttu-id="314c0-145">SetAppDomainManager (método)</span><span class="sxs-lookup"><span data-stu-id="314c0-145">SetAppDomainManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-setappdomainmanager-method.md)
- [<span data-ttu-id="314c0-146">Tutorial: Descargar ensamblados a petición con la API de implementación ClickOnce mediante el diseñador</span><span class="sxs-lookup"><span data-stu-id="314c0-146">Walkthrough: Downloading Assemblies on Demand with the ClickOnce Deployment API Using the Designer</span></span>](/visualstudio/deployment/walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api-using-the-designer)
