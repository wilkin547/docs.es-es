---
title: "ICLRHostProtectionManager::SetProtectedCategories (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRHostProtectionManager.SetProtectedCategories
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRHostProtectionManager::SetProtectedCategories
helpviewer_keywords:
- SetProtectedCategories method [.NET Framework hosting]
- ICLRHostProtectionManager::SetProtectedCategories method [.NET Framework hosting]
ms.assetid: fa21dc7b-5da7-440b-b59e-9180e5181f9d
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 984a88a9b75a03f421f1dd3f834665fee932876a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="iclrhostprotectionmanagersetprotectedcategories-method"></a><span data-ttu-id="2bdc9-102">ICLRHostProtectionManager::SetProtectedCategories (Método)</span><span class="sxs-lookup"><span data-stu-id="2bdc9-102">ICLRHostProtectionManager::SetProtectedCategories Method</span></span>
<span data-ttu-id="2bdc9-103">Especifica qué categorías de tipos y miembros administrados deben bloquearse de ejecución en el código de confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="2bdc9-103">Specifies which categories of managed types and members should be blocked from running in partially trusted code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2bdc9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2bdc9-104">Syntax</span></span>  
  
```  
HRESULT SetProtectedCategories (  
    [in] EApiCategories  categories  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2bdc9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2bdc9-105">Parameters</span></span>  
 `categories`  
 <span data-ttu-id="2bdc9-106">[in] Una combinación de [EApiCategories](../../../../docs/framework/unmanaged-api/hosting/eapicategories-enumeration.md) valores, que indica qué categorías de tipos y miembros administrados deben bloquearse de ejecución en el código de confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="2bdc9-106">[in] A combination of [EApiCategories](../../../../docs/framework/unmanaged-api/hosting/eapicategories-enumeration.md) values, indicating which categories of managed types and members should be blocked from running in partially trusted code.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2bdc9-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="2bdc9-107">Return Value</span></span>  
  
|<span data-ttu-id="2bdc9-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2bdc9-108">HRESULT</span></span>|<span data-ttu-id="2bdc9-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="2bdc9-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2bdc9-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="2bdc9-110">S_OK</span></span>|<span data-ttu-id="2bdc9-111">`SetProtectedCategories`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="2bdc9-111">`SetProtectedCategories` returned successfully.</span></span>|  
|<span data-ttu-id="2bdc9-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2bdc9-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2bdc9-113">Common language runtime (CLR) no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="2bdc9-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2bdc9-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2bdc9-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2bdc9-115">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="2bdc9-115">The call timed out.</span></span>|  
|<span data-ttu-id="2bdc9-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2bdc9-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2bdc9-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="2bdc9-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2bdc9-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2bdc9-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2bdc9-119">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="2bdc9-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2bdc9-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2bdc9-120">E_FAIL</span></span>|<span data-ttu-id="2bdc9-121">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="2bdc9-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2bdc9-122">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="2bdc9-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2bdc9-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="2bdc9-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2bdc9-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2bdc9-124">Remarks</span></span>  
 <span data-ttu-id="2bdc9-125">Cada `EApiCategories` valor hace referencia a una lista de tipos y miembros administrados.</span><span class="sxs-lookup"><span data-stu-id="2bdc9-125">Each `EApiCategories` value refers to a list of managed types and members.</span></span> <span data-ttu-id="2bdc9-126">El `EApiCategories` enumeración y el `SetProtectedCategories` método están directamente relacionados a los recursos administrados <xref:System.Security.Permissions.HostProtectionAttribute> (clase), que se utiliza para marcar tipos administrados y miembros que exponen funciones correspondientes a las categorías descritas por `EApiCategories`.</span><span class="sxs-lookup"><span data-stu-id="2bdc9-126">The `EApiCategories` enumeration and the `SetProtectedCategories` method are directly related to the managed <xref:System.Security.Permissions.HostProtectionAttribute> class, which is used to mark managed types and members that expose capabilities corresponding to the categories described by `EApiCategories`.</span></span> <span data-ttu-id="2bdc9-127">Para obtener más información, consulte <xref:System.Security.Permissions.HostProtectionAttribute> y <xref:System.Security.Permissions.HostProtectionResource> enumeración, que se corresponde directamente con `EApiCategories`.</span><span class="sxs-lookup"><span data-stu-id="2bdc9-127">For more information, see <xref:System.Security.Permissions.HostProtectionAttribute> and the <xref:System.Security.Permissions.HostProtectionResource> enumeration, which directly corresponds to `EApiCategories`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2bdc9-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2bdc9-128">Requirements</span></span>  
 <span data-ttu-id="2bdc9-129">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2bdc9-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2bdc9-130">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2bdc9-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2bdc9-131">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2bdc9-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2bdc9-132">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2bdc9-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2bdc9-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="2bdc9-133">See Also</span></span>  
 <xref:System.Security.Permissions.HostProtectionAttribute>  
 <xref:System.Security.Permissions.HostProtectionResource>  
 [<span data-ttu-id="2bdc9-134">EApiCategories (enumeración)</span><span class="sxs-lookup"><span data-stu-id="2bdc9-134">EApiCategories Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eapicategories-enumeration.md)  
 [<span data-ttu-id="2bdc9-135">ICLRControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2bdc9-135">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="2bdc9-136">ICLRHostProtectionManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2bdc9-136">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)
