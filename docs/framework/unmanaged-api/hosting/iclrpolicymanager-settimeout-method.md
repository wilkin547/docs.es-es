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
ms.openlocfilehash: 5b5a389af718322d1e0fffebae046bf28731877b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33435782"
---
# <a name="iclrpolicymanagersettimeout-method"></a><span data-ttu-id="8a09c-102">ICLRPolicyManager::SetTimeout (Método)</span><span class="sxs-lookup"><span data-stu-id="8a09c-102">ICLRPolicyManager::SetTimeout Method</span></span>
<span data-ttu-id="8a09c-103">Establece un valor de tiempo de espera para la operación especificada.</span><span class="sxs-lookup"><span data-stu-id="8a09c-103">Sets a timeout value for the specified operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a09c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8a09c-104">Syntax</span></span>  
  
```  
HRESULT SetTimeout (  
    [in] EClrOperation operation,  
    [in] DWORD dsMilliseconds  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8a09c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8a09c-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="8a09c-106">[in] Uno de los [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) valores, que indica la operación de common language runtime (CLR) para el que se va a establecer un tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="8a09c-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the common language runtime (CLR) operation for which to set a timeout.</span></span> <span data-ttu-id="8a09c-107">Se admiten los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="8a09c-107">The following values are supported:</span></span>  
  
-   <span data-ttu-id="8a09c-108">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="8a09c-108">OPR_AppDomainUnload</span></span>  
  
-   <span data-ttu-id="8a09c-109">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="8a09c-109">OPR_ProcessExit</span></span>  
  
-   <span data-ttu-id="8a09c-110">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="8a09c-110">OPR_ThreadRudeAbortInCriticalRegion</span></span>  
  
-   <span data-ttu-id="8a09c-111">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="8a09c-111">OPR_ThreadRudeAbortInNonCriticalRegion</span></span>  
  
 `dwMilliseconds`  
 <span data-ttu-id="8a09c-112">[in] El nuevo valor de tiempo de espera, en milisegundos.</span><span class="sxs-lookup"><span data-stu-id="8a09c-112">[in] The new timeout value, in milliseconds.</span></span> <span data-ttu-id="8a09c-113">Un valor de INFINITE hace que la operación nunca al tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="8a09c-113">A value of INFINITE causes the operation never to time out.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8a09c-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="8a09c-114">Return Value</span></span>  
  
|<span data-ttu-id="8a09c-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8a09c-115">HRESULT</span></span>|<span data-ttu-id="8a09c-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="8a09c-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8a09c-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="8a09c-117">S_OK</span></span>|<span data-ttu-id="8a09c-118">`SetTimeout` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="8a09c-118">`SetTimeout` returned successfully.</span></span>|  
|<span data-ttu-id="8a09c-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8a09c-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8a09c-120">El CLR no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="8a09c-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="8a09c-121">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="8a09c-121">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="8a09c-122">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="8a09c-122">The call timed out.</span></span>|  
|<span data-ttu-id="8a09c-123">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="8a09c-123">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="8a09c-124">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="8a09c-124">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="8a09c-125">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="8a09c-125">HOST_E_ABANDONED</span></span>|<span data-ttu-id="8a09c-126">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="8a09c-126">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="8a09c-127">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8a09c-127">E_FAIL</span></span>|<span data-ttu-id="8a09c-128">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="8a09c-128">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="8a09c-129">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="8a09c-129">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="8a09c-130">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="8a09c-130">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="8a09c-131">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="8a09c-131">E_INVALIDARG</span></span>|<span data-ttu-id="8a09c-132">No se puede establecer un tiempo de espera para el elemento especificado `operation`, o se ha proporcionado un valor no válido para `operation`.</span><span class="sxs-lookup"><span data-stu-id="8a09c-132">A timeout cannot be set for the specified `operation`, or an invalid value was supplied for `operation`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8a09c-133">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8a09c-133">Requirements</span></span>  
 <span data-ttu-id="8a09c-134">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8a09c-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a09c-135">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8a09c-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8a09c-136">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8a09c-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8a09c-137">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a09c-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a09c-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="8a09c-138">See Also</span></span>  
 [<span data-ttu-id="8a09c-139">EClrOperation (enumeración)</span><span class="sxs-lookup"><span data-stu-id="8a09c-139">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)  
 [<span data-ttu-id="8a09c-140">ICLRControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8a09c-140">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="8a09c-141">ICLRPolicyManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8a09c-141">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
