---
title: ICLRPolicyManager::SetTimeout (Método)
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager.SetTimeout
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager::SetTimeout
helpviewer_keywords:
- SetTimeout method [.NET Framework hosting]
- ICLRPolicyManager::SetTimeout method [.NET Framework hosting]
ms.assetid: 954404fd-d52d-4e68-b582-8692f3a5f608
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1e367fc772c5b673795c8229f9084fac850d53a8
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57474819"
---
# <a name="iclrpolicymanagersettimeout-method"></a><span data-ttu-id="3d8ad-102">ICLRPolicyManager::SetTimeout (Método)</span><span class="sxs-lookup"><span data-stu-id="3d8ad-102">ICLRPolicyManager::SetTimeout Method</span></span>
<span data-ttu-id="3d8ad-103">Establece un valor de tiempo de espera para la operación especificada.</span><span class="sxs-lookup"><span data-stu-id="3d8ad-103">Sets a timeout value for the specified operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d8ad-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3d8ad-104">Syntax</span></span>  
  
```  
HRESULT SetTimeout (  
    [in] EClrOperation operation,  
    [in] DWORD dsMilliseconds  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3d8ad-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3d8ad-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="3d8ad-106">[in] Uno de los [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) valores, que indica la operación de common language runtime (CLR) que se va a establecer un tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="3d8ad-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the common language runtime (CLR) operation for which to set a timeout.</span></span> <span data-ttu-id="3d8ad-107">Se admiten los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="3d8ad-107">The following values are supported:</span></span>  
  
-   <span data-ttu-id="3d8ad-108">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="3d8ad-108">OPR_AppDomainUnload</span></span>  
  
-   <span data-ttu-id="3d8ad-109">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="3d8ad-109">OPR_ProcessExit</span></span>  
  
-   <span data-ttu-id="3d8ad-110">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="3d8ad-110">OPR_ThreadRudeAbortInCriticalRegion</span></span>  
  
-   <span data-ttu-id="3d8ad-111">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="3d8ad-111">OPR_ThreadRudeAbortInNonCriticalRegion</span></span>  
  
 `dwMilliseconds`  
 <span data-ttu-id="3d8ad-112">[in] El nuevo valor de tiempo de espera, en milisegundos.</span><span class="sxs-lookup"><span data-stu-id="3d8ad-112">[in] The new timeout value, in milliseconds.</span></span> <span data-ttu-id="3d8ad-113">Un valor de infinito, la operación nunca al tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="3d8ad-113">A value of INFINITE causes the operation never to time out.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3d8ad-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="3d8ad-114">Return Value</span></span>  
  
|<span data-ttu-id="3d8ad-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3d8ad-115">HRESULT</span></span>|<span data-ttu-id="3d8ad-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="3d8ad-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3d8ad-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="3d8ad-117">S_OK</span></span>|<span data-ttu-id="3d8ad-118">`SetTimeout` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="3d8ad-118">`SetTimeout` returned successfully.</span></span>|  
|<span data-ttu-id="3d8ad-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3d8ad-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3d8ad-120">El CLR no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="3d8ad-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3d8ad-121">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3d8ad-121">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3d8ad-122">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="3d8ad-122">The call timed out.</span></span>|  
|<span data-ttu-id="3d8ad-123">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3d8ad-123">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3d8ad-124">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="3d8ad-124">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3d8ad-125">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3d8ad-125">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3d8ad-126">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="3d8ad-126">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3d8ad-127">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3d8ad-127">E_FAIL</span></span>|<span data-ttu-id="3d8ad-128">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="3d8ad-128">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3d8ad-129">Después de un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="3d8ad-129">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3d8ad-130">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="3d8ad-130">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="3d8ad-131">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="3d8ad-131">E_INVALIDARG</span></span>|<span data-ttu-id="3d8ad-132">No se puede establecer un tiempo de espera para el elemento especificado `operation`, o se ha proporcionado un valor no válido para `operation`.</span><span class="sxs-lookup"><span data-stu-id="3d8ad-132">A timeout cannot be set for the specified `operation`, or an invalid value was supplied for `operation`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3d8ad-133">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3d8ad-133">Requirements</span></span>  
 <span data-ttu-id="3d8ad-134">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3d8ad-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3d8ad-135">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3d8ad-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3d8ad-136">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3d8ad-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3d8ad-137">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3d8ad-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d8ad-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="3d8ad-138">See also</span></span>
- [<span data-ttu-id="3d8ad-139">EClrOperation (enumeración)</span><span class="sxs-lookup"><span data-stu-id="3d8ad-139">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="3d8ad-140">ICLRControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3d8ad-140">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="3d8ad-141">ICLRPolicyManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3d8ad-141">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
