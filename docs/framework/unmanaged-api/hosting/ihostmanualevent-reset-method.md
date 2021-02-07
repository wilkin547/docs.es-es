---
description: 'Más información acerca de: IHostManualEvent:: RESET (método)'
title: IHostManualEvent::Reset (Método)
ms.date: 03/30/2017
api_name:
- IHostManualEvent.Reset
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostManualEvent::Reset
helpviewer_keywords:
- Reset method, IHostManualEvent interface [.NET Framework hosting]
- IHostManualEvent::Reset method [.NET Framework hosting]
ms.assetid: 0d101168-b5e3-49ce-90c7-85cf2db83c4c
topic_type:
- apiref
ms.openlocfilehash: 84debb8b37c2cdfdbf294bff6736b081424f9e52
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99708078"
---
# <a name="ihostmanualeventreset-method"></a><span data-ttu-id="3a147-103">IHostManualEvent::Reset (Método)</span><span class="sxs-lookup"><span data-stu-id="3a147-103">IHostManualEvent::Reset Method</span></span>

<span data-ttu-id="3a147-104">Restablece la instancia de [IHostManualEvent](ihostmanualevent-interface.md) actual a un estado no señalado.</span><span class="sxs-lookup"><span data-stu-id="3a147-104">Resets the current [IHostManualEvent](ihostmanualevent-interface.md) instance to a non-signaled state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a147-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3a147-105">Syntax</span></span>  
  
```cpp  
HRESULT Reset ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="3a147-106">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="3a147-106">Return Value</span></span>  
  
|<span data-ttu-id="3a147-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3a147-107">HRESULT</span></span>|<span data-ttu-id="3a147-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="3a147-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3a147-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="3a147-109">S_OK</span></span>|<span data-ttu-id="3a147-110">`Reset` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="3a147-110">`Reset` returned successfully.</span></span>|  
|<span data-ttu-id="3a147-111">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3a147-111">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3a147-112">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="3a147-112">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3a147-113">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3a147-113">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3a147-114">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="3a147-114">The call timed out.</span></span>|  
|<span data-ttu-id="3a147-115">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3a147-115">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3a147-116">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="3a147-116">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3a147-117">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3a147-117">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3a147-118">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="3a147-118">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3a147-119">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3a147-119">E_FAIL</span></span>|<span data-ttu-id="3a147-120">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="3a147-120">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3a147-121">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="3a147-121">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3a147-122">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="3a147-122">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3a147-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3a147-123">Requirements</span></span>  

 <span data-ttu-id="3a147-124">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3a147-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a147-125">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="3a147-125">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3a147-126">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3a147-126">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3a147-127">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3a147-127">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a147-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="3a147-128">See also</span></span>

- [<span data-ttu-id="3a147-129">ICLRSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3a147-129">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="3a147-130">IHostAutoEvent (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3a147-130">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)
- [<span data-ttu-id="3a147-131">IHostManualEvent (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3a147-131">IHostManualEvent Interface</span></span>](ihostmanualevent-interface.md)
- [<span data-ttu-id="3a147-132">IHostSemaphore (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3a147-132">IHostSemaphore Interface</span></span>](ihostsemaphore-interface.md)
- [<span data-ttu-id="3a147-133">IHostSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3a147-133">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
