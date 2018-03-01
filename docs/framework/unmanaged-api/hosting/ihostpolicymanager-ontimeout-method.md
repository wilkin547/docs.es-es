---
title: "IHostPolicyManager::OnTimeout (Método)"
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
- IHostPolicyManager.OnTimeout
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostPolicyManager::OnTimeout
helpviewer_keywords:
- IHostPolicyManager::OnTimeout method [.NET Framework hosting]
- OnTimeout method [.NET Framework hosting]
ms.assetid: 0a313b51-5e4d-4714-a86b-af75cf3902e6
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 6b8c29bc281b64368e8b310e2b13f3fcb1bdc6ff
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ihostpolicymanagerontimeout-method"></a><span data-ttu-id="ddf15-102">IHostPolicyManager::OnTimeout (Método)</span><span class="sxs-lookup"><span data-stu-id="ddf15-102">IHostPolicyManager::OnTimeout Method</span></span>
<span data-ttu-id="ddf15-103">Notifica al host que common language runtime (CLR) está a punto de realizar la acción especificada por una llamada a la [ICLRPolicyManager:: SetActionOnTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md) método en respuesta a un tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="ddf15-103">Notifies the host that the common language runtime (CLR) is about to take the action specified by a call to the [ICLRPolicyManager::SetActionOnTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md) method in response to a timeout.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ddf15-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ddf15-104">Syntax</span></span>  
  
```  
HRESULT OnTimeout (  
    [in] EClrOperation  operation,   
    [in] EPolicyAction  action  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ddf15-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ddf15-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="ddf15-106">[in] Uno de los [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) valores, que indica el tipo de operación que se agotó el tiempo.</span><span class="sxs-lookup"><span data-stu-id="ddf15-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the kind of operation that timed out.</span></span>  
  
 `action`  
 <span data-ttu-id="ddf15-107">[in] Uno de los [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) valores, que indica la acción CLR está realizando en respuesta al tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="ddf15-107">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the action the CLR is taking in response to the timeout.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ddf15-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ddf15-108">Return Value</span></span>  
  
|<span data-ttu-id="ddf15-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ddf15-109">HRESULT</span></span>|<span data-ttu-id="ddf15-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="ddf15-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ddf15-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="ddf15-111">S_OK</span></span>|<span data-ttu-id="ddf15-112">`OnTimeout`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="ddf15-112">`OnTimeout` returned successfully.</span></span>|  
|<span data-ttu-id="ddf15-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ddf15-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ddf15-114">El CLR no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="ddf15-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ddf15-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ddf15-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ddf15-116">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="ddf15-116">The call timed out.</span></span>|  
|<span data-ttu-id="ddf15-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ddf15-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ddf15-118">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="ddf15-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ddf15-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ddf15-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ddf15-120">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="ddf15-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ddf15-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ddf15-121">E_FAIL</span></span>|<span data-ttu-id="ddf15-122">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="ddf15-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ddf15-123">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="ddf15-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ddf15-124">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="ddf15-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ddf15-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ddf15-125">Requirements</span></span>  
 <span data-ttu-id="ddf15-126">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ddf15-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ddf15-127">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ddf15-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ddf15-128">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ddf15-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ddf15-129">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ddf15-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ddf15-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="ddf15-130">See Also</span></span>  
 [<span data-ttu-id="ddf15-131">EClrOperation (enumeración)</span><span class="sxs-lookup"><span data-stu-id="ddf15-131">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)  
 [<span data-ttu-id="ddf15-132">EPolicyAction (enumeración)</span><span class="sxs-lookup"><span data-stu-id="ddf15-132">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)  
 [<span data-ttu-id="ddf15-133">ICLRPolicyManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ddf15-133">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)  
 [<span data-ttu-id="ddf15-134">IHostPolicyManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ddf15-134">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
