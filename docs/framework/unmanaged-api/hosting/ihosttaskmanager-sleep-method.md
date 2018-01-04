---
title: "IHostTaskManager::Sleep (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostTaskManager.Sleep
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostTaskManager::Sleep
helpviewer_keywords:
- IHostTaskManager::Sleep method [.NET Framework hosting]
- Sleep method, IHostTaskManager interface [.NET Framework hosting]
ms.assetid: f67d25f3-9199-4c5f-b1e8-1c819243cfd5
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b7e51dcd0d5becd0d87850ae542ac437ad651f33
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ihosttaskmanagersleep-method"></a><span data-ttu-id="fdce6-102">IHostTaskManager::Sleep (Método)</span><span class="sxs-lookup"><span data-stu-id="fdce6-102">IHostTaskManager::Sleep Method</span></span>
<span data-ttu-id="fdce6-103">Notifica al host que la tarea actual se va a suspender.</span><span class="sxs-lookup"><span data-stu-id="fdce6-103">Notifies the host that the current task is going to sleep.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fdce6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fdce6-104">Syntax</span></span>  
  
```  
HRESULT Sleep (  
    [in] DWORD dwMilliseconds,  
    [in] DWORD option  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fdce6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fdce6-105">Parameters</span></span>  
 `dwMilliseconds`  
 <span data-ttu-id="fdce6-106">[in] El intervalo de tiempo, en milisegundos, que el subproceso se suspenderá.</span><span class="sxs-lookup"><span data-stu-id="fdce6-106">[in] The time interval, in milliseconds, that the thread will sleep.</span></span>  
  
 `option`  
 <span data-ttu-id="fdce6-107">[in] Uno de los [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) valores de enumeración, que indica qué acción debe realizar el host si esta acción se bloquea.</span><span class="sxs-lookup"><span data-stu-id="fdce6-107">[in] One of the [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) enumeration values, indicating what action the host should take if this action blocks.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fdce6-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="fdce6-108">Return Value</span></span>  
  
|<span data-ttu-id="fdce6-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fdce6-109">HRESULT</span></span>|<span data-ttu-id="fdce6-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="fdce6-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fdce6-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="fdce6-111">S_OK</span></span>|<span data-ttu-id="fdce6-112">`Sleep`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="fdce6-112">`Sleep` returned successfully.</span></span>|  
|<span data-ttu-id="fdce6-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="fdce6-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="fdce6-114">Common language runtime (CLR) no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="fdce6-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="fdce6-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="fdce6-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="fdce6-116">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="fdce6-116">The call timed out.</span></span>|  
|<span data-ttu-id="fdce6-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="fdce6-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="fdce6-118">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="fdce6-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="fdce6-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="fdce6-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="fdce6-120">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="fdce6-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="fdce6-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="fdce6-121">E_FAIL</span></span>|<span data-ttu-id="fdce6-122">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="fdce6-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="fdce6-123">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="fdce6-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="fdce6-124">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="fdce6-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fdce6-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fdce6-125">Remarks</span></span>  
 <span data-ttu-id="fdce6-126">CLR llama normalmente `IHostTaskManager::Sleep` cuando <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> se llama desde código de usuario.</span><span class="sxs-lookup"><span data-stu-id="fdce6-126">The CLR typically calls `IHostTaskManager::Sleep` when <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> is called from user code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fdce6-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fdce6-127">Requirements</span></span>  
 <span data-ttu-id="fdce6-128">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fdce6-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fdce6-129">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="fdce6-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fdce6-130">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fdce6-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fdce6-131">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fdce6-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdce6-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="fdce6-132">See Also</span></span>  
 [<span data-ttu-id="fdce6-133">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="fdce6-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="fdce6-134">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="fdce6-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="fdce6-135">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="fdce6-135">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="fdce6-136">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="fdce6-136">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
