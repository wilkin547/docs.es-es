---
title: "ICLRControl::GetCLRManager (Método)"
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
- ICLRControl.GetCLRManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRControl::GetCLRManager
helpviewer_keywords:
- GetCLRManager method [.NET Framework hosting]
- ICLRControl::GetCLRManager method [.NET Framework hosting]
ms.assetid: 8a11bfa4-cbb0-4082-82b5-f9fba66c93f5
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 197a3818de8d0b17331a9f9ac422ecaabb230a50
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="iclrcontrolgetclrmanager-method"></a><span data-ttu-id="43540-102">ICLRControl::GetCLRManager (Método)</span><span class="sxs-lookup"><span data-stu-id="43540-102">ICLRControl::GetCLRManager Method</span></span>
<span data-ttu-id="43540-103">Obtiene un puntero de interfaz a una instancia de cualquiera de los tipos de administrador que el host puede utilizar para configurar common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="43540-103">Gets an interface pointer to an instance of any of the manager types the host can use to configure the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43540-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="43540-104">Syntax</span></span>  
  
```  
HRESULT GetCLRManager (  
    [in]  REFIID  riid,  
    [out] void  **ppObject  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="43540-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="43540-105">Parameters</span></span>  
 `riid`  
 <span data-ttu-id="43540-106">[in] El `IID` del tipo de administrador que se devuelve.</span><span class="sxs-lookup"><span data-stu-id="43540-106">[in] The `IID` of the manager type to return.</span></span> <span data-ttu-id="43540-107">Los siguientes `IID` se admiten valores.</span><span class="sxs-lookup"><span data-stu-id="43540-107">The following `IID` values are supported.</span></span>  
  
-   <span data-ttu-id="43540-108">IID_ICLRDebugManager: Especifica que `ppObject` será del tipo [ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="43540-108">IID_ICLRDebugManager: Specifies that `ppObject` will be of type [ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md).</span></span>  
  
-   <span data-ttu-id="43540-109">IID_ICLRErrorReportingManager: Especifica que `ppObject` será del tipo [ICLRErrorReportingManager](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="43540-109">IID_ICLRErrorReportingManager: Specifies that `ppObject` will be of type [ICLRErrorReportingManager](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md).</span></span>  
  
-   <span data-ttu-id="43540-110">IID_ICLRGCManager: Especifica que `ppObject` será del tipo [ICLRGCManager](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="43540-110">IID_ICLRGCManager: Specifies that `ppObject` will be of type [ICLRGCManager](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md).</span></span>  
  
-   <span data-ttu-id="43540-111">IID_ICLRHostProtectionManager: Especifica que `ppObject` será del tipo [ICLRHostProtectionManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="43540-111">IID_ICLRHostProtectionManager: Specifies that `ppObject` will be of type [ICLRHostProtectionManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md).</span></span>  
  
-   <span data-ttu-id="43540-112">IID_ICLROnEventManager: Especifica que `ppObject` será del tipo [ICLROnEventManager](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="43540-112">IID_ICLROnEventManager: Specifies that `ppObject` will be of type [ICLROnEventManager](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md).</span></span>  
  
-   <span data-ttu-id="43540-113">IID_ICLRPolicyManager: Especifica que `ppObject` será del tipo [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="43540-113">IID_ICLRPolicyManager: Specifies that `ppObject` will be of type [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md).</span></span>  
  
-   <span data-ttu-id="43540-114">IID_ICLRTaskManager: Especifica que `ppObject` será del tipo [ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="43540-114">IID_ICLRTaskManager: speciries that `ppObject` will be of type [ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md).</span></span>  
  
 `ppObject`  
 <span data-ttu-id="43540-115">[out] Un puntero de interfaz al administrador solicitado, o null, si se ha solicitado un tipo de administrador no válido.</span><span class="sxs-lookup"><span data-stu-id="43540-115">[out] An interface pointer to the requested manager, or null, if an invalid manager type was requested.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="43540-116">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="43540-116">Return Value</span></span>  
  
|<span data-ttu-id="43540-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="43540-117">HRESULT</span></span>|<span data-ttu-id="43540-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="43540-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="43540-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="43540-119">S_OK</span></span>|<span data-ttu-id="43540-120">El método se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="43540-120">The method returned successfully.</span></span>|  
|<span data-ttu-id="43540-121">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="43540-121">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="43540-122">El CLR no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="43540-122">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="43540-123">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="43540-123">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="43540-124">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="43540-124">The call timed out.</span></span>|  
|<span data-ttu-id="43540-125">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="43540-125">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="43540-126">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="43540-126">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="43540-127">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="43540-127">HOST_E_ABANDONED</span></span>|<span data-ttu-id="43540-128">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="43540-128">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="43540-129">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="43540-129">E_FAIL</span></span>|<span data-ttu-id="43540-130">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="43540-130">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="43540-131">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="43540-131">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="43540-132">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="43540-132">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="43540-133">E_NOINTERFACE</span><span class="sxs-lookup"><span data-stu-id="43540-133">E_NOINTERFACE</span></span>|<span data-ttu-id="43540-134">No se admite el tipo de interfaz.</span><span class="sxs-lookup"><span data-stu-id="43540-134">The interface type is not supported.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="43540-135">Requisitos</span><span class="sxs-lookup"><span data-stu-id="43540-135">Requirements</span></span>  
 <span data-ttu-id="43540-136">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="43540-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43540-137">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="43540-137">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="43540-138">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="43540-138">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="43540-139">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43540-139">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43540-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="43540-140">See Also</span></span>  
 [<span data-ttu-id="43540-141">ICLRControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="43540-141">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="43540-142">IHostControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="43540-142">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
