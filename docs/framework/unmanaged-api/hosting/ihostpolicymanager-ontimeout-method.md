---
title: IHostPolicyManager::OnTimeout (Método)
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ad1a9bc6b2e5c84f15cf0cf706504f18341f8584
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59209182"
---
# <a name="ihostpolicymanagerontimeout-method"></a><span data-ttu-id="1ae8b-102">IHostPolicyManager::OnTimeout (Método)</span><span class="sxs-lookup"><span data-stu-id="1ae8b-102">IHostPolicyManager::OnTimeout Method</span></span>
<span data-ttu-id="1ae8b-103">Notifica al host que common language runtime (CLR) está a punto de realizar la acción especificada por una llamada a la [ICLRPolicyManager:: SetActionOnTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md) método en respuesta a un tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="1ae8b-103">Notifies the host that the common language runtime (CLR) is about to take the action specified by a call to the [ICLRPolicyManager::SetActionOnTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-setactionontimeout-method.md) method in response to a timeout.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ae8b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1ae8b-104">Syntax</span></span>  
  
```  
HRESULT OnTimeout (  
    [in] EClrOperation  operation,   
    [in] EPolicyAction  action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1ae8b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1ae8b-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="1ae8b-106">[in] Uno de los [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) valores, que indica el tipo de operación que se agotó el tiempo.</span><span class="sxs-lookup"><span data-stu-id="1ae8b-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the kind of operation that timed out.</span></span>  
  
 `action`  
 <span data-ttu-id="1ae8b-107">[in] Uno de los [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) valores, que indica la acción de CLR está realizando en respuesta al tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="1ae8b-107">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the action the CLR is taking in response to the timeout.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1ae8b-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="1ae8b-108">Return Value</span></span>  
  
|<span data-ttu-id="1ae8b-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1ae8b-109">HRESULT</span></span>|<span data-ttu-id="1ae8b-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="1ae8b-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1ae8b-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="1ae8b-111">S_OK</span></span>|<span data-ttu-id="1ae8b-112">`OnTimeout` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="1ae8b-112">`OnTimeout` returned successfully.</span></span>|  
|<span data-ttu-id="1ae8b-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1ae8b-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1ae8b-114">El CLR no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="1ae8b-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1ae8b-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1ae8b-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1ae8b-116">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="1ae8b-116">The call timed out.</span></span>|  
|<span data-ttu-id="1ae8b-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1ae8b-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1ae8b-118">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="1ae8b-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1ae8b-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1ae8b-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1ae8b-120">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="1ae8b-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1ae8b-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1ae8b-121">E_FAIL</span></span>|<span data-ttu-id="1ae8b-122">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="1ae8b-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1ae8b-123">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="1ae8b-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1ae8b-124">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="1ae8b-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1ae8b-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1ae8b-125">Requirements</span></span>  
 <span data-ttu-id="1ae8b-126">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1ae8b-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1ae8b-127">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1ae8b-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1ae8b-128">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1ae8b-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1ae8b-129">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1ae8b-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ae8b-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="1ae8b-130">See also</span></span>

- [<span data-ttu-id="1ae8b-131">EClrOperation (enumeración)</span><span class="sxs-lookup"><span data-stu-id="1ae8b-131">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="1ae8b-132">EPolicyAction (enumeración)</span><span class="sxs-lookup"><span data-stu-id="1ae8b-132">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="1ae8b-133">ICLRPolicyManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1ae8b-133">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="1ae8b-134">IHostPolicyManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1ae8b-134">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
