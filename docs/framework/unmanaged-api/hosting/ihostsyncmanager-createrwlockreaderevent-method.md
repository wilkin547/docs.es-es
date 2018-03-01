---
title: "IHostSyncManager::CreateRWLockReaderEvent (Método)"
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 6b583e7b5dd1a83ecb891591c25802ae257ad7c7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ihostsyncmanagercreaterwlockreaderevent-method"></a><span data-ttu-id="c211f-102">IHostSyncManager::CreateRWLockReaderEvent (Método)</span><span class="sxs-lookup"><span data-stu-id="c211f-102">IHostSyncManager::CreateRWLockReaderEvent Method</span></span>
<span data-ttu-id="c211f-103">Crea un objeto de evento de restablecimiento manual para la implementación de un bloqueo de lector.</span><span class="sxs-lookup"><span data-stu-id="c211f-103">Creates a manual-reset event object for the implementation of a reader lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c211f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c211f-104">Syntax</span></span>  
  
```  
HRESULT CreateRWLockReaderEvent (  
    [in]  BOOL bInitialState,  
    [in]  SIZE_T cookie,  
    [out] IHostManualEvent **ppEvent  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c211f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c211f-105">Parameters</span></span>  
 `bInitialState`  
 <span data-ttu-id="c211f-106">[in] `true`si `ppEvent` debe señalado; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="c211f-106">[in] `true`, if `ppEvent` should be signaled; otherwise, `false`.</span></span>  
  
 `cookie`  
 <span data-ttu-id="c211f-107">[in] Cookie que se va a asociar con el bloqueo de lector.</span><span class="sxs-lookup"><span data-stu-id="c211f-107">[in] A cookie to associate with the reader lock.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="c211f-108">[out] Un puntero a la dirección de un [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) instancia o null si no se pudo crear el objeto de evento.</span><span class="sxs-lookup"><span data-stu-id="c211f-108">[out] A pointer to the address of an [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) instance, or null if the event object could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c211f-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c211f-109">Return Value</span></span>  
  
|<span data-ttu-id="c211f-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c211f-110">HRESULT</span></span>|<span data-ttu-id="c211f-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="c211f-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c211f-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="c211f-112">S_OK</span></span>|<span data-ttu-id="c211f-113">`CreateRWLockReaderEvent`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="c211f-113">`CreateRWLockReaderEvent` returned successfully.</span></span>|  
|<span data-ttu-id="c211f-114">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c211f-114">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c211f-115">Common language runtime (CLR) no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="c211f-115">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c211f-116">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c211f-116">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c211f-117">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="c211f-117">The call timed out.</span></span>|  
|<span data-ttu-id="c211f-118">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c211f-118">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c211f-119">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="c211f-119">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c211f-120">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c211f-120">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c211f-121">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="c211f-121">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c211f-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c211f-122">E_FAIL</span></span>|<span data-ttu-id="c211f-123">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="c211f-123">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c211f-124">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="c211f-124">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c211f-125">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="c211f-125">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="c211f-126">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="c211f-126">E_OUTOFMEMORY</span></span>|<span data-ttu-id="c211f-127">No había memoria suficiente disponible para crear el objeto de evento solicitado.</span><span class="sxs-lookup"><span data-stu-id="c211f-127">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c211f-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c211f-128">Remarks</span></span>  
 <span data-ttu-id="c211f-129">CLR llama `CreateRWLockReaderEvent` para obtener una referencia a un `IHostManualEvent` instancia y utilizarla en su implementación de un bloqueo de lector.</span><span class="sxs-lookup"><span data-stu-id="c211f-129">The CLR calls `CreateRWLockReaderEvent` to get a reference to an `IHostManualEvent` instance to use in its implementation of a reader lock.</span></span> <span data-ttu-id="c211f-130">El host puede utilizar la cookie para determinar qué tareas están esperando en el bloqueo de lector consultando la [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) interfaz.</span><span class="sxs-lookup"><span data-stu-id="c211f-130">The host can use the cookie to determine which tasks are waiting on the reader lock by querying the [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c211f-131">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c211f-131">Requirements</span></span>  
 <span data-ttu-id="c211f-132">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c211f-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c211f-133">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c211f-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c211f-134">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c211f-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c211f-135">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c211f-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c211f-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="c211f-136">See Also</span></span>  
 [<span data-ttu-id="c211f-137">ICLRSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c211f-137">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="c211f-138">IHostAutoEvent (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c211f-138">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 [<span data-ttu-id="c211f-139">IHostManualEvent (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c211f-139">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)  
 [<span data-ttu-id="c211f-140">IHostSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c211f-140">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
