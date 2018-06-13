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
ms.openlocfilehash: 5668d75c831710b4f077c325b40352a518ee2c96
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33434309"
---
# <a name="iclrsyncmanagergetmonitorowner-method"></a><span data-ttu-id="09396-102">ICLRSyncManager::GetMonitorOwner (Método)</span><span class="sxs-lookup"><span data-stu-id="09396-102">ICLRSyncManager::GetMonitorOwner Method</span></span>
<span data-ttu-id="09396-103">Obtiene el [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instancia propietaria del monitor identificado por la cookie especificada.</span><span class="sxs-lookup"><span data-stu-id="09396-103">Gets the [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance that owns the monitor identified by the specified cookie.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09396-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="09396-104">Syntax</span></span>  
  
```  
HRESULT GetMonitorOwner (  
    [in]  SIZE_T     cookie,  
    [out] IHostTask *ppOwnerHostTask  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="09396-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="09396-105">Parameters</span></span>  
 `cookie`  
 <span data-ttu-id="09396-106">[in] La cookie asociada con el monitor.</span><span class="sxs-lookup"><span data-stu-id="09396-106">[in] The cookie associated with the monitor.</span></span>  
  
 `ppOwnerHostTask`  
 <span data-ttu-id="09396-107">[out] Un puntero a la `IHostTask` que actualmente posee el monitor, o null si no hay ninguna tarea tiene una propiedad.</span><span class="sxs-lookup"><span data-stu-id="09396-107">[out] A pointer to the `IHostTask` that currently owns the monitor, or null if no task has ownership.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="09396-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="09396-108">Return Value</span></span>  
  
|<span data-ttu-id="09396-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="09396-109">HRESULT</span></span>|<span data-ttu-id="09396-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="09396-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="09396-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="09396-111">S_OK</span></span>|<span data-ttu-id="09396-112">`GetMonitorOwner` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="09396-112">`GetMonitorOwner` returned successfully.</span></span>|  
|<span data-ttu-id="09396-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="09396-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="09396-114">El CLR no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="09396-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="09396-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="09396-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="09396-116">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="09396-116">The call timed out.</span></span>|  
|<span data-ttu-id="09396-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="09396-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="09396-118">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="09396-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="09396-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="09396-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="09396-120">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="09396-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="09396-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="09396-121">E_FAIL</span></span>|<span data-ttu-id="09396-122">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="09396-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="09396-123">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="09396-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="09396-124">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="09396-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="09396-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="09396-125">Remarks</span></span>  
 <span data-ttu-id="09396-126">El host llama normalmente `GetMonitorOwner` como parte de un mecanismo de detección de interbloqueos.</span><span class="sxs-lookup"><span data-stu-id="09396-126">The host typically calls `GetMonitorOwner` as part of a deadlock-detection mechanism.</span></span> <span data-ttu-id="09396-127">La cookie está asociada a un monitor cuando se crea mediante una llamada a [IHostSyncManager:: CreateMonitorEvent](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createmonitorevent-method.md).</span><span class="sxs-lookup"><span data-stu-id="09396-127">The cookie is associated with a monitor when it is created by using a call to [IHostSyncManager::CreateMonitorEvent](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createmonitorevent-method.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="09396-128">Una llamada para liberar el evento subyacente al monitor podría bloquearse, pero no interbloquee: si una llamada a este método está actualmente en vigor en la cookie asociada al monitor.</span><span class="sxs-lookup"><span data-stu-id="09396-128">A call to release the event underlying the monitor might block—but will not deadlock—if a call to this method is currently in effect on the cookie associated with that monitor.</span></span> <span data-ttu-id="09396-129">Otras tareas también podrían bloquearse si éstos intentan adquirir a este monitor.</span><span class="sxs-lookup"><span data-stu-id="09396-129">Other tasks might also block if they attempt to acquire this monitor.</span></span>  
  
 <span data-ttu-id="09396-130">`GetMonitorOwner` siempre se devuelve inmediatamente y se puede llamar en cualquier momento después de llamar a `CreateMonitorEvent`.</span><span class="sxs-lookup"><span data-stu-id="09396-130">`GetMonitorOwner` always returns immediately and can be called any time after a call to `CreateMonitorEvent`.</span></span> <span data-ttu-id="09396-131">El host no tenga que esperar hasta que una tarea está esperando en el evento.</span><span class="sxs-lookup"><span data-stu-id="09396-131">The host does not need to wait until a task is waiting on the event.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="09396-132">Requisitos</span><span class="sxs-lookup"><span data-stu-id="09396-132">Requirements</span></span>  
 <span data-ttu-id="09396-133">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="09396-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09396-134">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="09396-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="09396-135">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="09396-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="09396-136">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="09396-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09396-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="09396-137">See Also</span></span>  
 [<span data-ttu-id="09396-138">ICLRSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="09396-138">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="09396-139">IHostSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="09396-139">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
