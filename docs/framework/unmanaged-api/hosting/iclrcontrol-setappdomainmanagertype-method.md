---
title: ICLRControl::SetAppDomainManagerType (Método)
ms.date: 03/30/2017
api_name:
- ICLRControl.SetAppDomainManagerType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRControl::SetAppDomainManagerType
helpviewer_keywords:
- SetAppDomainManagerType method, ICLRControl interface [.NET Framework hosting]
- ICLRControl::SetAppDomainManagerType method [.NET Framework hosting]
ms.assetid: ec57828b-2aad-496d-a35a-e45d4bd7fe77
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: be778fed910b2cbdbf5e9ae7754abae437ef6bec
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33433739"
---
# <a name="iclrcontrolsetappdomainmanagertype-method"></a><span data-ttu-id="7e5c6-102">ICLRControl::SetAppDomainManagerType (Método)</span><span class="sxs-lookup"><span data-stu-id="7e5c6-102">ICLRControl::SetAppDomainManagerType Method</span></span>
<span data-ttu-id="7e5c6-103">Establece un tipo derivado de <xref:System.AppDomainManager> como el tipo para los administradores de dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="7e5c6-103">Sets a type derived from <xref:System.AppDomainManager> as the type for application domain managers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e5c6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7e5c6-104">Syntax</span></span>  
  
```  
HRESULT SetAppDomainManagerType (  
    [in] LPCWSTR pwzAppDomainManagerAssembly,  
    [in] LPCWSTR pwzAppDomainManagerType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7e5c6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7e5c6-105">Parameters</span></span>  
 `pwzAppDomainManagerAssembly`  
 <span data-ttu-id="7e5c6-106">[in] El nombre del ensamblado en el que se deriva el tipo solicitado de <xref:System.AppDomainManager> se implementa.</span><span class="sxs-lookup"><span data-stu-id="7e5c6-106">[in] The name of the assembly in which the requested type derived from <xref:System.AppDomainManager> is implemented.</span></span>  
  
 `pwzAppDomainManagerType`  
 <span data-ttu-id="7e5c6-107">[in] El nombre del tipo implementado en el `pwzAppDomainManagerAssembly` parámetro que implementa las capacidades de <xref:System.AppDomainManager>.</span><span class="sxs-lookup"><span data-stu-id="7e5c6-107">[in] The name of the type implemented in the `pwzAppDomainManagerAssembly` parameter that implements the capabilities of <xref:System.AppDomainManager>.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7e5c6-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="7e5c6-108">Return Value</span></span>  
  
|<span data-ttu-id="7e5c6-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7e5c6-109">HRESULT</span></span>|<span data-ttu-id="7e5c6-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="7e5c6-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7e5c6-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="7e5c6-111">S_OK</span></span>|<span data-ttu-id="7e5c6-112">El método se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="7e5c6-112">The method returned successfully.</span></span>|  
|<span data-ttu-id="7e5c6-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7e5c6-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7e5c6-114">Common language runtime (CLR) no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="7e5c6-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7e5c6-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7e5c6-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7e5c6-116">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="7e5c6-116">The call timed out.</span></span>|  
|<span data-ttu-id="7e5c6-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7e5c6-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7e5c6-118">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="7e5c6-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7e5c6-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7e5c6-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7e5c6-120">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="7e5c6-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7e5c6-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7e5c6-121">E_FAIL</span></span>|<span data-ttu-id="7e5c6-122">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="7e5c6-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7e5c6-123">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="7e5c6-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7e5c6-124">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="7e5c6-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7e5c6-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7e5c6-125">Requirements</span></span>  
 <span data-ttu-id="7e5c6-126">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7e5c6-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7e5c6-127">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7e5c6-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7e5c6-128">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7e5c6-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7e5c6-129">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7e5c6-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e5c6-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="7e5c6-130">See Also</span></span>  
 [<span data-ttu-id="7e5c6-131">ICLRControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7e5c6-131">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="7e5c6-132">IHostControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7e5c6-132">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
