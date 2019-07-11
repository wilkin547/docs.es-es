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
ms.openlocfilehash: 1cfb57ba6f07437abfc8576ca4d5ff9cd0131d8b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67753434"
---
# <a name="ihostsyncmanagercreatemanualevent-method"></a><span data-ttu-id="b41cc-102">IHostSyncManager::CreateManualEvent (Método)</span><span class="sxs-lookup"><span data-stu-id="b41cc-102">IHostSyncManager::CreateManualEvent Method</span></span>
<span data-ttu-id="b41cc-103">Crea un objeto de evento de restablecimiento manual.</span><span class="sxs-lookup"><span data-stu-id="b41cc-103">Creates a manual-reset event object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b41cc-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b41cc-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateManualEvent (  
    [in]  BOOL bInitialState,  
    [out] IHostManualEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b41cc-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b41cc-105">Parameters</span></span>  
 `bInitialState`  
 <span data-ttu-id="b41cc-106">[in] `true`, si el objeto está señalado; de lo contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="b41cc-106">[in] `true`, if the object is signaled; otherwise, `false`.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="b41cc-107">[out] Un puntero a la dirección de un [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) de instancia, o null si no se pudo crear el evento.</span><span class="sxs-lookup"><span data-stu-id="b41cc-107">[out] A pointer to the address of an [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) instance, or null if the event could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b41cc-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b41cc-108">Return Value</span></span>  
  
|<span data-ttu-id="b41cc-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b41cc-109">HRESULT</span></span>|<span data-ttu-id="b41cc-110">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="b41cc-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b41cc-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="b41cc-111">S_OK</span></span>|<span data-ttu-id="b41cc-112">`CreateManualEvent` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="b41cc-112">`CreateManualEvent` returned successfully.</span></span>|  
|<span data-ttu-id="b41cc-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b41cc-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b41cc-114">Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="b41cc-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b41cc-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b41cc-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b41cc-116">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="b41cc-116">The call timed out.</span></span>|  
|<span data-ttu-id="b41cc-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b41cc-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b41cc-118">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="b41cc-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b41cc-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b41cc-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b41cc-120">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="b41cc-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b41cc-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b41cc-121">E_FAIL</span></span>|<span data-ttu-id="b41cc-122">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="b41cc-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b41cc-123">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="b41cc-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b41cc-124">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="b41cc-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="b41cc-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="b41cc-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="b41cc-126">No había suficiente memoria disponible para crear el objeto de evento solicitado.</span><span class="sxs-lookup"><span data-stu-id="b41cc-126">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b41cc-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b41cc-127">Remarks</span></span>  
 <span data-ttu-id="b41cc-128">`CreateManualEvent` crea un `IHostManualEvent`, un objeto de evento de restablecimiento manual que requiere una llamada a la [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-reset-method.md) método establecerlo en un estado no señalado.</span><span class="sxs-lookup"><span data-stu-id="b41cc-128">`CreateManualEvent` creates an `IHostManualEvent`, a manual-reset event object that requires a call to the [IHostManualEvent::Reset](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-reset-method.md) method to set it to a non-signaled state.</span></span> <span data-ttu-id="b41cc-129">`CreateManualEvent` refleja el Win32 `CreateEvent` función con un valor de `true` especificado para el `bManualReset` parámetro.</span><span class="sxs-lookup"><span data-stu-id="b41cc-129">`CreateManualEvent` mirrors the Win32 `CreateEvent` function with a value of `true` specified for the `bManualReset` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b41cc-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b41cc-130">Requirements</span></span>  
 <span data-ttu-id="b41cc-131">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b41cc-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b41cc-132">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b41cc-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b41cc-133">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b41cc-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b41cc-134">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b41cc-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b41cc-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="b41cc-135">See also</span></span>

- [<span data-ttu-id="b41cc-136">ICLRSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b41cc-136">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="b41cc-137">IHostManualEvent (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b41cc-137">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="b41cc-138">IHostSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b41cc-138">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
