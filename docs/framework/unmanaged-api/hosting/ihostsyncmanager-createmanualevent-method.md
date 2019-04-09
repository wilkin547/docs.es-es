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
ms.openlocfilehash: ada9a3131ea3063239ab7897d0096f0accbd0f94
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59137740"
---
# <a name="ihostsyncmanagercreatemanualevent-method"></a><span data-ttu-id="12d10-102">IHostSyncManager::CreateManualEvent (Método)</span><span class="sxs-lookup"><span data-stu-id="12d10-102">IHostSyncManager::CreateManualEvent Method</span></span>
<span data-ttu-id="12d10-103">Crea un objeto de evento de restablecimiento manual.</span><span class="sxs-lookup"><span data-stu-id="12d10-103">Creates a manual-reset event object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12d10-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="12d10-104">Syntax</span></span>  
  
```  
HRESULT CreateManualEvent (  
    [in]  BOOL bInitialState,  
    [out] IHostManualEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="12d10-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="12d10-105">Parameters</span></span>  
 `bInitialState`  
 <span data-ttu-id="12d10-106">[in] `true`, si el objeto está señalado; de lo contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="12d10-106">[in] `true`, if the object is signaled; otherwise, `false`.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="12d10-107">[out] Un puntero a la dirección de un [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) de instancia, o null si no se pudo crear el evento.</span><span class="sxs-lookup"><span data-stu-id="12d10-107">[out] A pointer to the address of an [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) instance, or null if the event could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="12d10-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="12d10-108">Return Value</span></span>  
  
|<span data-ttu-id="12d10-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="12d10-109">HRESULT</span></span>|<span data-ttu-id="12d10-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="12d10-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="12d10-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="12d10-111">S_OK</span></span>|`CreateManualEvent` <span data-ttu-id="12d10-112">se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="12d10-112">returned successfully.</span></span>|  
|<span data-ttu-id="12d10-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="12d10-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="12d10-114">Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="12d10-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="12d10-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="12d10-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="12d10-116">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="12d10-116">The call timed out.</span></span>|  
|<span data-ttu-id="12d10-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="12d10-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="12d10-118">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="12d10-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="12d10-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="12d10-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="12d10-120">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="12d10-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="12d10-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="12d10-121">E_FAIL</span></span>|<span data-ttu-id="12d10-122">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="12d10-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="12d10-123">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="12d10-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="12d10-124">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="12d10-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="12d10-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="12d10-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="12d10-126">No había suficiente memoria disponible para crear el objeto de evento solicitado.</span><span class="sxs-lookup"><span data-stu-id="12d10-126">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="12d10-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="12d10-127">Remarks</span></span>  
 `CreateManualEvent` <span data-ttu-id="12d10-128">crea un `IHostManualEvent`, un objeto de evento de restablecimiento manual que requiere una llamada a la [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-reset-method.md) método establecerlo en un estado no señalado.</span><span class="sxs-lookup"><span data-stu-id="12d10-128">creates an `IHostManualEvent`, a manual-reset event object that requires a call to the [IHostManualEvent::Reset](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-reset-method.md) method to set it to a non-signaled state.</span></span> `CreateManualEvent` <span data-ttu-id="12d10-129">refleja el Win32 `CreateEvent` función con un valor de `true` especificado para el `bManualReset` parámetro.</span><span class="sxs-lookup"><span data-stu-id="12d10-129">mirrors the Win32 `CreateEvent` function with a value of `true` specified for the `bManualReset` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="12d10-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="12d10-130">Requirements</span></span>  
 <span data-ttu-id="12d10-131">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="12d10-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="12d10-132">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="12d10-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="12d10-133">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="12d10-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="12d10-134">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="12d10-134">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="12d10-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="12d10-135">See also</span></span>

- [<span data-ttu-id="12d10-136">ICLRSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="12d10-136">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="12d10-137">IHostManualEvent (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="12d10-137">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="12d10-138">IHostSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="12d10-138">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
