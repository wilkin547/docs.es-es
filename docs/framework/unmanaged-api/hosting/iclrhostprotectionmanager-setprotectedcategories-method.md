---
title: ICLRHostProtectionManager::SetProtectedCategories (Método)
ms.date: 03/30/2017
api_name:
- ICLRHostProtectionManager.SetProtectedCategories
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostProtectionManager::SetProtectedCategories
helpviewer_keywords:
- SetProtectedCategories method [.NET Framework hosting]
- ICLRHostProtectionManager::SetProtectedCategories method [.NET Framework hosting]
ms.assetid: fa21dc7b-5da7-440b-b59e-9180e5181f9d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c6c93566d0909f1dbef46862760d47ede478d51a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33434543"
---
# <a name="iclrhostprotectionmanagersetprotectedcategories-method"></a><span data-ttu-id="1adc0-102">ICLRHostProtectionManager::SetProtectedCategories (Método)</span><span class="sxs-lookup"><span data-stu-id="1adc0-102">ICLRHostProtectionManager::SetProtectedCategories Method</span></span>
<span data-ttu-id="1adc0-103">Especifica qué categorías de tipos y miembros administrados deben bloquearse de ejecución en el código de confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="1adc0-103">Specifies which categories of managed types and members should be blocked from running in partially trusted code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1adc0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1adc0-104">Syntax</span></span>  
  
```  
HRESULT SetProtectedCategories (  
    [in] EApiCategories  categories  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1adc0-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1adc0-105">Parameters</span></span>  
 `categories`  
 <span data-ttu-id="1adc0-106">[in] Una combinación de [EApiCategories](../../../../docs/framework/unmanaged-api/hosting/eapicategories-enumeration.md) valores, que indica qué categorías de tipos y miembros administrados deben bloquearse de ejecución en el código de confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="1adc0-106">[in] A combination of [EApiCategories](../../../../docs/framework/unmanaged-api/hosting/eapicategories-enumeration.md) values, indicating which categories of managed types and members should be blocked from running in partially trusted code.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1adc0-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="1adc0-107">Return Value</span></span>  
  
|<span data-ttu-id="1adc0-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1adc0-108">HRESULT</span></span>|<span data-ttu-id="1adc0-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="1adc0-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1adc0-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="1adc0-110">S_OK</span></span>|<span data-ttu-id="1adc0-111">`SetProtectedCategories` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="1adc0-111">`SetProtectedCategories` returned successfully.</span></span>|  
|<span data-ttu-id="1adc0-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1adc0-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1adc0-113">Common language runtime (CLR) no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="1adc0-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1adc0-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1adc0-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1adc0-115">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="1adc0-115">The call timed out.</span></span>|  
|<span data-ttu-id="1adc0-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1adc0-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1adc0-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="1adc0-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1adc0-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1adc0-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1adc0-119">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="1adc0-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1adc0-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1adc0-120">E_FAIL</span></span>|<span data-ttu-id="1adc0-121">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="1adc0-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1adc0-122">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="1adc0-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1adc0-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="1adc0-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1adc0-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1adc0-124">Remarks</span></span>  
 <span data-ttu-id="1adc0-125">Cada `EApiCategories` valor hace referencia a una lista de tipos y miembros administrados.</span><span class="sxs-lookup"><span data-stu-id="1adc0-125">Each `EApiCategories` value refers to a list of managed types and members.</span></span> <span data-ttu-id="1adc0-126">El `EApiCategories` enumeración y el `SetProtectedCategories` método están directamente relacionados a los recursos administrados <xref:System.Security.Permissions.HostProtectionAttribute> (clase), que se utiliza para marcar tipos administrados y miembros que exponen funciones correspondientes a las categorías descritas por `EApiCategories`.</span><span class="sxs-lookup"><span data-stu-id="1adc0-126">The `EApiCategories` enumeration and the `SetProtectedCategories` method are directly related to the managed <xref:System.Security.Permissions.HostProtectionAttribute> class, which is used to mark managed types and members that expose capabilities corresponding to the categories described by `EApiCategories`.</span></span> <span data-ttu-id="1adc0-127">Para obtener más información, consulte <xref:System.Security.Permissions.HostProtectionAttribute> y <xref:System.Security.Permissions.HostProtectionResource> enumeración, que se corresponde directamente con `EApiCategories`.</span><span class="sxs-lookup"><span data-stu-id="1adc0-127">For more information, see <xref:System.Security.Permissions.HostProtectionAttribute> and the <xref:System.Security.Permissions.HostProtectionResource> enumeration, which directly corresponds to `EApiCategories`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1adc0-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1adc0-128">Requirements</span></span>  
 <span data-ttu-id="1adc0-129">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1adc0-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1adc0-130">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1adc0-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1adc0-131">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1adc0-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1adc0-132">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1adc0-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1adc0-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="1adc0-133">See Also</span></span>  
 <xref:System.Security.Permissions.HostProtectionAttribute>  
 <xref:System.Security.Permissions.HostProtectionResource>  
 [<span data-ttu-id="1adc0-134">EApiCategories (enumeración)</span><span class="sxs-lookup"><span data-stu-id="1adc0-134">EApiCategories Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eapicategories-enumeration.md)  
 [<span data-ttu-id="1adc0-135">ICLRControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1adc0-135">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="1adc0-136">ICLRHostProtectionManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1adc0-136">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)
