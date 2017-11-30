---
title: "IHostPolicyManager::OnDefaultAction (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostPolicyManager.OnDefaultAction
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostPolicyManager::OnDefaultAction
helpviewer_keywords:
- OnDefaultAction method [.NET Framework hosting]
- IHostPolicyManager::OnDefaultAction method [.NET Framework hosting]
ms.assetid: 071e73bd-4795-470f-9373-cfaef553b7f2
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ca5eb767c08733980c9156d04526594c62349624
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ihostpolicymanagerondefaultaction-method"></a><span data-ttu-id="28d70-102">IHostPolicyManager::OnDefaultAction (Método)</span><span class="sxs-lookup"><span data-stu-id="28d70-102">IHostPolicyManager::OnDefaultAction Method</span></span>
<span data-ttu-id="28d70-103">Notifica al host que common language runtime (CLR) está a punto de realizar la acción predeterminada que se establece mediante una llamada a la [ICLRPolicyManager:: SetDefaultAction](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md) método en respuesta a una anulación del subproceso o <xref:System.AppDomain> descargar.</span><span class="sxs-lookup"><span data-stu-id="28d70-103">Notifies the host that the common language runtime (CLR) is about to take the default action that was set by a call to the [ICLRPolicyManager::SetDefaultAction](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setdefaultaction-method.md) method in response to a thread abort or <xref:System.AppDomain> unload.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28d70-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="28d70-104">Syntax</span></span>  
  
```  
HRESULT OnDefaultAction (  
    [in] EClrOperation  operation,   
    [in] EPolicyAction  action  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="28d70-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="28d70-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="28d70-106">[in] Uno de los [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) valores, que indica el tipo de evento al que está respondiendo CLR.</span><span class="sxs-lookup"><span data-stu-id="28d70-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the kind of event to which the CLR is responding.</span></span>  
  
 `action`  
 <span data-ttu-id="28d70-107">[in] Uno de los [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) valores, que indica la acción que está realizando CLR en respuesta al evento.</span><span class="sxs-lookup"><span data-stu-id="28d70-107">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the action that the CLR is taking in response to the event.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="28d70-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="28d70-108">Return Value</span></span>  
  
|<span data-ttu-id="28d70-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="28d70-109">HRESULT</span></span>|<span data-ttu-id="28d70-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="28d70-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="28d70-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="28d70-111">S_OK</span></span>|<span data-ttu-id="28d70-112">`OnDefaultAction`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="28d70-112">`OnDefaultAction` returned successfully.</span></span>|  
|<span data-ttu-id="28d70-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="28d70-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="28d70-114">El CLR no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada.</span><span class="sxs-lookup"><span data-stu-id="28d70-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call.</span></span> <span data-ttu-id="28d70-115">correctamente</span><span class="sxs-lookup"><span data-stu-id="28d70-115">successfully</span></span>|  
|<span data-ttu-id="28d70-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="28d70-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="28d70-117">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="28d70-117">The call timed out.</span></span>|  
|<span data-ttu-id="28d70-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="28d70-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="28d70-119">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="28d70-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="28d70-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="28d70-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="28d70-121">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="28d70-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="28d70-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="28d70-122">E_FAIL</span></span>|<span data-ttu-id="28d70-123">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="28d70-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="28d70-124">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="28d70-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="28d70-125">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="28d70-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="28d70-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="28d70-126">Requirements</span></span>  
 <span data-ttu-id="28d70-127">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="28d70-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="28d70-128">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="28d70-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="28d70-129">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="28d70-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="28d70-130">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="28d70-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28d70-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="28d70-131">See Also</span></span>  
 [<span data-ttu-id="28d70-132">EClrOperation (enumeración)</span><span class="sxs-lookup"><span data-stu-id="28d70-132">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)  
 [<span data-ttu-id="28d70-133">EPolicyAction (enumeración)</span><span class="sxs-lookup"><span data-stu-id="28d70-133">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)  
 [<span data-ttu-id="28d70-134">ICLRPolicyManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="28d70-134">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 [<span data-ttu-id="28d70-135">IHostPolicyManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="28d70-135">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
