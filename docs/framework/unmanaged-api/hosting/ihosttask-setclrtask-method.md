---
title: IHostTask::SetCLRTask (Método)
ms.date: 03/30/2017
api_name:
- IHostTask.SetCLRTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask::SetCLRTask
helpviewer_keywords:
- SetCLRTask method [.NET Framework hosting]
- IHostTask::SetCLRTask method [.NET Framework hosting]
ms.assetid: e9d39c80-41a1-49e7-bb5e-ea3433bfb5d7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2149293989136e0b006f044c925353efbfd94031
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33442805"
---
# <a name="ihosttasksetclrtask-method"></a><span data-ttu-id="7df1f-102">IHostTask::SetCLRTask (Método)</span><span class="sxs-lookup"><span data-stu-id="7df1f-102">IHostTask::SetCLRTask Method</span></span>
<span data-ttu-id="7df1f-103">Asocia un `ICLRTask` instancia con el actual [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instancia.</span><span class="sxs-lookup"><span data-stu-id="7df1f-103">Associates an `ICLRTask` instance with the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7df1f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7df1f-104">Syntax</span></span>  
  
```  
HRESULT SetCLRTask (  
    [in] ICLRTask *pCLRTask  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7df1f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7df1f-105">Parameters</span></span>  
 `pCLRTask`  
 <span data-ttu-id="7df1f-106">[in] Un puntero de interfaz a la `ICLRTask` instancia que se asociará con el actual `IHostTask` instancia.</span><span class="sxs-lookup"><span data-stu-id="7df1f-106">[in] An interface pointer to the `ICLRTask` instance to be associated with the current `IHostTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7df1f-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="7df1f-107">Return Value</span></span>  
  
|<span data-ttu-id="7df1f-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7df1f-108">HRESULT</span></span>|<span data-ttu-id="7df1f-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="7df1f-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7df1f-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="7df1f-110">S_OK</span></span>|<span data-ttu-id="7df1f-111">`SetCLRTask` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="7df1f-111">`SetCLRTask` returned successfully.</span></span>|  
|<span data-ttu-id="7df1f-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7df1f-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7df1f-113">Common language runtime (CLR) no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="7df1f-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7df1f-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7df1f-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7df1f-115">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="7df1f-115">The call timed out.</span></span>|  
|<span data-ttu-id="7df1f-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7df1f-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7df1f-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="7df1f-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7df1f-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7df1f-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7df1f-119">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="7df1f-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7df1f-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7df1f-120">E_FAIL</span></span>|<span data-ttu-id="7df1f-121">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="7df1f-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7df1f-122">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="7df1f-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7df1f-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="7df1f-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7df1f-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7df1f-124">Remarks</span></span>  
 <span data-ttu-id="7df1f-125">CLR llama `SetCLRTask` para asociar un `ICLRTask` instancia con el actual `IHostTask` instancia, que se creó mediante una llamada a [IHostTaskManager:: CreateTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-createtask-method.md).</span><span class="sxs-lookup"><span data-stu-id="7df1f-125">The CLR calls `SetCLRTask` to associate an `ICLRTask` instance with the current `IHostTask` instance, which was created by a call to [IHostTaskManager::CreateTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-createtask-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7df1f-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7df1f-126">Requirements</span></span>  
 <span data-ttu-id="7df1f-127">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7df1f-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7df1f-128">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7df1f-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7df1f-129">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7df1f-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7df1f-130">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7df1f-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7df1f-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="7df1f-131">See Also</span></span>  
 [<span data-ttu-id="7df1f-132">ICLRTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7df1f-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="7df1f-133">ICLRTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7df1f-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="7df1f-134">IHostTask (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7df1f-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="7df1f-135">IHostTaskManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7df1f-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
