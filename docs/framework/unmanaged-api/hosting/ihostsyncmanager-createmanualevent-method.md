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
ms.openlocfilehash: 13679b4d40e660dfdd18e6fbafe19226b2ffda37
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73195869"
---
# <a name="ihostsyncmanagercreatemanualevent-method"></a><span data-ttu-id="51f9f-102">IHostSyncManager::CreateManualEvent (Método)</span><span class="sxs-lookup"><span data-stu-id="51f9f-102">IHostSyncManager::CreateManualEvent Method</span></span>
<span data-ttu-id="51f9f-103">Crea un objeto de evento de restablecimiento manual.</span><span class="sxs-lookup"><span data-stu-id="51f9f-103">Creates a manual-reset event object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51f9f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="51f9f-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateManualEvent (  
    [in]  BOOL bInitialState,  
    [out] IHostManualEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="51f9f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="51f9f-105">Parameters</span></span>  
 `bInitialState`  
 <span data-ttu-id="51f9f-106">[in] `true`, si el objeto está señalado; de lo contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="51f9f-106">[in] `true`, if the object is signaled; otherwise, `false`.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="51f9f-107">enuncia Un puntero a la dirección de una instancia de [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) , o null si no se pudo crear el evento.</span><span class="sxs-lookup"><span data-stu-id="51f9f-107">[out] A pointer to the address of an [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) instance, or null if the event could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="51f9f-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="51f9f-108">Return Value</span></span>  
  
|<span data-ttu-id="51f9f-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="51f9f-109">HRESULT</span></span>|<span data-ttu-id="51f9f-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="51f9f-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="51f9f-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="51f9f-111">S_OK</span></span>|<span data-ttu-id="51f9f-112">`CreateManualEvent` devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="51f9f-112">`CreateManualEvent` returned successfully.</span></span>|  
|<span data-ttu-id="51f9f-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="51f9f-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="51f9f-114">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="51f9f-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="51f9f-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="51f9f-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="51f9f-116">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="51f9f-116">The call timed out.</span></span>|  
|<span data-ttu-id="51f9f-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="51f9f-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="51f9f-118">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="51f9f-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="51f9f-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="51f9f-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="51f9f-120">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="51f9f-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="51f9f-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="51f9f-121">E_FAIL</span></span>|<span data-ttu-id="51f9f-122">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="51f9f-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="51f9f-123">Cuando un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="51f9f-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="51f9f-124">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="51f9f-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="51f9f-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="51f9f-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="51f9f-126">No había suficiente memoria disponible para crear el objeto de evento solicitado.</span><span class="sxs-lookup"><span data-stu-id="51f9f-126">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="51f9f-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="51f9f-127">Remarks</span></span>  
 <span data-ttu-id="51f9f-128">`CreateManualEvent` crea un `IHostManualEvent`, un objeto de evento de restablecimiento manual que requiere una llamada al método [IHostManualEvent:: RESET](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-reset-method.md) para establecerlo en un estado no señalado.</span><span class="sxs-lookup"><span data-stu-id="51f9f-128">`CreateManualEvent` creates an `IHostManualEvent`, a manual-reset event object that requires a call to the [IHostManualEvent::Reset](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-reset-method.md) method to set it to a non-signaled state.</span></span> <span data-ttu-id="51f9f-129">`CreateManualEvent` refleja la función de `CreateEvent` de Win32 con un valor de `true` especificado para el parámetro `bManualReset`.</span><span class="sxs-lookup"><span data-stu-id="51f9f-129">`CreateManualEvent` mirrors the Win32 `CreateEvent` function with a value of `true` specified for the `bManualReset` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="51f9f-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="51f9f-130">Requirements</span></span>  
 <span data-ttu-id="51f9f-131">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="51f9f-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51f9f-132">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="51f9f-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="51f9f-133">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="51f9f-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="51f9f-134">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51f9f-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51f9f-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="51f9f-135">See also</span></span>

- [<span data-ttu-id="51f9f-136">ICLRSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="51f9f-136">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="51f9f-137">IHostManualEvent (interfaz)</span><span class="sxs-lookup"><span data-stu-id="51f9f-137">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [<span data-ttu-id="51f9f-138">IHostSyncManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="51f9f-138">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
