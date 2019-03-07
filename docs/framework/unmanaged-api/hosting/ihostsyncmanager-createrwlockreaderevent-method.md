---
title: IHostSyncManager::CreateRWLockReaderEvent (Método)
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateRWLockReaderEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateRWLockReaderEvent
helpviewer_keywords:
- CreateRWLockReaderEvent method [.NET Framework hosting]
- IHostSyncManager::CreateRWLockReaderEvent method [.NET Framework hosting]
ms.assetid: 68c4ea19-c47c-45c6-b420-d3a2ba1c2d50
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b5aef90fa14dac58a0b38316cd5f64b4ac8c9aa1
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57495655"
---
# <a name="ihostsyncmanagercreaterwlockreaderevent-method"></a><span data-ttu-id="7c12e-102">IHostSyncManager::CreateRWLockReaderEvent (Método)</span><span class="sxs-lookup"><span data-stu-id="7c12e-102">IHostSyncManager::CreateRWLockReaderEvent Method</span></span>
<span data-ttu-id="7c12e-103">Crea un objeto de evento de restablecimiento manual para la implementación de un bloqueo de lector.</span><span class="sxs-lookup"><span data-stu-id="7c12e-103">Creates a manual-reset event object for the implementation of a reader lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c12e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7c12e-104">Syntax</span></span>  
  
```  
HRESULT CreateRWLockReaderEvent (  
    [in]  BOOL bInitialState,  
    [in]  SIZE_T cookie,  
    [out] IHostManualEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7c12e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7c12e-105">Parameters</span></span>  
 `bInitialState`  
 <span data-ttu-id="7c12e-106">[in] `true`si `ppEvent` debe señalado; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="7c12e-106">[in] `true`, if `ppEvent` should be signaled; otherwise, `false`.</span></span>  
  
 `cookie`  
 <span data-ttu-id="7c12e-107">[in] Una cookie para asociar con el bloqueo de lector.</span><span class="sxs-lookup"><span data-stu-id="7c12e-107">[in] A cookie to associate with the reader lock.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="7c12e-108">[out] Un puntero a la dirección de un [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) de instancia, o null si no se pudo crear el objeto de evento.</span><span class="sxs-lookup"><span data-stu-id="7c12e-108">[out] A pointer to the address of an [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) instance, or null if the event object could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7c12e-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="7c12e-109">Return Value</span></span>  
  
|<span data-ttu-id="7c12e-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7c12e-110">HRESULT</span></span>|<span data-ttu-id="7c12e-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="7c12e-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7c12e-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="7c12e-112">S_OK</span></span>|<span data-ttu-id="7c12e-113">`CreateRWLockReaderEvent` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="7c12e-113">`CreateRWLockReaderEvent` returned successfully.</span></span>|  
|<span data-ttu-id="7c12e-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7c12e-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7c12e-115">Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="7c12e-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7c12e-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7c12e-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7c12e-117">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="7c12e-117">The call timed out.</span></span>|  
|<span data-ttu-id="7c12e-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7c12e-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7c12e-119">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="7c12e-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7c12e-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7c12e-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7c12e-121">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="7c12e-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7c12e-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7c12e-122">E_FAIL</span></span>|<span data-ttu-id="7c12e-123">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="7c12e-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7c12e-124">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="7c12e-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7c12e-125">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="7c12e-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="7c12e-126">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="7c12e-126">E_OUTOFMEMORY</span></span>|<span data-ttu-id="7c12e-127">No había suficiente memoria disponible para crear el objeto de evento solicitado.</span><span class="sxs-lookup"><span data-stu-id="7c12e-127">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7c12e-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7c12e-128">Remarks</span></span>  
 <span data-ttu-id="7c12e-129">CLR llama a `CreateRWLockReaderEvent` para obtener una referencia a un `IHostManualEvent` instancia que se utiliza en su implementación de un bloqueo de lector.</span><span class="sxs-lookup"><span data-stu-id="7c12e-129">The CLR calls `CreateRWLockReaderEvent` to get a reference to an `IHostManualEvent` instance to use in its implementation of a reader lock.</span></span> <span data-ttu-id="7c12e-130">El host puede usar la cookie para determinar qué tareas están esperando el bloqueo de lector consultando la [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) interfaz.</span><span class="sxs-lookup"><span data-stu-id="7c12e-130">The host can use the cookie to determine which tasks are waiting on the reader lock by querying the [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c12e-131">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7c12e-131">Requirements</span></span>  
 <span data-ttu-id="7c12e-132">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7c12e-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c12e-133">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7c12e-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7c12e-134">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7c12e-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7c12e-135">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c12e-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c12e-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="7c12e-136">See also</span></span>
- [<span data-ttu-id="7c12e-137">ICLRSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7c12e-137">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="7c12e-138">IHostAutoEvent (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7c12e-138">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [<span data-ttu-id="7c12e-139">IHostManualEvent (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7c12e-139">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="7c12e-140">IHostSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7c12e-140">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
