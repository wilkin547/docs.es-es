---
title: ICLRSyncManager::GetMonitorOwner (Método)
ms.date: 03/30/2017
api_name:
- ICLRSyncManager.GetMonitorOwner
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRSyncManager::GetMonitorOwner
helpviewer_keywords:
- ICLRSyncManager::GetMonitorOwner method [.NET Framework hosting]
- GetMonitorOwner method [.NET Framework hosting]
ms.assetid: 840983a4-396d-47b4-86a0-d35f9b437cdb
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3847c5e5704f4eef138bf8b3f7966e4ff66d8784
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54716324"
---
# <a name="iclrsyncmanagergetmonitorowner-method"></a><span data-ttu-id="abdf2-102">ICLRSyncManager::GetMonitorOwner (Método)</span><span class="sxs-lookup"><span data-stu-id="abdf2-102">ICLRSyncManager::GetMonitorOwner Method</span></span>
<span data-ttu-id="abdf2-103">Obtiene el [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instancia que posee el monitor identificado por la cookie especificada.</span><span class="sxs-lookup"><span data-stu-id="abdf2-103">Gets the [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance that owns the monitor identified by the specified cookie.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="abdf2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="abdf2-104">Syntax</span></span>  
  
```  
HRESULT GetMonitorOwner (  
    [in]  SIZE_T     cookie,  
    [out] IHostTask *ppOwnerHostTask  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="abdf2-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="abdf2-105">Parameters</span></span>  
 `cookie`  
 <span data-ttu-id="abdf2-106">[in] La cookie asociada con el monitor.</span><span class="sxs-lookup"><span data-stu-id="abdf2-106">[in] The cookie associated with the monitor.</span></span>  
  
 `ppOwnerHostTask`  
 <span data-ttu-id="abdf2-107">[out] Un puntero a la `IHostTask` que actualmente posee el monitor, o null si no hay ninguna tarea tiene una propiedad.</span><span class="sxs-lookup"><span data-stu-id="abdf2-107">[out] A pointer to the `IHostTask` that currently owns the monitor, or null if no task has ownership.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="abdf2-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="abdf2-108">Return Value</span></span>  
  
|<span data-ttu-id="abdf2-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="abdf2-109">HRESULT</span></span>|<span data-ttu-id="abdf2-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="abdf2-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="abdf2-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="abdf2-111">S_OK</span></span>|<span data-ttu-id="abdf2-112">`GetMonitorOwner` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="abdf2-112">`GetMonitorOwner` returned successfully.</span></span>|  
|<span data-ttu-id="abdf2-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="abdf2-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="abdf2-114">El CLR no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="abdf2-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="abdf2-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="abdf2-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="abdf2-116">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="abdf2-116">The call timed out.</span></span>|  
|<span data-ttu-id="abdf2-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="abdf2-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="abdf2-118">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="abdf2-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="abdf2-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="abdf2-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="abdf2-120">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="abdf2-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="abdf2-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="abdf2-121">E_FAIL</span></span>|<span data-ttu-id="abdf2-122">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="abdf2-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="abdf2-123">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="abdf2-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="abdf2-124">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="abdf2-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="abdf2-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="abdf2-125">Remarks</span></span>  
 <span data-ttu-id="abdf2-126">El host llama normalmente `GetMonitorOwner` como parte de un mecanismo de detección de interbloqueos.</span><span class="sxs-lookup"><span data-stu-id="abdf2-126">The host typically calls `GetMonitorOwner` as part of a deadlock-detection mechanism.</span></span> <span data-ttu-id="abdf2-127">La cookie está asociada con un monitor cuando se crea mediante una llamada a [IHostSyncManager:: CreateMonitorEvent](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createmonitorevent-method.md).</span><span class="sxs-lookup"><span data-stu-id="abdf2-127">The cookie is associated with a monitor when it is created by using a call to [IHostSyncManager::CreateMonitorEvent](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createmonitorevent-method.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="abdf2-128">Una llamada para liberar el evento subyacente al monitor podría bloquearse, pero no generará un interbloqueo, si una llamada a este método está actualmente en vigor en la cookie asociada con ese monitor.</span><span class="sxs-lookup"><span data-stu-id="abdf2-128">A call to release the event underlying the monitor might block—but will not deadlock—if a call to this method is currently in effect on the cookie associated with that monitor.</span></span> <span data-ttu-id="abdf2-129">También podrían estar bloqueando otras tareas si éstos intentan adquirir a este monitor.</span><span class="sxs-lookup"><span data-stu-id="abdf2-129">Other tasks might also block if they attempt to acquire this monitor.</span></span>  
  
 <span data-ttu-id="abdf2-130">`GetMonitorOwner` siempre devuelve inmediatamente y se puede llamar a cualquier momento después de llamar a `CreateMonitorEvent`.</span><span class="sxs-lookup"><span data-stu-id="abdf2-130">`GetMonitorOwner` always returns immediately and can be called any time after a call to `CreateMonitorEvent`.</span></span> <span data-ttu-id="abdf2-131">El host no es necesario esperar hasta que una tarea está esperando en el evento.</span><span class="sxs-lookup"><span data-stu-id="abdf2-131">The host does not need to wait until a task is waiting on the event.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="abdf2-132">Requisitos</span><span class="sxs-lookup"><span data-stu-id="abdf2-132">Requirements</span></span>  
 <span data-ttu-id="abdf2-133">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="abdf2-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="abdf2-134">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="abdf2-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="abdf2-135">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="abdf2-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="abdf2-136">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="abdf2-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abdf2-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="abdf2-137">See also</span></span>
- [<span data-ttu-id="abdf2-138">ICLRSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="abdf2-138">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="abdf2-139">IHostSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="abdf2-139">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
