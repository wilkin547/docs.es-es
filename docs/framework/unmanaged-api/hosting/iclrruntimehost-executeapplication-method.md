---
description: 'Más información acerca de: ICLRRuntimeHost:: ExecuteApplication ((método)'
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
ms.openlocfilehash: 1511cc3dcf05c3f2243f4080143789e456c39167
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99688980"
---
# <a name="iclrruntimehostexecuteapplication-method"></a><span data-ttu-id="59fdd-103">ICLRRuntimeHost::ExecuteApplication (Método)</span><span class="sxs-lookup"><span data-stu-id="59fdd-103">ICLRRuntimeHost::ExecuteApplication Method</span></span>

<span data-ttu-id="59fdd-104">Se usa en escenarios de implementación ClickOnce basados en manifiesto para especificar la aplicación que se va a activar en un dominio nuevo.</span><span class="sxs-lookup"><span data-stu-id="59fdd-104">Used in manifest-based ClickOnce deployment scenarios to specify the application to be activated in a new domain.</span></span> <span data-ttu-id="59fdd-105">Para obtener más información acerca de estos escenarios, consulte [seguridad e implementación de ClickOnce](/visualstudio/deployment/clickonce-security-and-deployment).</span><span class="sxs-lookup"><span data-stu-id="59fdd-105">For more information about these scenarios, see [ClickOnce Security and Deployment](/visualstudio/deployment/clickonce-security-and-deployment).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59fdd-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="59fdd-106">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="59fdd-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="59fdd-107">Parameters</span></span>  

 `pwzAppFullName`  
 <span data-ttu-id="59fdd-108">de Nombre completo de la aplicación, tal y como se define para <xref:System.ApplicationIdentity> .</span><span class="sxs-lookup"><span data-stu-id="59fdd-108">[in] The full name of the application, as defined for <xref:System.ApplicationIdentity>.</span></span>  
  
 `dwManifestPaths`  
 <span data-ttu-id="59fdd-109">de Número de cadenas contenidas en la `ppwzManifestPaths` matriz.</span><span class="sxs-lookup"><span data-stu-id="59fdd-109">[in] The number of strings contained in the `ppwzManifestPaths` array.</span></span>  
  
 `ppwzManifestPaths`  
 <span data-ttu-id="59fdd-110">[in] Opcional.</span><span class="sxs-lookup"><span data-stu-id="59fdd-110">[in] Optional.</span></span> <span data-ttu-id="59fdd-111">Matriz de cadenas que contiene las rutas de acceso de manifiesto para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="59fdd-111">A string array that contains manifest paths for the application.</span></span>  
  
 `dwActivationData`  
 <span data-ttu-id="59fdd-112">de Número de cadenas contenidas en la `ppwzActivationData` matriz.</span><span class="sxs-lookup"><span data-stu-id="59fdd-112">[in] The number of strings contained in the `ppwzActivationData` array.</span></span>  
  
 `ppwzActivationData`  
 <span data-ttu-id="59fdd-113">[in] Opcional.</span><span class="sxs-lookup"><span data-stu-id="59fdd-113">[in] Optional.</span></span> <span data-ttu-id="59fdd-114">Una matriz de cadenas que contiene los datos de activación de la aplicación, como la parte de la cadena de consulta de la dirección URL de las aplicaciones implementadas a través de la Web.</span><span class="sxs-lookup"><span data-stu-id="59fdd-114">A string array that contains the application's activation data, such as the query string portion of the URL for applications deployed over the Web.</span></span>  
  
 `pReturnValue`  
 <span data-ttu-id="59fdd-115">enuncia El valor devuelto desde el punto de entrada de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="59fdd-115">[out] The value returned from the entry point of the application.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="59fdd-116">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="59fdd-116">Return Value</span></span>  
  
|<span data-ttu-id="59fdd-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="59fdd-117">HRESULT</span></span>|<span data-ttu-id="59fdd-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="59fdd-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="59fdd-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="59fdd-119">S_OK</span></span>|<span data-ttu-id="59fdd-120">`ExecuteApplication` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="59fdd-120">`ExecuteApplication` returned successfully.</span></span>|  
|<span data-ttu-id="59fdd-121">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="59fdd-121">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="59fdd-122">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="59fdd-122">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="59fdd-123">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="59fdd-123">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="59fdd-124">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="59fdd-124">The call timed out.</span></span>|  
|<span data-ttu-id="59fdd-125">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="59fdd-125">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="59fdd-126">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="59fdd-126">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="59fdd-127">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="59fdd-127">HOST_E_ABANDONED</span></span>|<span data-ttu-id="59fdd-128">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="59fdd-128">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="59fdd-129">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="59fdd-129">E_FAIL</span></span>|<span data-ttu-id="59fdd-130">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="59fdd-130">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="59fdd-131">Si un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="59fdd-131">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="59fdd-132">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="59fdd-132">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="59fdd-133">Observaciones</span><span class="sxs-lookup"><span data-stu-id="59fdd-133">Remarks</span></span>  

 <span data-ttu-id="59fdd-134">`ExecuteApplication` se utiliza para activar las aplicaciones ClickOnce en un dominio de aplicación recién creado.</span><span class="sxs-lookup"><span data-stu-id="59fdd-134">`ExecuteApplication` is used to activate ClickOnce applications in a newly created application domain.</span></span>  
  
 <span data-ttu-id="59fdd-135">El `pReturnValue` parámetro de salida se establece en el valor devuelto por la aplicación.</span><span class="sxs-lookup"><span data-stu-id="59fdd-135">The `pReturnValue` output parameter is set to the value returned by the application.</span></span> <span data-ttu-id="59fdd-136">Si proporciona un valor null para, no `pReturnValue` `ExecuteApplication` producirá un error, pero no devolverá ningún valor.</span><span class="sxs-lookup"><span data-stu-id="59fdd-136">If you supply a value of null for `pReturnValue`, `ExecuteApplication` does not fail, but it does not return a value.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="59fdd-137">No llame al método [Start Method](iclrruntimehost-start-method.md) antes de llamar al `ExecuteApplication` método para activar una aplicación basada en manifiesto.</span><span class="sxs-lookup"><span data-stu-id="59fdd-137">Do not call the [Start Method](iclrruntimehost-start-method.md) method before calling the `ExecuteApplication` method to activate a manifest-based application.</span></span> <span data-ttu-id="59fdd-138">Si `Start` se llama primero al método, `ExecuteApplication` se producirá un error en la llamada al método.</span><span class="sxs-lookup"><span data-stu-id="59fdd-138">If the `Start` method is called first, the `ExecuteApplication` method call will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="59fdd-139">Requisitos</span><span class="sxs-lookup"><span data-stu-id="59fdd-139">Requirements</span></span>  

 <span data-ttu-id="59fdd-140">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="59fdd-140">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="59fdd-141">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="59fdd-141">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="59fdd-142">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="59fdd-142">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="59fdd-143">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="59fdd-143">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59fdd-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="59fdd-144">See also</span></span>

- <xref:System.ActivationContext>
- <xref:System.AppDomainManager>
- <xref:System.ApplicationIdentity>
- [<span data-ttu-id="59fdd-145">ICLRRuntimeHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="59fdd-145">ICLRRuntimeHost Interface</span></span>](iclrruntimehost-interface.md)
- [<span data-ttu-id="59fdd-146">Método SetAppDomainManager</span><span class="sxs-lookup"><span data-stu-id="59fdd-146">SetAppDomainManager Method</span></span>](ihostcontrol-setappdomainmanager-method.md)
- [<span data-ttu-id="59fdd-147">Tutorial: descargar ensamblados a petición con la API de implementación de ClickOnce mediante el diseñador</span><span class="sxs-lookup"><span data-stu-id="59fdd-147">Walkthrough: Downloading Assemblies on Demand with the ClickOnce Deployment API Using the Designer</span></span>](/visualstudio/deployment/walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api-using-the-designer)
