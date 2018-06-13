---
title: IHostSyncManager::CreateManualEvent (Método)
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateManualEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateManualEvent
helpviewer_keywords:
- CreateManualEvent method [.NET Framework hosting]
- IHostSyncManager::CreateManualEvent method [.NET Framework hosting]
ms.assetid: 68661fbd-09cf-46dc-890b-e694f8a3880a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ecf53606dd12b517d9ec31ab25f98452d35bdf98
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33443454"
---
# <a name="ihostsyncmanagercreatemanualevent-method"></a><span data-ttu-id="1b5bd-102">IHostSyncManager::CreateManualEvent (Método)</span><span class="sxs-lookup"><span data-stu-id="1b5bd-102">IHostSyncManager::CreateManualEvent Method</span></span>
<span data-ttu-id="1b5bd-103">Crea un objeto de evento de restablecimiento manual.</span><span class="sxs-lookup"><span data-stu-id="1b5bd-103">Creates a manual-reset event object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b5bd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1b5bd-104">Syntax</span></span>  
  
```  
HRESULT CreateManualEvent (  
    [in]  BOOL bInitialState,  
    [out] IHostManualEvent **ppEvent  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1b5bd-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1b5bd-105">Parameters</span></span>  
 `bInitialState`  
 <span data-ttu-id="1b5bd-106">[in] `true`, si el objeto está señalado; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="1b5bd-106">[in] `true`, if the object is signaled; otherwise, `false`.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="1b5bd-107">[out] Un puntero a la dirección de un [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) instancia o null si no se pudo crear el evento.</span><span class="sxs-lookup"><span data-stu-id="1b5bd-107">[out] A pointer to the address of an [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) instance, or null if the event could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1b5bd-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="1b5bd-108">Return Value</span></span>  
  
|<span data-ttu-id="1b5bd-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1b5bd-109">HRESULT</span></span>|<span data-ttu-id="1b5bd-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="1b5bd-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1b5bd-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="1b5bd-111">S_OK</span></span>|<span data-ttu-id="1b5bd-112">`CreateManualEvent` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="1b5bd-112">`CreateManualEvent` returned successfully.</span></span>|  
|<span data-ttu-id="1b5bd-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1b5bd-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1b5bd-114">Common language runtime (CLR) no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="1b5bd-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1b5bd-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1b5bd-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1b5bd-116">La llamada agotó el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="1b5bd-116">The call timed out.</span></span>|  
|<span data-ttu-id="1b5bd-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1b5bd-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1b5bd-118">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="1b5bd-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1b5bd-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1b5bd-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1b5bd-120">Se canceló un evento mientras un subproceso bloqueado o fibra esperó en él.</span><span class="sxs-lookup"><span data-stu-id="1b5bd-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1b5bd-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1b5bd-121">E_FAIL</span></span>|<span data-ttu-id="1b5bd-122">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="1b5bd-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1b5bd-123">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="1b5bd-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1b5bd-124">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="1b5bd-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="1b5bd-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="1b5bd-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="1b5bd-126">No había memoria suficiente disponible para crear el objeto de evento solicitado.</span><span class="sxs-lookup"><span data-stu-id="1b5bd-126">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1b5bd-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1b5bd-127">Remarks</span></span>  
 <span data-ttu-id="1b5bd-128">`CreateManualEvent` crea un `IHostManualEvent`, un objeto de evento de restablecimiento manual que requiere una llamada a la [IHostManualEvent:: Reset](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-reset-method.md) método establecerlo en un estado no señalado.</span><span class="sxs-lookup"><span data-stu-id="1b5bd-128">`CreateManualEvent` creates an `IHostManualEvent`, a manual-reset event object that requires a call to the [IHostManualEvent::Reset](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-reset-method.md) method to set it to a non-signaled state.</span></span> <span data-ttu-id="1b5bd-129">`CreateManualEvent` refleja el Win32 `CreateEvent` función con un valor de `true` especificado para el `bManualReset` parámetro.</span><span class="sxs-lookup"><span data-stu-id="1b5bd-129">`CreateManualEvent` mirrors the Win32 `CreateEvent` function with a value of `true` specified for the `bManualReset` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1b5bd-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1b5bd-130">Requirements</span></span>  
 <span data-ttu-id="1b5bd-131">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1b5bd-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1b5bd-132">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1b5bd-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1b5bd-133">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1b5bd-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1b5bd-134">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1b5bd-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b5bd-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="1b5bd-135">See Also</span></span>  
 [<span data-ttu-id="1b5bd-136">ICLRSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1b5bd-136">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="1b5bd-137">IHostManualEvent (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1b5bd-137">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)  
 [<span data-ttu-id="1b5bd-138">IHostSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1b5bd-138">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
