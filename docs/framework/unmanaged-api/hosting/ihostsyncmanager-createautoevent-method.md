---
description: 'Más información acerca de: IHostSyncManager:: CreateAutoEvent ((método)'
title: IHostSyncManager::CreateAutoEvent (Método)
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateAutoEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateAutoEvent
helpviewer_keywords:
- IHostSyncManager::CreateAutoEvent method [.NET Framework hosting]
- CreateAutoEvent method [.NET Framework hosting]
ms.assetid: 3153643e-cf5c-4b44-8e0e-c2b22cb08208
topic_type:
- apiref
ms.openlocfilehash: 69767f1e01ead93c874eecf01c3167a5dc0e4b82
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784852"
---
# <a name="ihostsyncmanagercreateautoevent-method"></a><span data-ttu-id="c9978-103">IHostSyncManager::CreateAutoEvent (Método)</span><span class="sxs-lookup"><span data-stu-id="c9978-103">IHostSyncManager::CreateAutoEvent Method</span></span>

<span data-ttu-id="c9978-104">Crea un objeto de evento de restablecimiento automático.</span><span class="sxs-lookup"><span data-stu-id="c9978-104">Creates an auto-reset event object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9978-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c9978-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateAutoEvent (  
    [out] IHostAutoEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c9978-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c9978-106">Parameters</span></span>  

 `ppEvent`  
 <span data-ttu-id="c9978-107">enuncia Un puntero a la dirección de una instancia de [IHostAutoEvent](ihostautoevent-interface.md) implementada por el host, o null si no se pudo crear el objeto de evento.</span><span class="sxs-lookup"><span data-stu-id="c9978-107">[out] A pointer to the address of an [IHostAutoEvent](ihostautoevent-interface.md) instance implemented by the host, or null if the event object could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c9978-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c9978-108">Return Value</span></span>  
  
|<span data-ttu-id="c9978-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c9978-109">HRESULT</span></span>|<span data-ttu-id="c9978-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="c9978-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c9978-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="c9978-111">S_OK</span></span>|<span data-ttu-id="c9978-112">`CreateAutoEvent` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="c9978-112">`CreateAutoEvent` returned successfully.</span></span>|  
|<span data-ttu-id="c9978-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c9978-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c9978-114">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="c9978-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c9978-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c9978-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c9978-116">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="c9978-116">The call timed out.</span></span>|  
|<span data-ttu-id="c9978-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c9978-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c9978-118">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="c9978-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c9978-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c9978-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c9978-120">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="c9978-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c9978-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c9978-121">E_FAIL</span></span>|<span data-ttu-id="c9978-122">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="c9978-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c9978-123">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="c9978-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c9978-124">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="c9978-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="c9978-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="c9978-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="c9978-126">No había suficiente memoria disponible para crear el objeto de evento solicitado.</span><span class="sxs-lookup"><span data-stu-id="c9978-126">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c9978-127">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c9978-127">Remarks</span></span>  

 <span data-ttu-id="c9978-128">`CreateAutoEvent` crea un objeto de evento automático cuyo estado se cambia automáticamente a no señalizado después de que se haya liberado el subproceso en espera.</span><span class="sxs-lookup"><span data-stu-id="c9978-128">`CreateAutoEvent` creates an auto-event object whose state is automatically changed to non-signaled after the waiting thread has been released.</span></span> <span data-ttu-id="c9978-129">Este método refleja la `CreateEvent` función de Win32 con el valor `false` especificado para el `bManualReset` parámetro.</span><span class="sxs-lookup"><span data-stu-id="c9978-129">This method mirrors the Win32 `CreateEvent` function with a value of `false` specified for the `bManualReset` parameter</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c9978-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c9978-130">Requirements</span></span>  

 <span data-ttu-id="c9978-131">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c9978-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c9978-132">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="c9978-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c9978-133">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c9978-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c9978-134">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c9978-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9978-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="c9978-135">See also</span></span>

- [<span data-ttu-id="c9978-136">ICLRSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c9978-136">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="c9978-137">IHostAutoEvent (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c9978-137">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)
- [<span data-ttu-id="c9978-138">IHostControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c9978-138">IHostControl Interface</span></span>](ihostcontrol-interface.md)
- [<span data-ttu-id="c9978-139">IHostSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c9978-139">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
