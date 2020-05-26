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
ms.openlocfilehash: 334520df749ba428e6480188cd0655bb734725a6
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/22/2020
ms.locfileid: "83803306"
---
# <a name="ihostsyncmanagercreatemanualevent-method"></a><span data-ttu-id="eeb7e-102">IHostSyncManager::CreateManualEvent (Método)</span><span class="sxs-lookup"><span data-stu-id="eeb7e-102">IHostSyncManager::CreateManualEvent Method</span></span>
<span data-ttu-id="eeb7e-103">Crea un objeto de evento de restablecimiento manual.</span><span class="sxs-lookup"><span data-stu-id="eeb7e-103">Creates a manual-reset event object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eeb7e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="eeb7e-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateManualEvent (  
    [in]  BOOL bInitialState,  
    [out] IHostManualEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eeb7e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="eeb7e-105">Parameters</span></span>  
 `bInitialState`  
 <span data-ttu-id="eeb7e-106">[in] `true` , si el objeto está señalado; de lo contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="eeb7e-106">[in] `true`, if the object is signaled; otherwise, `false`.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="eeb7e-107">enuncia Un puntero a la dirección de una instancia de [IHostManualEvent](ihostmanualevent-interface.md) , o null si no se pudo crear el evento.</span><span class="sxs-lookup"><span data-stu-id="eeb7e-107">[out] A pointer to the address of an [IHostManualEvent](ihostmanualevent-interface.md) instance, or null if the event could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="eeb7e-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="eeb7e-108">Return Value</span></span>  
  
|<span data-ttu-id="eeb7e-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="eeb7e-109">HRESULT</span></span>|<span data-ttu-id="eeb7e-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="eeb7e-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="eeb7e-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="eeb7e-111">S_OK</span></span>|<span data-ttu-id="eeb7e-112">`CreateManualEvent`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="eeb7e-112">`CreateManualEvent` returned successfully.</span></span>|  
|<span data-ttu-id="eeb7e-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="eeb7e-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="eeb7e-114">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="eeb7e-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="eeb7e-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="eeb7e-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="eeb7e-116">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="eeb7e-116">The call timed out.</span></span>|  
|<span data-ttu-id="eeb7e-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="eeb7e-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="eeb7e-118">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="eeb7e-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="eeb7e-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="eeb7e-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="eeb7e-120">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="eeb7e-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="eeb7e-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="eeb7e-121">E_FAIL</span></span>|<span data-ttu-id="eeb7e-122">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="eeb7e-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="eeb7e-123">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="eeb7e-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="eeb7e-124">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="eeb7e-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="eeb7e-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="eeb7e-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="eeb7e-126">No había suficiente memoria disponible para crear el objeto de evento solicitado.</span><span class="sxs-lookup"><span data-stu-id="eeb7e-126">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eeb7e-127">Observaciones</span><span class="sxs-lookup"><span data-stu-id="eeb7e-127">Remarks</span></span>  
 <span data-ttu-id="eeb7e-128">`CreateManualEvent`crea un `IHostManualEvent` objeto, un objeto de evento de restablecimiento manual que requiere una llamada al método [IHostManualEvent:: RESET](ihostmanualevent-reset-method.md) para establecerlo en un estado no señalado.</span><span class="sxs-lookup"><span data-stu-id="eeb7e-128">`CreateManualEvent` creates an `IHostManualEvent`, a manual-reset event object that requires a call to the [IHostManualEvent::Reset](ihostmanualevent-reset-method.md) method to set it to a non-signaled state.</span></span> <span data-ttu-id="eeb7e-129">`CreateManualEvent`refleja la `CreateEvent` función de Win32 con el valor `true` especificado para el `bManualReset` parámetro.</span><span class="sxs-lookup"><span data-stu-id="eeb7e-129">`CreateManualEvent` mirrors the Win32 `CreateEvent` function with a value of `true` specified for the `bManualReset` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eeb7e-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="eeb7e-130">Requirements</span></span>  
 <span data-ttu-id="eeb7e-131">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eeb7e-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eeb7e-132">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="eeb7e-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="eeb7e-133">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="eeb7e-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="eeb7e-134">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eeb7e-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eeb7e-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="eeb7e-135">See also</span></span>

- [<span data-ttu-id="eeb7e-136">ICLRSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="eeb7e-136">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="eeb7e-137">IHostManualEvent (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="eeb7e-137">IHostManualEvent Interface</span></span>](ihostmanualevent-interface.md)
- [<span data-ttu-id="eeb7e-138">IHostSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="eeb7e-138">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
