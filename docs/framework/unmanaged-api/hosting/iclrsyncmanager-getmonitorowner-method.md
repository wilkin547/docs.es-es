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
ms.openlocfilehash: 77debe047f5b379237022f44ef8f9d96718b227d
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762505"
---
# <a name="iclrsyncmanagergetmonitorowner-method"></a><span data-ttu-id="bddc1-102">ICLRSyncManager::GetMonitorOwner (Método)</span><span class="sxs-lookup"><span data-stu-id="bddc1-102">ICLRSyncManager::GetMonitorOwner Method</span></span>
<span data-ttu-id="bddc1-103">Obtiene la instancia de [IHostTask](ihosttask-interface.md) que posee el monitor identificado por la cookie especificada.</span><span class="sxs-lookup"><span data-stu-id="bddc1-103">Gets the [IHostTask](ihosttask-interface.md) instance that owns the monitor identified by the specified cookie.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bddc1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bddc1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMonitorOwner (  
    [in]  SIZE_T     cookie,  
    [out] IHostTask *ppOwnerHostTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bddc1-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bddc1-105">Parameters</span></span>  
 `cookie`  
 <span data-ttu-id="bddc1-106">de Cookie asociada al monitor.</span><span class="sxs-lookup"><span data-stu-id="bddc1-106">[in] The cookie associated with the monitor.</span></span>  
  
 `ppOwnerHostTask`  
 <span data-ttu-id="bddc1-107">enuncia Puntero al `IHostTask` que posee actualmente el monitor o null si ninguna tarea tiene propiedad.</span><span class="sxs-lookup"><span data-stu-id="bddc1-107">[out] A pointer to the `IHostTask` that currently owns the monitor, or null if no task has ownership.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bddc1-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="bddc1-108">Return Value</span></span>  
  
|<span data-ttu-id="bddc1-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="bddc1-109">HRESULT</span></span>|<span data-ttu-id="bddc1-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="bddc1-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="bddc1-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="bddc1-111">S_OK</span></span>|<span data-ttu-id="bddc1-112">`GetMonitorOwner`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="bddc1-112">`GetMonitorOwner` returned successfully.</span></span>|  
|<span data-ttu-id="bddc1-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="bddc1-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="bddc1-114">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="bddc1-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="bddc1-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="bddc1-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="bddc1-116">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="bddc1-116">The call timed out.</span></span>|  
|<span data-ttu-id="bddc1-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="bddc1-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="bddc1-118">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="bddc1-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="bddc1-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="bddc1-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="bddc1-120">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="bddc1-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="bddc1-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="bddc1-121">E_FAIL</span></span>|<span data-ttu-id="bddc1-122">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="bddc1-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="bddc1-123">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="bddc1-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="bddc1-124">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="bddc1-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bddc1-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bddc1-125">Remarks</span></span>  
 <span data-ttu-id="bddc1-126">Normalmente, el host llama `GetMonitorOwner` como parte de un mecanismo de detección de interbloqueos.</span><span class="sxs-lookup"><span data-stu-id="bddc1-126">The host typically calls `GetMonitorOwner` as part of a deadlock-detection mechanism.</span></span> <span data-ttu-id="bddc1-127">La cookie está asociada a un monitor cuando se crea mediante una llamada a [IHostSyncManager:: CreateMonitorEvent (](ihostsyncmanager-createmonitorevent-method.md).</span><span class="sxs-lookup"><span data-stu-id="bddc1-127">The cookie is associated with a monitor when it is created by using a call to [IHostSyncManager::CreateMonitorEvent](ihostsyncmanager-createmonitorevent-method.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bddc1-128">Una llamada para liberar el evento subyacente al monitor podría bloquearse, pero no interbloqueará, si una llamada a este método está actualmente en vigor en la cookie asociada a ese monitor.</span><span class="sxs-lookup"><span data-stu-id="bddc1-128">A call to release the event underlying the monitor might block—but will not deadlock—if a call to this method is currently in effect on the cookie associated with that monitor.</span></span> <span data-ttu-id="bddc1-129">Otras tareas también podrían bloquearse si intentan adquirir este monitor.</span><span class="sxs-lookup"><span data-stu-id="bddc1-129">Other tasks might also block if they attempt to acquire this monitor.</span></span>  
  
 <span data-ttu-id="bddc1-130">`GetMonitorOwner`siempre devuelve inmediatamente y se puede llamar en cualquier momento después de una llamada a `CreateMonitorEvent` .</span><span class="sxs-lookup"><span data-stu-id="bddc1-130">`GetMonitorOwner` always returns immediately and can be called any time after a call to `CreateMonitorEvent`.</span></span> <span data-ttu-id="bddc1-131">No es necesario que el host espere hasta que una tarea esté esperando en el evento.</span><span class="sxs-lookup"><span data-stu-id="bddc1-131">The host does not need to wait until a task is waiting on the event.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bddc1-132">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bddc1-132">Requirements</span></span>  
 <span data-ttu-id="bddc1-133">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bddc1-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bddc1-134">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="bddc1-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bddc1-135">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="bddc1-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bddc1-136">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bddc1-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bddc1-137">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="bddc1-137">See also</span></span>

- [<span data-ttu-id="bddc1-138">ICLRSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="bddc1-138">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="bddc1-139">IHostSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="bddc1-139">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
